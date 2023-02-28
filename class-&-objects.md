# Class & Objects

```
internal class Program
{
    class student
    {
        int rollno;
        string name;
        int age;
        int standard;

        public void setRollNo(int rollno)
        {
            this.rollno = rollno;
        }
        public int getRollNo()
        {
            return this.rollno;
        }
    }
    static void Main(string[] args)
    {
        student s = new student();
        s.setRollNo(1);
        Console.WriteLine(s.getRollNo());
        Console.ReadLine();
    }
}
```