# Ternary Operator, If Else, Switch

## Ternary Operator

<b> Syntax: </b>

Boolean Expression ? First Statement : Second Statement

```
int a = 9;
string b = (a > 10) ? "A is greather than 10" : "A is less than 10";
Console.WriteLine(b);
```

<b> Precedence of Operator --> ( ), /, *, +, - </b>

## Decision making Condition

```
int percentage = 90;

if (percentage >= 80)
{
    Console.WriteLine("Grade - A1");
}
 else if( percentage >= 70){
   Console.WriteLine("Grade - A");
}
 else if( percentage >= 60)
{
    Console.WriteLine("Grade - B");
}
 else if( percentage >= 50)
{
    Console.WriteLine("Grade - C");
}
else if (percentage >= 40)
{
    Console.WriteLine("Grade - D");
}
else if (percentage >= 33)
{
   Console.WriteLine("Grade - E");
}
else if (percentage < 33)
{
    Console.WriteLine("Fail");
}
```

## Switch case

```
int week_number = 9;

switch (week_number)
{
case 1:
Console.WriteLine("monday");
break;
case 2:
Console.WriteLine("Tuesday");
break;
case 3:
Console.WriteLine("Wedensday");
break;
case 4:
Console.WriteLine("Thursday");
break;
case 5:
Console.WriteLine("Friday");
break;
case 6:
Console.WriteLine("saturday");
break;
case 7:
Console.WriteLine("sunday");
break;
default: 
Console.WriteLine("invalid number");
break;
}
```