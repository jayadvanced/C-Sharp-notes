# Indexders

- Indexers allow our object to be used just like an array, or we can say we can index the object using [ ] brackets just like arrays.
- Indexer is created with the help of this keyword.

- Indexer Concept is object act as an array.
- Indexers in C# must have at least one parameter. Else the compiler will generate a compilation error.

```
class Employee
{
    private int[] Age = new int[3];

    public int this[int index]
    {
        set
        {
            if(index >= 0 && index < Age.Length) 
            {
                if(value > 0)
                {
                    Age[index] = value;
                }
                else
                {
                    Console.WriteLine("Value is invalid!!");
                }
            }
            else
            {
                Console.WriteLine("Invalid index");
            }
        }
        get
        {
            return Age[index];
        }
    }
    public int this[int index, int i]
    {
        set
        {
            Age[index] = value + i;
        }
        get
        {
            return Age[index];
        }
    }
}
```

```
Employee emp = new Employee();
emp[2] = -2;
emp[0, 5] = 5;
Console.WriteLine(emp[2]);
Console.WriteLine(emp[0]);
```