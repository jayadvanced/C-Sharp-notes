# Break Continue Goto

<b>Break Statement</b>

```
Console.Write("Break statement: ");
int i;
for(i=0; i<=10; i++)
{
if(i == 5)
{
break;
}
Console.Write(i);
}
```

<b>Continue statement</b>

```
Console.WriteLine(" ");
Console.Write("continue statement: ");
int i;
for (i = 0; i <= 10; i++)
{
    if (i == 5)
     {
         continue;
     }
     Console.Write(i);
 }
```

<b>Go to Statement</b>

```
Console.WriteLine(" ");
Console.Write("continue statement: ");
int i;
for (i = 0; i <= 10; i++)
{
    if (i == 5)
    {
        goto stop;
    }
    Console.Write(i);
}

stop:
Console.WriteLine(" Program Exits");
```