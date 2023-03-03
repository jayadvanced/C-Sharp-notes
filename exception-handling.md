# Exception & Handling

```
internal class Program
{
    static void Main(string[] args)
    {
        Console.WriteLine("Enter first Number:");
        int num1 = int.Parse(Console.ReadLine());

        Console.WriteLine("Enter Second number:");
        int num2 = int.Parse(Console.ReadLine());

        try
        {
            int result = num1 / num2;
            Console.WriteLine("Division Result=" + result);
        }
        catch (DivideByZeroException ex)
        {
            Console.WriteLine("You cannot divide number by zero:");
            Console.WriteLine(ex.Message);
        }
    }
}
```

Output:

>Enter first Number:

>3

>Enter Second number:

>0

>You cannot divide number by zero:

>Attempted to divide by zero.


## Index out of range Exception

```
internal class Program
{
    static void Main(string[] args)
    {
        int[] arr = new int[3];
        try
        {
            arr[0] = 1;
            arr[1] = 2;
            arr[2] = 3;
            arr[3] = 4;

            foreach (int i in arr)
            {
                Console.WriteLine(i);
            }
        }
        catch(Exception ex)
        {
            Console.WriteLine("Array range Exceeded");
            Console.WriteLine(ex.Message);
        }
    }
}
```

Output:

> Array range Exceeded

> Index was outside the bounds of the array.

## HANDLING FORMAT EXCEPTION 

```
internal class Program
{
    static void Main(string[] args)
    {
        Console.WriteLine("Enter a number :");
        string number = Console.ReadLine();
        try
        {
            int num = int.Parse(number);
            Console.WriteLine("Number is: " + num);
        }
        catch(Exception ex)
        {
            Console.WriteLine(ex.Message);
        }
        Console.ReadLine();
    }
}
```

Output:

>Enter a number :

>hello

>Input string was not in a correct format.

## TRY WITH MULTIPLE CATCH BLOCKS

```
internal class Program
{
    static void Main(string[] args)
    {
    try
        {
            //int a = 10;
            //int b = 0;
            //int c = a / b;

            //string a = null;
            //Console.WriteLine(a.Length);

            int[] arr = new int[3];
            arr[0] = 1;
            arr[1] = 2;
            arr[2] = 3;
            arr[3] = 4;
        }
        catch(DivideByZeroException ex)
        {
            Console.WriteLine(ex.Message);
        }
        catch(NullReferenceException ex)
        {
            Console.WriteLine(ex.Message);
        }
        catch(Exception ex)
        {
            Console.WriteLine(ex.Message);
        }
    }
}
```

Output:

> Index was outside the bounds of the array.

## FINALLY BLOCK WITH TRY CATCH

- Finally block is always executed whether exception is occures or not.

```
try
{
    int a = 10;
    int b = 0;
    int c = a / b;
    Console.WriteLine(c);
}
catch(Exception e)
{
    Console.WriteLine(e.Message);
}
finally
{
    Console.WriteLine("Finally block Executed...");
}
```

Output:

> Attempted to divide by zero.

> Finally block Executed...


## Throw Keyword

```
internal class Program
{
    static void Main(string[] args)
    {
        Console.WriteLine("Enter your age=");
        int age = int.Parse(Console.ReadLine());
        try
        {
            if (age >= 18)
            {
                Console.WriteLine("You are eligible to vote");
            }
            else
            {
                throw new Exception("You are not eligible to vote");
            }
        }
        catch (Exception ex)
        {
            Console.WriteLine(ex.Message);
        }
    }
}
```