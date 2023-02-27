## Default Constructor
A Constructor which has not defined any parameter or we can say without any parameters is called default constructor.

```
 class student
        {
            int rollno;
            string name;
            int age;
            int standard;

            public student()
            {
                Console.WriteLine("Constructor called");
            }
            public void setRollNo(int rollno)
            {
                this.rollno = rollno;
            }
            public int getRollNo()
            {
                return this.rollno;
            }
        }
```

```
student s = new student();
s.setRollNo(1);
Console.WriteLine(s.getRollNo());
```

## Parameterized Constructor
A Constructor which has atleast one parameter

```
class Employee
    {
        int EmpId;
        string EmpName;
        int EmpAge;

        public Employee(int EmpId, string EmpName, int EmpAge)
        {
            this.EmpId= EmpId;
            this.EmpName= EmpName;
            this.EmpAge= EmpAge;
        }

        public int getEmpId()
        {
            return this.EmpId;
        }

        public string getEmpName()
        {
            return this.EmpName;
        }

        public int getEmpAge()
        {
            return this.EmpAge;
        }
    }
```

```
Employee e = new Employee(1, "Jay", 21);
Console.WriteLine(e.getEmpName());
Console.WriteLine(e.getEmpAge());
Console.WriteLine(e.getEmpId());
```

## Constructor Overloading

```
class College
{
    public College(int a)
    {
        Console.WriteLine("This is First Constuctor " + a);
    }
    public College(int a, int b)
    {
        Console.WriteLine("This is Second Constructor " + (a + b));
    }
    public College(int a,int b,int c)
    {
        Console.WriteLine("This is Third Constructor " + (a + b +c));
    }
}
```

```
College c = new College(10,20,30);
```