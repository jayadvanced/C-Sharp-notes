
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