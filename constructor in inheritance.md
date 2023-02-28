
```
class BaseClass{
    public BaseClass(){
        Console.WriteLine("This is Constructor of Base class");
    }
}

class DerivedClass : BaseClass
{
    public DerivedClass() : base()
        {
            Console.WriteLine("This is Constructor of Derived class");
        }
}
```

```
DerivedClass dc = new DerivedClass();
```

> Output :

> This is Constructor of Base class

> This is Constructor of Derived class



```
class BaseClass{
    public BaseClass(string message){
        Console.WriteLine(message);
    }
}

class DerivedClass : BaseClass
{
    public DerivedClass() : base("Hello C Sharp")
        {
            Console.WriteLine("This is Constructor of Derived class");
        }
}
```

```
DerivedClass dc = new DerivedClass();
```

> Output :

> Hello C Sharp

> This is Constructor of Derived class