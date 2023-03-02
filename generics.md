# Generics

C#, Generics allow you to write a class or method that can work with any data type.

```
class Example
{
    public static void ShowArray<T>(T[] arr)
    {
        for(int i=0; i<arr.Length; i++)
        {
            Console.WriteLine(arr[i]);
        }
    }
}

internal class Program
{
    static void Main(string[] args)
    {
        int[] numbers = new int[3];
        numbers[0] = 1;
        numbers[1] = 2;
        numbers[2] = 3;

        string[] name = { "jay", "yash", "aayush" };
        Example.ShowArray(numbers);
        Example.ShowArray(name);
    }
}
```

Output:
> 1

> 2

> 3

> jay

> yash

> aayush

## Generics Class

```
class Example<T>
{
    T box;
    public Example(T b)
    {
        this.box = b;
    }

    public T getBox()
    {
        return this.box;
    }
}
internal class Program
{
    static void Main(string[] args)
    {
        Example<int> e = new Example<int>(20);
        Console.WriteLine(e.getBox());
        
        Example<string> e1 = new Example<string>("Hello");
        Console.WriteLine(e1.getBox());
    }
}
```