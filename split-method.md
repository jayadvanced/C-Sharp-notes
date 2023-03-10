# Split Method

```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace date_time_dotnet
{
    internal class Program
    {
        static void Main(string[] args)
        {
            string hello = "Hello,How,Are,you";

            string[] parts = hello.Split(',');
            Console.WriteLine(parts[0]);
            Console.WriteLine(parts[1]);
            Console.WriteLine(parts[2]);
            Console.WriteLine(parts[3]);
            Console.WriteLine(hello);

            Console.ReadLine();
        }
    }
}
```