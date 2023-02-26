
## Method in c# Programming
C# method cannot begin with a digit, can begin with a letter, underscore, @ character

Example of valid method name are: Add(), Sum_Add(), @Add, _Add()

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

        public static void Show_Name_Age(string name, int age){
            Console.WriteLine("Your Name is: " + name);
            Console.WriteLine("Your age is:" + age);
        }

        static void Main(string[] args)
        {
            Program p1 = new Program();
            p1.Show();

            //Access static method Show1
            Program.Show1();

            //Parameterized Method
            Program.ShowName("Jay");

            //Named Argument
            Program.Show_Name_Age(age:21, name:"Jay");

            Console.ReadKey();
        }
    }
}
```