# Destructor

A destructor is a special method which has the same name as the class but starts with the character ~ before the class name and immediately de-allocates memory of objects that are no longer required.

features of destructors:

- Destructors cannot be overloaded or inherited.
- Destructors cannot be explicitly invoked.
- Destructors cannot specify access modifiers and cannot take parameters.

```
class Person
{
    public string Name;
    public int Age;
    public Person(string Name, int Age)
    {
        this.Name = Name;
        this.Age = Age;
    }

    public string getName()
    {
        return Name;
    }
    
    public int getAge()
    {
        return Age;
    }

    ~Person()
    {
        Console.WriteLine("Destructor has been invoked !");
    }
}
```

```
Person jay = new Person("jay", 21);
Person yash = new Person("Yash", 22);
Console.WriteLine(jay.getName());
```