# STATIC CONSTRUCTOR IN C#

- A static constructor is used to initialize static variables of the class
and to perform a particular action only once.
- Static constructor is called only once, no matter how many
objects you create.
- Static constructor is called before instance (default or
parameterized) constructor.
- A static constructor does not take any parameters and does not
use any access modifiers.

## KEY POINTS OF STATIc CONSTRUCTOR
- Only one static constructor can be created in the class.
- It is called automatically before the first instance of the class
created.
- We cannot call static constructor directly.

```
class Person
{
    public static string PersonName;
    public static int PersonAge;

    static Person()
    {
        PersonName = "Jay";
        PersonAge = 21;
        Console.WriteLine("Static Constructor Invoked !");
    }

    public Person()
    {
        Console.WriteLine("default Constructor Invoked!");
    }
}
```

```
Person jay = new Person();
Person yash = new Person();
```