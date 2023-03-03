# String & String Builder

- Strings are immutable.
- String cannot be changed once created.

<img src="images\string&string-builder.png" alt="String and String builder">

<img src="images\string builder.png">

## String Builder

- StringBuilder is a dynamic object that allows you to expand the number of characters in the string.

- You can give an initial capacity of characters by passing an int value in the constructor. By default its 16 characters.

- StringBuilder is mutable.

- StringBuilder performs faster than string when appending multiple string values.

- Use StringBuilder when you need to append more than three or four strings.

Ex.

```
StringBuilder sb = new StringBuilder(50);
// OR
StringBuilder sb = new StringBuilder("Hello World!!",50);
```

```
static void Main(string[] args)
{
    string s1 = "Jay";
    Stopwatch sw1 = new Stopwatch();
    
    sw1.Start();
    for(int i=0;i<100000; i++)
    {
        s1 = s1 + i;
    }
    sw1.Stop();
    
    StringBuilder sb = new StringBuilder();
    Stopwatch sw2 = new Stopwatch();
    
    sw2.Start();
    for(int i = 0; i < 100000; i++)
    {
        sb.Append(i);
    }
    sw2.Stop();
    Console.WriteLine("Time Taken By string: {0}", sw1.ElapsedMilliseconds);
    Console.WriteLine("Time Taken By String Builder: {0}", sw2.ElapsedMilliseconds);

    Console.ReadLine();
}
```

Output:

> Time Taken By string: 33376

> Time Taken By String Builder: 18
