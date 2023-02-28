## Pass By Value

```
public static void PassByValue(int a)
{
    a = a + 10;
    Console.WriteLine("Value is: " + a);
}
```

```
int value = 5;
Program.PassByValue(value); //15
Console.WriteLine(value); //5
```

## Pass By Reference

```
public static void PassByRef(ref int a)
{
    a = a + 10;
    Console.WriteLine("value is:" + a);
}
```

```
int value = 5;
PassByRef(ref value); //15
Console.WriteLine(value); //15
```
## Pass By Out

```
public static void PassByOut(out int a)
{
    a = 20;
    Console.WriteLine("Value is: " + a);
}
```

```
int value;
PassByOut(out value); //20
Console.WriteLine(value); //20
```

<b>Difference</b>
- The only difference between the two is that the out keyword does not require the variables that are passed by reference to be initialized. 