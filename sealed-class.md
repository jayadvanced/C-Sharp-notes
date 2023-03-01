# Sealed Class

- A sealed class is a class that prevents inheritance.

- The sealed keyword prevents a class from being inherited by any other class.

```
sealed class BaseClass
{
    public void Show1()
    {
        Console.WriteLine("Method of Base Class...");
    }
}
```