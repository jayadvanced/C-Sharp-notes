# Lambda Expression

- The => is the lambda operator which is used in all lambda expressions.

- Lambda expression is a shorthand for an anonymous function.

> The Lambda Expressions can be of two types:

1. Statement Lambda: Consists of the input and a set of statements to be executed.

> Syntax :

> input => { statements };

Note: Does not return any value implicitly

```
public delegate void MyDelegate(int num);

internal class Program
{
static void Main(string[] args)
{
    MyDelegate obj = (a) =>
    {
        a += 5;
        Console.WriteLine(a);
    };
    obj.Invoke(5);
}
}
```

Output:
> 10

2. Expression Lambda: Consists of the input and the expression.

> Syntax :

> input => expression;

Note: Returns the evaluated value implicitly.

```
public delegate int MyDelegate(int num);

internal class Program
{
    static void Main(string[] args)
    {
        MyDelegate obj = (a) => a * a;
        Console.WriteLine(obj.Invoke(5));
        Console.ReadLine();
    }
}
```

Output:
> 25