Extension Method

- We cannot apply inheritance on sealed classes.
- There is no inheritance is available for structures.

Program.cs
```
namespace ExtensionMethodDemo
{
    class Program
    {
        public void Func1()
        {
            Console.WriteLine("This is First Function..");
        }

        public void Func2()
        {
            Console.WriteLine("This is Second Function..");
        }

        static void Main(string[] args)
        {
            Program p = new Program();
            p.Func1();
            p.Func2();
            Console.ReadLine();
        }
    }
}
```

MyStaticClass.cs

```
namespace ExtensionMethodDemo
{
    static class MyStaticClass
    {
        public static void Func3(this Program p, int i)
        {
            Console.WriteLine("This is Third Function.. " + i);
        }

        public static bool IsGreaterThan(this int i, int value)
        {
            return i > value;
        }
    }
}
```

TestExtensionMethod.cs

```
namespace ExtensionMethodDemo
{
    class TestExtensionMethod
    {
        static void Main()
        {
            Program p = new Program();

            p.Func3();
            int i = 20;
            bool result = i.IsGreaterThan(10);
            Console.WriteLine(result);


            Console.ReadLine();
        }
    }
}
```