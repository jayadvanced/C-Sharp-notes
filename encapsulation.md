# Encapsulation
Encapsulation in C# is a mechanism of wrapping the data (variables) and code acting on the data (methods or properties) together as a single unit.

In encapsulation, the variables of a class will be hidden from other classes, and can be accessed oly through the methods or properties of their current class. Therefore, it is also knovwn as data hiding.

```
namespace LearningNeverEnd5
{
    class Person
    {
        private string Name;
        private int Age;

        public void setName(string Name)
        {
            if (string.IsNullOrEmpty(Name))
            {
                Console.WriteLine("Name is required");
            }
            else
            {
                this.Name = Name;
            }
        }

        public void setAge(int Age)
        {
            if (Age > 0)
            {
                this.Age = Age;
            }
            else
            {
                Console.WriteLine("Age should not be negative or zero");
            }            
        }

        public void getName()
        {
            if(string.IsNullOrEmpty(Name))
            {
            }
            else
            {
                Console.WriteLine(this.Name);
            }  
        }

        public void getAge()
        {
            if (this.Age > 0)
            {
                Console.WriteLine(this.Age);
            }
        }
    }
    internal class Program
    {
        static void Main(string[] args)
        {
            Person p1 = new Person();
            p1.setName("jay");
            p1.getName();

            p1.setAge(0);
            p1.getAge();
            Console.ReadLine();
        }
    }
}
```