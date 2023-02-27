# Copy Constructor

The constructor which creates an object by copying variables from
another object is called a copy constructor.

In simple words, we can say copy constructor is a constructor which
copies a data of one object into another object.
```
class Example
{
    string name;
    int age;

    public Example(string name, int age)
    {
        this.name = name;
        this.age = age;
    }

    //copy constructor
    public Example(Example e)
    {
        this.name = e.name;
        this.age = e.age;
    }

    public void GetData()
    {
        Console.WriteLine("Name is: {0}", name);
        Console.WriteLine("Age is: {0}", age);
    }
}
```

```
Example obj = new Example("Jay", 22);
obj.GetData();
Example obj1 = new Example(obj);
obj1.GetData();
```