# Polymorphism

"Poly" means many "Morphs" means forms

Two Types Of Polymorphism

Static Polymorphism (Compile Time Polymorphism)

Dynamic Polymorphism (Run Time Polymorphism)

## Static Polymorphism (Compile Time Polymorphism)

- The mechanism of linking a function with an object during compile time is called static polymorphism or early binding.

- It is also called static binding.

## Method Or Function Overloading

- You can have multiple definitions for the same function name in the same scope.

- You cannot overload function declarations that differ only by return type.

```
class FunctionOverloading
{
    public void Add(int a, int b)
    {
        Console.WriteLine(a + b);
    }
    public void Add(string a, string b)
    {
        Console.WriteLine(a + b);
    }
    public void Add(float a, float b)
    {
        Console.WriteLine(a + b);
    }
}
```

```
FunctionOverloading f = new FunctionOverloading();
f.Add(2, 3);
f.Add("Hello ", "Friends");
Console.ReadLine();
```

# Operator Overloading

<img src="images\operatoroverloading.png" alt="Operator Overloading">

```
class OperatorOverloading
{
    public string str;
    public int num;
    
    public static OperatorOverloading operator +(OperatorOverloading obj1, OperatorOverloading obj2)
    {
        OperatorOverloading obj3 = new OperatorOverloading();
        obj3.str = obj1.str + obj2.str;
        obj3.num = obj1.num + obj2.num;
        return obj3;
    }
}
```

```
OperatorOverloading obj1 = new OperatorOverloading();
obj1.str = "Jay";
obj1.num = 20;

OperatorOverloading obj2 = new OperatorOverloading();
obj2.str = "Patel";
obj2.num = 30;

OperatorOverloading obj3 = new OperatorOverloading();
obj3 = obj1 + obj2;

Console.WriteLine(obj3.str);
Console.WriteLine(obj3.num);
```