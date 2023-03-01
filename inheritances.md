## Single Inheritance

```
class Baseclass 
{
    public void Show1() {
    Console.WriteLine("this is a method of base class . . ");
}
}
class DerivedClass : Baseclass
{
    public void Show2()
    {
        Console.WriteLine("this is a method of derived class");
    }
}
```

```
DerivedClass dc1= new DerivedClass();
dc1.Show1();
dc1.Show2();
```

## Hierarchical Inheritance

```
class Baseclass 
{
    public void Show1() {
    Console.WriteLine("this is a method of base class . . ");
}
}
class DerivedClass1 : Baseclass
{
    public void Show2()
    {
        Console.WriteLine("this is a method of 1st derived class");
    }
}
class DerivedClassd2 : Baseclass
{
    public void Show3()
    {
        Console.WriteLine("this is a method of 2nd derived class");
    }
}
```

```
DerivedClass1 dc1= new DerivedClass1();
dc1.Show1();
dc1.Show2();

DerivedClass2 dc2= new DerivedClass2();
dc2.Show1();
dc2.Show3();
```

## Multilevel Inheritance

```
class Baseclass 
{
    public void Show1() {
    Console.WriteLine("this is a method of base class . . ");
}
}
class DerivedClass1 : Baseclass
{
    public void Show2()
    {
        Console.WriteLine("this is a method of 1st derived class");
    }
}
class DerivedClassd2 : DerivedClass1
{
    public void Show3()
    {
        Console.WriteLine("this is a method of 2nd derived class");
    }
}
```

```
DerivedClass1 dc1= new DerivedClass1();
dc1.Show1();
dc1.Show2();

DerivedClass2 dc2= new DerivedClass2();
dc2.Show1();
dc2.Show2();
dc2.Show3();
```

## Multiple Inheritance

- there is no concept of multiple inheritance using classes

-> there is concept of multiple inheritance using interface

```
class Person
{

}
interface Employee
{

}
class Teacher : Person, Employee
{
    
}