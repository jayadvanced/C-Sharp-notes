# Partial Class

- It provides a special ability to implement the functionality of a single class into multiple files and all these files are combined into a single class file when the application is compiled.

- We use partial class when code of a class contains so many lines to manage.

Program.cs
```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Partial_class_demo
{
    internal class Program
    {
        static void Main(string[] args)
        {
            StudentPartial obj = new StudentPartial();
            obj.firstName = "Jay";
            obj.lastName = "Patel";
            Console.WriteLine("Your Complete Name is:" + obj.GetCompleteName());
            Console.ReadLine();
        }
    }
}
```

```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Partial_class_demo
{
    public partial class StudentPartial
    {
        private string _firstName;
        private string _lastName;

        public string firstName
        {
            set
            {
                _firstName = value;
            }

            get
            {
                return _firstName;
            }
        }

        public string lastName
        {
            set
            {
                _lastName = value;
            }

            get
            {
                return _lastName;
            }
        }
    }
}
```

```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Partial_class_demo
{
    public partial class StudentPartial
    {
        public string GetCompleteName()
        {
            return _firstName + " " + _lastName;
        }
    }
}
```

Output:

> Your Complete Name is:Jay Patel
