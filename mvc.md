# MVC

Model: The model contains data that is represented by the view.

View: responsible for presenting Modal(data) and handle user interaction.

Controller: manages presentation and model.

<img src="images\mvc.png">

@ you tell compiler you writting c# not html code in .cshtml file


```
public IActionResult CreateDog(DogViewModel dogViewModel)
{
    //return View("Index");// Retun direct to cshtml page
    return View(nameof(Index)); // it will first call index method then call cshtml page
}
```


index.cshtml

```
@model List<FirstMVCApp.Models.DogViewModel>
```

here we defined list because we passed list at controller

```
public IActionResult Index()
{    
    return View(dogs);
}
```

<b>To add data context Steps:</b>

- install Microsoft.EntityFrameworkCore
- Right click on controller folder
- Add -> New Scaffolded Item 
- MVC Controller with views, using Entity Framework
- Model class -> select -> Book(MVCLibrary.Models)
- Data context class : click plus button -> add -> Add

Migration adding

- PM> Add-Migration InitialCreate

seeding -> create database with initial values

After adding Author in app

- PM> Add-Migration AddedBookAuthor
