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

