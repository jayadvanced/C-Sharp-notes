# Interface

- An interface in c#, contains only abstract members, 

- In C# Programming, by default, all members declared in an interface have public as the access modifier. They don’t allow explicit access modifiers.

- We cannot make object of interface

```
interface IEmployee
{
    void show();
}

class PartTimeEmployee : IEmployee
{
    public void show() 
    {
        Console.WriteLine("This is method of Iemployee interface");
    }
}
internal class Program
{
    static void Main(string[] args)
    {
           PartTimeEmployee pte = new PartTimeEmployee();
            pte.show();
    }
}
```

## Interface Inheritance

```
interface i1
{
    void print();
}
interface i2
{
    void print1();
}
interface i3: i1, i2
{
    void print2();
}
```

## Explicit Implementation


```
interface i1
{
    void show();
}
interface i2
{
    void show();
}
class Myclass : i1, i2
{
    void i1.show()
    {
        Console.WriteLine("this is method of i1 interface");
    }
    void i2.show() 
    { 
        Console.WriteLine("this is method of i2 interface");
    }
}

internal class Program
{
    static void Main(string[] args)
    {
        Myclass obj = new Myclass();
        ((i1)obj).show();
    }
}
```