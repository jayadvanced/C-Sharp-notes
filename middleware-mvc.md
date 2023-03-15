- A middleware is nothing but a component (class) which is executed on every request in ASP.NET Core application.
- Middleware in ASP.NET Core controls how our application responds to HTTP requests.
- Middleware are software components that are assembled into an application pipeline to handle requests and responses.

-----------------------------------------------

- It can also control how our application looks when there is an error.
- It is a key piece in how we authenticate and authorize a user to perform specific actions.
- Middleware has access to all the request and response.
- Middlewares are located in Configure method in Startup.cs class file.


## Steps

-> enable hot reload

-> right click on project file -> open Manage NuGet Package -> click on browse -> search -> entityframeworkcore -> install Microsoft Entity FrameworkCore

---------------------------------------------

-> properties -> launch settings.json file -> port on which web app run

-> wwwroot -> static files

-> appsettings.json -> different in development, staging, production -> save connection string to database to connect with application 

-> one controller -> more than one action method

-> right click on models -> add -> class -> Category.cs

```
using System.ComponentModel.DataAnnotations;

namespace SampleApplication.Models
{
    public class Category
    {
        [Key]
        public int Id { get; set; }

        [Required]
        public string Name { get; set; }

        public int DisplayOrder { get; set; }

        public DateTime CreatedDateTime { get; set; } = DateTime.Now;
    }
}
```

### Data anotation

primary key -> [key]

### Connection string

- more than one connection
- used to connect with first server than database
- Mutiple Acive Result sets -> more than one query we apply on that

```
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
    "AllowedHosts": "*",
    "ConnectionStrings": {
        "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=SampleApplicationDB;Trusted_Connection=True;MultipleActiveResultSets=true"
    }
}
```

register context file in program.cs file 

### Data Context file

create folder -> data
create class file ApplicationDbContext.cs

```
using Microsoft.EntityFrameworkCore;
using SampleApplication.Models;

namespace SampleApplication.Data
{
    public class ApplicationDbContext : DbContext
    {
        public ApplicationDbContext(DbContextOptions<ApplicationDbContext> options)
            :base(options)
        {

        }
        public DbSet<Category> Categories { get; set; }
    }
}
```
To register it program.cs

```
using Microsoft.EntityFrameworkCore;
using SampleApplication.Data;


builder.Services.AddDbContext<ApplicationDbContext>(options =>
{
    options.UseSqlServer(builder.Configuration.GetConnectionString("DefaultConnection"));
});
```

### Create database
- Tools -> NuGet Package Manager -> Package manager Console

- project right click -> manage nuGetpackage -> tools package search -> Microsoft.Entity.Framework.Tools

- in PM -> 

```
add-migration AddCategoryToDatabase
```
```
update-database
```

- Tools -> Connect To Database -> Microsoft Sql Server -> servername -> (localdb)\mssqllocaldb -> select SampleApplicationDb from drop down

### Create controller and view

-> right click on controller -> add -> Controller -> CategoryController.cs

-> right click on Index -> add View -> Razor View -> Add

-> layout.cshtml remove privacy and add category 


```
<a class="nav-link text-dark" asp-area="" asp-controller="Category" asp-action="Index">Category</a>
```

indexcs.html
```
@{
    ViewData["Title"] = "Index";
}

<h1>Categories</h1>
```

CategoryController.cs
```
using Microsoft.AspNetCore.Mvc;
using SampleApplication.Data;
using SampleApplication.Models;

namespace SampleApplication.Controllers
{
    public class CategoryController : Controller
    {
        private ApplicationDbContext _context;

        public CategoryController(ApplicationDbContext context)
        {
            _context = context;
        }

        public IActionResult Index()
        {
            IEnumerable<Category> categories = _context.Categories;
            return View(categories);
        }
    }
}
```

### Retrive and display categories
Ienumerable list use -> does not return null 

### bootswatch.com

- download superhero theme
- wwwroot -> add -> new item -> stylesheet ->SuperheroBootswatchTheme.css

lable in createcs.html is tag helper

### create button  category

```
using Microsoft.AspNetCore.Mvc;
using SampleApplication.Data;
using SampleApplication.Models;

namespace SampleApplication.Controllers
{
    public class CategoryController : Controller
    {
        private ApplicationDbContext _context;

        public CategoryController(ApplicationDbContext context)
        {
            _context = context;
        }

        public IActionResult Index()
        {
            IEnumerable<Category> categories = _context.Categories;
            return View(categories);
        }

        [HttpGet]
        public IActionResult Create()
        {
            return View();
        }
    }
}
```

createcs.html

```
@model Category

<form method="post">
    <div class="border p-3 mt-4">
        <div class="row pb-3">
            <h2 class="text-primary">Category</h2>
            <hr />
        </div>
        <div class="row mb-3">
            <lable asp-for="Name"></lable>
            <input asp-for="Name" class="form-control" />
        </div>
        <div class="row mb-3">
            <lable asp-for="DisplayOrder"></lable>
            <input asp-for="DisplayOrder" class="form-control" />
        </div>
        <button class="btn btn-primary" type="submit">Create</button>
    </div>
    <a asp-action="Index" asp-controller="category">Back to List</a>
</form>


@{
    ViewData["Title"] = "Create";
}
```

[ValidateAntiForgeryToken] -> used to prevent 

client side validation means -> page is not refreshed