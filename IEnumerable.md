# IEnumerable

WHAT IS IENUMERABLE IN C#?

- When we use collections in c# we need to iterate the items of the collection by using foreach loop.
- In c#, IEnumerable is an interface and it is useful to enable an iteration over non-generic collections.
- Every collection class whether it is genericor non generic collection, implements lenumerable interface.
- IEnumerable in C# is an interface that defines one method GetEnumerator which returns an IEnumerator interface.
- This allows readonly access to a collection then a collection that implements IEnumerable can be used with a for-each statement.

- IEnumerable interface is a generic interface which allows looping over generic or non-generic lists.
- IEnumerable interface also works with linq query expression.

- Enumerator means count karne wala.
- IEnumerator is an interface, it has 3 things which helps to get  current elements from the collection, two methods 1 property.

-- MoveNext()

- Sets the enumerator to the next element of the collection; it Returns true if the enumerator was successfully set to the next element and false if the enumerator has reached the end of the
collection.

-- Reset()

- Sets the enumerator to its initial position, which is before the first element in the collection.

```
using System;
using System.Collections;
using System.Collections.Generic;
using System.Linq;
using System.Security.AccessControl;
using System.Text;
using System.Threading.Tasks;

namespace IEnumerableDemo
{
    class Student
    {
        public int id
        {
            get; set;
        }
        public string name { get; set; }
        public int standard { get; set; }
    }
    class School : IEnumerable
    {
        List<Student> students = new List<Student>();

        public void Add(Student s)
        {
            students.Add(s);
        }

        public IEnumerator GetEnumerator()
        {
            return students.GetEnumerator();
        }
    }
    internal class Program
    {
        static void Main(string[] args)
        {
            Student std1 = new Student();
            std1.id = 1;
            std1.name = "Jay";
            std1.standard = 12;

            Student std2 = new Student();
            std2.id = 2;
            std2.name = "yash";
            std2.standard = 11;

            Student std3 = new Student();
            std3.id = 3;
            std3.name = "rutvik";
            std3.standard = 9;

            //List<Student> students = new List<Student>();
            School students = new School();
            students.Add(std1);
            students.Add(std2);
            students.Add(std3);

            foreach (Student s in students)
            {
                Console.WriteLine(s.id + " " + s.name + " " + s.standard); 
            }
            Console.ReadLine();
        }
    }
}
```

Output:

> 1 Jay 12

> 2 yash 11

> 3 rutvik 9


```
List<int> numbers = new List<int>() { 11, 22, 33, 44, 55, 66, 77, 88 };

foreach (int i in numbers)
{
    Console.WriteLine(i);
}

Console.WriteLine("------------------------");

IEnumerator<int> nums= numbers.GetEnumerator();
while (nums.MoveNext())
{
    Console.WriteLine(nums.Current.ToString());
}
Console.ReadLine();
```

Output:

>11

>22

>33

>44

>55

>66

>77

>88
------------------------
>11

>22

>33

>44

>55

>66

>77

>88

IENUMERABLE VS IENUMERATOR INTERFACE
1. IEnumerable and IEnumerator are both interfaces.
2. IEnumerable has just one method called GetEnumerator. This method returns another type which is an interface that interface is IEnumerator.
3. If we want to implement enumerator logic in any collection class, it needs to implement IEnumerable interface (either generic or non-generic).
4. Enumerable has just one method whereas IEnumerator has two methods (MoveNext and Reset) and a property Current.

- The main difference between lEnumerable and IEnumerator is an lEnumerator retains its cursors current state.

## IEnumerable vs IQueryable

- IEnumerable is inherited by IQueryable, Hence IQueryable has all the featdres of IEnumerable and except this, it has its own features.

<img src="images\ienumerable-vs-iquerable.png">