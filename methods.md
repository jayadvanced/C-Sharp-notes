
## Method in c# Programming
```
using System;
namespace learningNeverEnd1
{
    internal class Program
    {
        public void Show()
        {
            Console.WriteLine("Welcome to c# Programming");
        }
        
        public static void Show1()
        {
            Console.WriteLine("welcome to c# static method");
        }

        public static void ShowName(string name = "Unkonwn") //Parameterized Method
        {
            Console.WriteLine("Hello, Welcome " + name);
        }

        static void Main(string[] args)
        {
            Program p1 = new Program();
            p1.Show();

            //Access static method Show1
            Program.Show1();

            //Parameterized Method
            Program.ShowName("Jay");

            Console.ReadKey();
        }
    }
}
```