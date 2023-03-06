# Array, Multi Dimenstional Array, Foreach

## Int Array
```
int[] my_array = new int[4];
my_array[0] = 11;
my_array[1] = 22;
my_array[2] = 33;
my_array[3] = 44;
Console.WriteLine(my_array[1]);
```

### Another way to create int Array

```
var numbers = new double[4] {12.7, 20.3, 6.22, 8.0}
//or
var numbers = new double[] {12.7, 20.3, 6.22, 8.0}
//or
var numbers = new[] {12.7, 20.3, 6.22, 8.0}
```

## String Array
```
string[] my_string = new string[4];
my_string[0] = "Hello";
my_string[1] = "My";
my_string[2] = "name is";
my_string[3] = "Jay";
Console.WriteLine(my_string[1]);
```

### another way to create string Array
```
string[] my_second_string = new string[] { "Hello", "My", "name is", "Jay 2" };

string[] my_third_string = { "Hello", "My", "name is", "Jay 3" };
```

## Foreach Loop

```
string[] my_string = { "Hello", "My", "Name", "Jay"};
int[] my_int_array = { 11, 22, 33, 44 };

foreach(string item in my_string)
{
    Console.WriteLine(item);
}

foreach(int item in my_int_array)
{
    Console.WriteLine(item);
}
```
## Multi dimentional Array

```
int[,] multi_array = new int[3, 4]
{
    {11, 22, 33, 44},
    {23, 32, 69, 89},
    {24, 23, 45, 67}
};

Console.WriteLine(multi_array[1, 2]);
Console.WriteLine(multi_array.GetLength(0)); //row length
Console.WriteLine(multi_array.GetLength(1)); //Column length
Console.WriteLine(multi_array.Rank);

// access whole multi dimentional array
for(int i = 0;i < multi_array.GetLength(0); i++)
{
    for(int j=0; j < multi_array.GetLength(1); j++)
    {
        Console.Write(multi_array[i, j] + " ");
    }
    Console.WriteLine(" ");
}

// Foreach multi array
foreach (int item in multi_array)
{
    Console.WriteLine(item);
}
```

## Rectangular Array Or multidimensional Array:
There are 3 ways to initialize multidimensional array in C# while declaration.

```
int[,] arr = new int[3, 3] {
    { 1, 2, 3},
    { 4, 5, 6}, 
    { 7, 8, 9} 
};

//We can omit the array size.
int[,] arr1 = new int[,] { { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };
//We can omit the new operator also.
int[,] arr2 ={ { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };
```

## JAGGED Array

Is a multidimensional array where one of the specified dimensions can have varying sizes.

Can have unequal number of columns for each row.

```
int[][] jagged_array = new int[3][];
jagged_array[0] = new[] { 1, 2, 3 };
jagged_array[1] = new[] { 1, 2, 3, 4, 5, 6 };
jagged_array[2] = new[] { 1, 2, 3, 4 };

Console.WriteLine(jagged_array[0][2]);

for(int i=0; i<jagged_array.GetLength(0); i++)
{
    for(int j=0; j < jagged_array[i].Length; j++)
    {
        Console.Write(jagged_array[i][j]);
    }
    Console.WriteLine(" ");
}

foreach (int[] items in jagged_array)
{
    foreach(int i in items)
    {
        Console.Write(i);
    }
    Console.WriteLine(" ");
}
```

## CREATING ARRAY WITH USER INPUT

```
Console.WriteLine("Enter total number of items");
int num = int.Parse(Console.ReadLine());
int[] numbers = new int[num];

for (int i = 0; i < num; i++)
{
    int data = int.Parse(Console.ReadLine());
    numbers[i] = data;
}

foreach (int item in numbers)
{
    Console.WriteLine(item);
}
```