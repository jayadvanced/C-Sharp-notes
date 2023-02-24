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

## String Array
```
string[] my_string = new string[4];
my_string[0] = "Hello";
my_string[1] = "My";
my_string[2] = "name is";
my_string[3] = "Jay";
Console.WriteLine(my_string[1]);
```

### another way to create string
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