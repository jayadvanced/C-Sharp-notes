# Stack

- Stack allows null value and also duplicate values.

```
using System.Collections;

namespace LearningNeverEnd7
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Stack Mystack = new Stack();
            Mystack.Push("Jay");
            Mystack.Push(28); 
            Mystack.Push(false);
            Mystack.Push(5.11);

            foreach(object item in Mystack)
            {
                Console.WriteLine(item);
            }

            Mystack.Pop();
            Console.WriteLine("-------------------------");

            foreach(object item in Mystack)
            {
                Console.WriteLine(item);
            }
        }
    }
}
```