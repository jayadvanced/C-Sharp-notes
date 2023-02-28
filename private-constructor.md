# Private Constructor

When a constructor is created with a private specifier, it is not possible
for other classes to derive from this class, neither is it possible to create
an instance of this class. They are usually used in classes that contain
static members only. Some key points of a private constructor are:

- One use of a private constructor is when we have only static members
- Once we provide a constructor that is either private or public or any, the compiler will not add the parameter-less public constructor to the class.
- In the presence of parameterless private constructor you cannot create a default constructor.
- We cannot inherit the class in which we have a private constructor.
- We can have parameters in private constructor.


```
class Example
{
    public static int a=10;
    private Example() 
    {
        
    }
    public static void getTime()
    {
        Console.WriteLine(DateTime.Now);
    }

    public static int getIncrement()
    {
        return ++a;
    }
}
//Not Possible
//class Example2 : Example
//{

//}
```

```
//Example e = new Example(); // Not possible
Example.getTime();
Console.WriteLine(Example.getIncrement());
```