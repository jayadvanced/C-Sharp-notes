# ASP.Net Web API

- Rest Stands for “Representational state transfer”.

- REST is Architecture pattern or style

- In REST architecture, a REST Server simply provides access to resources and the REST client accesses and presents the resources.

- Here each resource is identified by URIs/ Global IDs.

- A resource is any information that has name like image, entity, document etc.

REST architectural pattern specifies a set of constraints that a system adhere to.
- Client Server
- Stateless
- Cacheable
- Uniform Interface

## differences between MVC and Web API

- We can use the MVC for developing the Web application that return both data and views but the Web API is used for generating the HTTP services that returns only data.

- Web api always extand or inherite ApiController class

## Steps to create web api
- File -> project -> new
- select -> ASP.NET Web Application (.NET Framework)
- then select empty -> tick mvc, webapi
- To create web api controller
- right click controller -> Add -> Controller -> choose Web API 2 empty -> EmployeesDataController

EmployeesDataController.cs
```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Net;
using System.Net.Http;
using System.Web.Http;

namespace asp_dot_net_web_api2.Controllers
{
    public class EmployeesDataController : ApiController
    {
        public string[] myEmployees = { "jay", "Rutvik", "Yash", "Ayush" };

        [HttpGet]
        public string[] GetEmployees()
        {
            return myEmployees;
        }

        [HttpGet]
        public string GetEmployeesByIndex(int id)
        {
            return myEmployees[id];
        }
    }
}
```

Output:

https://localhost:44325/api/EmployeesData
https://localhost:44325/api/EmployeesData/0

## Steps to add MVC controller

- right click on controller -> add -> MVC 5 Empty
- HomeController -> 
- now generate view of Index method -> right click on Index -> click Add View -> add simple empty templete view

add Jquery from

https://code.jquery.com/jquery-3.6.4.min.js

in project folder make scripts/Jquery.js

view file Index.cshtml

```

@{
    ViewBag.Title = "Index";
}
<script src="~/scripts/jquery.js"></script>
<h2>Index</h2>

<input type="button" value="Get All Employees" id="btn1" />
<br />
<input type="text" placeholder="Enter Employee ID" id="txt" />
<input type="button" value="Get Employee By Id" id="btn3" />
<input type="button" value="Clear" id="btn2" />
<br />

<div id="ShowData">


</div>

<script>

    $(document).ready(function () {

        $("#btn3").click(function () {
            var id = $("#txt").val();
            $.getJSON('/api/EmployeesData/' + id, function (responseData) {

                var item = "<h2>" + responseData + "</h2>";
                $(item).appendTo("#ShowData");

            });

        });

        $("#btn2").click(function () {

            $("#ShowData").empty();

        });

        $("#btn1").click(function () {

            $.getJSON('/api/EmployeesData', function (responseData) {

                $.each(responseData, function (key, val) {

                    var item = "<h2>" + val + "</h2>";
                    $(item).appendTo("#ShowData");

                });

            });

        });

    });
</script>
```