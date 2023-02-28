## Static and Instance Variable & Methods

static means all objects same variable value of items is same for all objects (class method)
we cannot access instance variable in static method

```
class Student
{
    public int rollNo;
    public string firstname;
    public string lastname;
    public int standard;
    public static string schoolName = "ABC School";  //class method
    public static int fees = 4000;

    // instance method
    public void PrintFullName()
    {
        string fullname = this.firstname + " " + this.lastname;
        System.Console.WriteLine("Your Full Name= {0}", fullname);
    }
    // static means all objects same variable value of items is same for all objects (class method)

    public static int GetFees()
    {
        return fees;
    }
}
```

```
Student jay = new Student();
jay.rollNo= 1;
jay.firstname = "Jay";
jay.lastname = "Patel";
jay.standard = 10;
Console.WriteLine(Student.fees);

Student yash = new Student();
yash.rollNo= 2;
yash.firstname = "Yash";
yash.lastname = "shrivastav";
yash.standard = 12;

Console.Write(jay.rollNo); 
Console.Write(jay.firstname);
Console.Write(jay.lastname);
Console.WriteLine(jay.standard);
jay.PrintFullName();
Console.WriteLine(Student.schoolName);

Console.WriteLine(" ");
Console.WriteLine("-----------------");

Console.Write(yash.rollNo);
Console.Write(yash.firstname); 
Console.Write(yash.lastname);
Console.WriteLine(yash.standard);
yash.PrintFullName();
Console.WriteLine(Student.schoolName);
Console.WriteLine(Student.GetFees());
```