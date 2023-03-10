# LINQ

- LINQ stands for Language Integrated Query
- LINQ in C# is used to work with data access from data sources such as objects, data sets, SQL Server, and XML etc.
- LINQ is a data querying API with SQL like query syntaxes.

```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace learningNeverEnd9__Linq
{
    internal class Program
    {
        static void Main(string[] args)
        {
            int[] age = { 41, 22, 5, 74, 15, 66, 27, 8, 29 };
            var a = from i in age where i > 20 select i;
            foreach(int item in a)
            {
                Console.WriteLine(item+ " ");
            }
            Console.ReadLine();
        }
    }
}
```

Output:

> 41 22 74 66 27 29

## sorting

```
using System;
using System.Collections.Generic;
using System.ComponentModel.Design;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace learningNeverEnd9__Linq
{
    internal class Program
    {
        static void Main(string[] args)
        {
            int[] age = { 41, 22, 5, 74, 15, 66, 27, 8, 29 };
            var a = from i in age where i > 20 select i;
            var b = from i in age where i > 20 orderby i descending select i;
            foreach(int item in a)
            {
                Console.Write(item + " ");
            }
            Console.WriteLine();

            foreach(int item in b)
            {
                Console.Write(item + " ");
            }
            Console.ReadLine();
        }
    }
}
```

Output:

> 41 22 74 66 27 29

> 74 66 41 29 27 22


```
using System;
using System.Collections.Generic;
using System.ComponentModel.Design;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace learningNeverEnd9__Linq
{
    internal class Program
    {
        static void Main(string[] args)
        {
            string[] names = {"Jay", "Yash", "Rutvik", "Nihar", "Ayush" };
            var a = from name in names where name.Contains("y") select name;

            foreach(string item in a)
            {
                Console.WriteLine(item);
            }
            Console.ReadLine();
        }
    }
}
```

Output:

> Jay

> Ayush