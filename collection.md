<table>
    <tr>
    <th>ARRAY</th>
    <th>COLLECTION</th>
    </tr>
    <tr>
    <td>Cannot be resized at run-time.</td>
    <td>Can be resized at run-time.</td>
    </tr>
     <tr>
    <td>The individual elements are of the same data type.</td>
    <td>The individual elements can be of different data types.</td>
    </tr>
     <tr>
    <td>Do not contain any methods for operations on elements.</td>
    <td>Contain methods for operations on elements.</td>
    </tr>
     <tr>
    <td>We can never insert a value into a middle of an array.</td>
    <td>We can insert a value into a middle of a collection.</td>
    </tr>
     <tr>
    <td>We can never delete a value from a middle of an array.</td>
    <td>We can delete a value from a middle of a collection.</td>
    </tr>
</table>

```
int[] MyArray = new int[3];
MyArray[0] = 1;
MyArray[1] = 2;
MyArray[2] = 3;

Array.Resize(ref MyArray, 4);
MyArray[3] = 4;

for(int i = 0;i < MyArray.Length; i++)
{
    Console.WriteLine(MyArray[i]);
}
```

Output:

> 1

> 2

> 3

> 4

## Array List

```
internal class Program
{
    static void Main(string[] args)
    {
        ArrayList MyList= new ArrayList();
        Console.WriteLine(MyList.Capacity);
        MyList.Add(10);
        Console.WriteLine(MyList.Capacity);
        MyList.Add(20);
        MyList.Add(30);
        MyList.Add(40);
        Console.WriteLine(MyList.Capacity);
        MyList.Add(50);
        Console.WriteLine(MyList.Capacity);

        foreach (object obj in MyList)
        {
            Console.Write(obj + " ");
        }

        Console.WriteLine();

        MyList.Insert(2, 25);

        foreach (object obj in MyList)
        {
            Console.Write(obj + " ");
        }

        Console.WriteLine(" ");
        //MyList.Remove(40);
        MyList.RemoveAt(4);
        foreach(object obj in MyList)
        {
            Console.Write(obj + " ");
        }
    }
}
```

Output:

> 0

> 4

> 4

> 8

> 10 20 30 40 50

> 10 20 25 30 40 50

> 10 20 25 30 50
 




