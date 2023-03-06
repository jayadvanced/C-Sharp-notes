# Generic Collection

A List is one of the generic collection classes in the “System.Collection.Generic” namespace.

- Are Type safe
- variable length (Auto resizing)

<img src="images\boxing-unboxing.png" alt="boxing unboxing">

## List

- A List class can be used to create a collection of any type.

```
static void Main(string[] args)
{
    List<int> Mynumbers = new List<int>();
    Mynumbers.Add(100);
    Mynumbers.Add(44);
    Mynumbers.Add(22);
    Mynumbers.Add(33);
    Mynumbers.Add(55);

    foreach (int i in Mynumbers)
    {
        Console.Write(i + " ");
    }

    Console.WriteLine();
    
    Mynumbers.Sort();

    foreach (int i in Mynumbers)
    {
        Console.Write(i + " ");
    }
}
```
Output:
> 100 44 22 33 55

> 22 33 44 55 100

<table>
<tr>
<th>NON-GENERIC COLLECTION</th>
<th>GENERIC COLLECTION</th>
</tr>
<tr>
<td>These are the collection that can hold elements of different data types.</td>
<td>These are the collection that can hold data of same data type.</td>
</tr>
<tr>
<td>It holds elements as Object type. So it includes overhead of type conversions.</td>
<td>It reduced overhead of type -conversions.</td>
</tr>
<tr>
<td>These are also called loosely typed.</td>
<td>These are also called Strongly typed.</td>
</tr>
<tr>
<td>Not Type Safe.</td>
<td>Type Safe.</td>
</tr>
<tr>
<td>Not Secure</td>
<td>Secure</td>
</tr>
</table>

```
class Employee
{
    public string name { get; set; }
    public int age { get; set; }
    public string designation { get; set; }
}
internal class Program
{
    static void Main(string[] args)
    {

        Employee emp1 = new Employee()
        {
            name = "Jay",
            age = 20,
            designation = "Manager"
        };

        Employee emp2 = new Employee()
        {
            name = "Yash",
            age = 20,
            designation = "Director"
        };

        List<Employee> EmpList = new List<Employee>();
        EmpList.Add(emp1);
        EmpList.Add(emp2);

        foreach(Employee emp in EmpList)
        {
            Console.WriteLine("Employee Name is: {0}, Age is: {1} Designation is: {2}",emp.name, emp.age, emp.designation);
        }

        Console.ReadLine();
    }
}
```

Output:

> Employee Name is: Jay, Age is: 20 Designation is: Manager

> Employee Name is: Yash, Age is: 20 Designation is: Director


Methods Of List<T>

- Add()
- AddRange() : Adds the elements of the specified collection to the end of the List.
- Insert()
- InsertRange() : Inserts the elements of a collection into the List at the specified index.
- Remove()
- RemoveAt()
- RemoveRange()
- RemoveAll()
- Contains()
- Reverse()
- Sort()