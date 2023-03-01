# Properties Get-Set

Properties in C# allow you to set and retrieve values of fields declared with any access modifier in a secured manner.

```
class student
{
    private int _StdId;
    private string _FName;
    private string _LName;

    public int StdId {
        set
        {
            if(value <= 0)
            {
                Console.WriteLine("Id cannot be zero or negative");
            }
            else
            {
                _StdId = value;
            }
        }
        get 
        {
            if(_StdId <= 0)
            {
                return -1;
            }
            else
            {
                return _StdId;
            }
        } 
    }

    public string FName
    {
        get;
        set;
    }
    public string LName
    {
        get;
        private set;
    }
}
```

```
student s = new student();
s.StdId = 8;
if (s.StdId != -1)
{
    Console.WriteLine(s.StdId);
}

s.FName = "Jay";
//s.LName = "Patel";

Console.WriteLine(s.FName);
Console.WriteLine(s.LName);
```

## static Properties in C#

```
class University
{
    private static string UniversityName;
    private static string DepartmentName;

    public static string _UniversityName
    {
        set
        {
            UniversityName= value;
        }
        get
        {
            return UniversityName;
        }
    }
}
```

```
University._UniversityName = "RRU";
Console.WriteLine(University._UniversityName);
Console.ReadLine();
```