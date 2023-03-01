# Method hiding occurs in inheritance

```
class Parent
{
    public void show()
    {
        Console.WriteLine("Parent class method");
    }
}
class Child: Parent
{
    public void show()
    {
        Console.WriteLine("Child class method");
    }
}
```

```
Child c = new Child();
c.show();
```

> Output:

> Child class method

```
class Parent
{
    public void show()
    {
        Console.WriteLine("Parent class method");
    }
}
class Child: Parent
{
    public new void show()
    {
        base.show();
    }
}
```

```
Child c = new Child();
c.show();
((Parent)c).show();
```

> Output:

> Parent class method

> Parent class method

```
Parent p = new Child();
p.show();
```

> Output:

> Parent class method
