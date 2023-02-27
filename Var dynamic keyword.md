## Var Keyword
- Var keyword is used to store any type of data in its variable.
- Value of var variable is decided at compile time.

```
var b = "HEllo";
Console.WriteLine(b);
Console.WriteLine(b.GetType());
```

## Dynamic Keyword
- Dynamic keyword is also used to store any type of data in its variable.
- Value of dynamic variable is decided at run time.
- When we initialize the dynamic variable with some value then we can change the value of dynamic variable with some other data type value.

```
public static dynamic Show(dynamic a)
{
    //Console.WriteLine(a);
    return a;
}
```

```
dynamic b = 10;
b = "Hello";
Console.WriteLine(b);
Console.WriteLine(b.GetType());

Console.WriteLine(Program.Show("Hello"));
Console.WriteLine(Program.Show(10));
Console.WriteLine(Program.Show(true));
```