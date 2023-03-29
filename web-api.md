# Web-Api

install -> Microsoft.EntityFramework.InMomery

ShoppingListContext.cs
```
using Microsoft.EntityFrameworkCore;

namespace ShoppingListApi.Models
{
    public class ShoppingListContext : DbContext
    {
        public ShoppingListContext(DbContextOptions<ShoppingListContext> options):base(options)
        {
                
        }

        public DbSet<Grocery> Grocery { get; set; }
    }
}
```

program.cs

```
builder.Services.AddDbContext<ShoppingListContext>(opt => opt.UseInMemoryDatabase("ShoppingList"));
```

add New Scaffolded Item

- Right click on controller folder
- Add -> New Scaffolded Item 
<img src="images\api-controller-actions-entity-framework.png">

install
- Microsoft.VisualStudio.Web.CodeGeneration.Design.6.0.13

## Swagger

- two main OpenApi for .NET are Swashbuckle and NsWag.

## Minimal Api

install packages

- Microsoft.EntityFrameworkCore.InMemory
- Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.7.0.4

remove content of program.cs

```
var builder = WebApplication.CreateBuilder(args);

builder.Services.AddEndpointsApiExplorer();
builder.Services.AddSwaggerGen();

var app = builder.Build();

if (app.Environment.IsDevelopment())
{
    app.UseSwagger();
    app.UseSwaggerUI();
}

app.UseHttpsRedirection();

app.Run();
```

this is how we set up minimal Api in 
GET Method
```
app.MapGet("shoppinglist", async (ApiDbContext db) =>
       await db.Groceries.ToListAsync());
```