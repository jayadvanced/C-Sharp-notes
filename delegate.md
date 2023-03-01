# Delegate

signature --> parameter, data type

- Delegate is a type which holds a method’s reference in an object.
- It is also called function pointer.
- In the .Net framework, a delegate points to one or more methods. Once you instantiate the delegate, the corresponding methods invoke.
- Delegate signature should be as same as the method signature referencing by a delegate.
- It is also called function pointer.
- We can use invoke() method with delegates.

```
public delegate void Calculation(int a, int b);
internal class Program
{
    public static void Addition(int a, int b)
    {
        int result = a + b;
        Console.WriteLine("Addition result is {0}", result);
    }

    public static void Subtraction(int a, int b)
    {
        int result = a - b;
        Console.WriteLine("Subtraction result is {0}", result);
    }
    public static void Multiplication(int a, int b)
    {
        int result = a * b;
        Console.WriteLine("Multiplication result is {0}", result);
    }

    public static void Division(int a, int b)
    {
        int result = a / b;
        Console.WriteLine("Division result is {0}", result);
    }
    static void Main(string[] args)
    {
    Calculation obj = new Calculation(Program.Addition);
    obj.Invoke(20, 10);
    obj = Multiplication;
    obj.Invoke(2, 4);
    }
}
```

Output:

> Addition result is 30

> Multiplication result is 8

## Multiple Delegation

```
public delegate void Calculation(int a, int b);
public delegate void Show_Delegate();

internal class Program
{
    public static void Addition(int a, int b)
    {
        int result = a + b;
        Console.WriteLine("Addition result is {0}", result);
    }

    public static void Subtraction(int a, int b)
    {
        int result = a - b;
        Console.WriteLine("Subtraction result is {0}", result);
    }

    public static void Multiplication(int a, int b)
    {
        int result = a * b;
        Console.WriteLine("Multiplication result is {0}", result);
    }

    public static void Division(int a, int b)
    {
        int result = a / b;
        Console.WriteLine("Division result is {0}", result);
    }
    public static void Show()
    {
        Console.WriteLine("THis is show method");
    }
    
    static void Main(string[] args)
    {
    Calculation obj = new Calculation(Program.Addition);
    obj.Invoke(20, 10);
    obj = Multiplication;
    obj.Invoke(2, 4);

    Show_Delegate s_obj = new Show_Delegate(Show);
    s_obj.Invoke();
    }
}
```

> Output:

> Addition result is 30

> Multiplication result is 8

> THis is show method

## Multicast Delegation

```
public delegate void Calculation(int a, int b);
internal class Program
{
    public static void Addition(int a, int b)
    {
        int result = a + b;
        Console.WriteLine("Addition result is {0}", result);
    }

    public static void Subtraction(int a, int b)
    {
        int result = a - b;
        Console.WriteLine("Subtraction result is {0}", result);
    }
    public static void Multiplication(int a, int b)
    {
        int result = a * b;
        Console.WriteLine("Multiplication result is {0}", result);
    }

    public static void Division(int a, int b)
    {
        int result = a / b;
        Console.WriteLine("Division result is {0}", result);
    }
    static void Main(string[] args)
    {
        Calculation obj = new Calculation(Program.Addition);
        obj += Multiplication;
        obj.Invoke(2, 4);
    }
}
```

> Output:

> Addition result is 6

> Multiplication result is 8