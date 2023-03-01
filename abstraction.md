# Abstraction

- Means displaying what is necessary and encapsulate the unnecessary things to outside the world.

- we cannot make object of abstract class

```
abstract class person
{
    //public abstract void show();
    public string name;
    public int age;
    public long PhoneNumber;

    public abstract void printdetails();
}

class student : person 
{
    public int RollNo;
    public int Fees;

    public override void printdetails()
    {
        Console.WriteLine("student Name: {0}", this.name);
        Console.WriteLine("Student age: {0}", this.age);
        Console.WriteLine("Student PhoneNumber: {0}", this.PhoneNumber);
        Console.WriteLine("Student Roll No: {0}", this.RollNo);
        Console.WriteLine("Student Fees {0}", this.Fees);
    }
}

internal class Program
{
    static void Main(string[] args)
    {
        student jay = new student();
        jay.name = "Jay";
        jay.age = 20;
        jay.PhoneNumber = 1122222222;
        jay.RollNo = 28;
        jay.Fees= 1500;
        jay.printdetails();
    }
}
```