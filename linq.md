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
                Console.WriteLine(item);
            }
            Console.ReadLine();
        }
    }
}
```

Output:

> 41

> 22

> 74

> 66

> 27

> 29