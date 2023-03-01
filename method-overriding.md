# Method Overriding

It is used to achieve runtime polymorphism.

```
class Parent
{
    public virtual void print()
    {
        Console.WriteLine("This is method of Parent class");
    }
}

class Child : Parent
{
    public override void print()
    {
        Console.WriteLine("This is method of child class");
    }
}
```

```
Parent p = new Child();
p.print();

Console.ReadLine();
```

> Output:

> This method is of Child Class