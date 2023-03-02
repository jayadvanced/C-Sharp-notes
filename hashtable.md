# Hash Table

- HashTable stores data in key/value format.
- In HashTable, keys are not pre-defined it means you can explicitly define user-defined keys in HashTable.
- Contains and ContainsKey are same

```
using System.Collections;

namespace LearningNeverEnd7
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Hashtable ht = new Hashtable();
            ht.Add("Id", 1123);
            ht.Add("Name", "Jay");
            ht.Add("Salary", 20000);
            ht.Add("Designation", "trainee");

            Console.WriteLine(ht["Designation"]);

            Hashtable ht2 = new Hashtable()
            {
                    {1, "one"},
                    {2, "Two"}
            };

            Console.WriteLine(ht2[1]);
            
            foreach(object key in ht.Keys)
            {
                Console.WriteLine(key + " " + ht[key]);
            }

            Console.WriteLine("---------------------------");

            ht.Remove("Salary");

            foreach (object key in ht.Keys)
            {
                Console.WriteLine(key + " " + ht[key]);
            }
            Console.WriteLine(ht.Contains("Salary"));
            Console.WriteLine(ht.ContainsKey("Salary"));
            Console.WriteLine("Id".GetHashCode());
            Console.WriteLine(ht.Count);

            Console.ReadLine();
        }
    }
}
```

> Output:

> trainee

> one

> Designation :trainee

> Name :Jay

> Id :1123

> Salary :20000

> ---------------------------

> Designation :trainee

> Name :Jay

> Id :1123

> False

> False

> -840517657

> 3