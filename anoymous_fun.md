# Anoymous Function

- We don’t required to use access modifiers with anonymous function like public, private etc.

- We don’t required to use return type like int, string because its return type is set as same as delegate type.

- Anonymous functions are suggested when code volumes are less.

- It cannot contain jump statement like goto, break or continue.

- It cannot access ref or out parameter of an outer method.

```
public delegate void MyDelegate(int num);

internal class Program
{
    static void Main(string[] args)
    {
        MyDelegate md_obj = delegate (int a)
        {
            a += 10;
            Console.WriteLine(a);
        };
        md_obj(5);
        md_obj.Invoke(5);
    }
}
```

Output:
> 15

> 15

```
public static void Mymethod(MyDelegate del, int a)
{
    a += 10;
    del.Invoke(a);
    //Console.WriteLine(a);
}
static void Main(string[] args)
{
    Program.Mymethod(delegate (int b) { b += 10; Console.WriteLine(b);}, 5);
}
```     

Output:
> 25