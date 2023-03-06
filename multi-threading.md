# Multi Threading

- Threads are executed by the operating system using time-sharing.

- Threads are executed simultaneously.

```
using System.Threading;
namespace LearningNeverEnd8
{
    internal class Program
    {
        public static void func1()
        {
            for(int i=1; i<=50; i++)
            {
                Console.WriteLine("Func1: " + i);
            }
        }

        public static void func2()
        {
            for (int i = 1; i <= 50; i++)
            {
                Console.WriteLine("Func2: " + i);
                if(i == 25)
                {
                    Console.WriteLine("Thread is going to sleep for 8 second");
                    Thread.Sleep(8000);
                }
            }
        }

        public static void func3()
        {
            for (int i = 1; i <= 50; i++)
            {
                Console.WriteLine("Func3: " + i);
            }
        }
        static void Main(string[] args)
        {
            Thread t = Thread.CurrentThread;
            t.Name = "Main Thread";
            Console.WriteLine("Current Executing Thread is: " +  Thread.CurrentThread.Name);

            //Program.func1();
            //Program.func2();
            //Program.func3();

            Thread t1 = new Thread(func1);
            Thread t2 = new Thread(func2);
            Thread t3 = new Thread(func3);

            t1.Start();
            t2.Start();
            t3.Start();

            Console.ReadLine();
        }
    }
}
```

Output:

> Current Executing Thread is: Main Thread

>Func1: 2

> Func1: 1

> Func1: 4

> Func1: 3

> Func3: 1

> Func2: 1

> Func3: 2

> Func3: 3

> Func3: 4

> Func3: 5

> Func3: 6

> Func3: 7

> Func3: 8

> Func3: 9

> Func3: 10

> Func3: 11

> Func3: 12

> Func3: 13

> Func3: 14

> Func3: 15

> Func3: 16

> Func3: 17

> Func3: 18

> Func3: 19

> Func3: 20

> Func3: 21

> Func3: 22

> Func3: 23

> Func1: 5

> Func1: 6

> Func1: 7

> Func1: 8

> Func1: 9

> Func1: 10

> Func1: 11

> Func1: 12

> Func1: 13

> Func1: 14

> Func1: 15

> Func1: 16

> Func3: 24

> Func2: 2

> Func1: 17

> Func1: 18

> Func3: 25

> Func1: 19

> Func1: 20

> Func1: 21

> Func1: 22

> Func1: 23

> Func1: 24

> Func1: 25

> Func2: 3

> Func2: 4

> Func2: 5

> Func2: 6

> Func3: 26

> Func3: 27

> Func3: 28

> Func3: 29

> Func3: 30

> Func3: 31

> Func3: 32

> Func1: 26

> Func2: 7

> Func2: 8

> Func2: 9

> Func2: 10

> Func2: 11

> Func2: 12

> Func2: 13

> Func2: 14

> Func2: 15

> Func2: 16

> Func2: 17

> Func2: 18

> Func1: 27

> Func3: 33

> Func3: 34

> Func3: 35

> Func3: 36

> Func3: 37

> Func3: 38

> Func3: 39

> Func3: 40

> Func3: 41

> Func3: 42

> Func3: 43

> Func3: 44

> Func2: 19

> Func1: 28

> Func1: 29

> Func1: 30

> Func2: 20

> Func3: 45

> Func3: 46

> Func3: 47

> Func3: 48

> Func3: 49

> Func3: 50

> Func1: 31

> Func1: 32

> Func1: 33

> Func1: 34

> Func1: 35

> Func2: 21

> Func2: 22

> Func1: 36

> Func1: 37

> Func1: 38

> Func1: 39

> Func1: 40

> Func1: 41

> Func1: 42

> Func2: 23

> Func2: 24

> Func2: 25

> Thread is going to sleep for 8 second

> Func1: 43

> Func1: 44

> Func1: 45

> Func1: 46

> Func1: 47

> Func1: 48

> Func1: 49

> Func1: 50

> Func2: 26

> Func2: 27

> Func2: 28

> Func2: 29

> Func2: 30

> Func2: 31

> Func2: 32

> Func2: 33

> Func2: 34

> Func2: 35

> Func2: 36

> Func2: 37

> Func2: 38

> Func2: 39

> Func2: 40

> Func2: 41

> Func2: 42

> Func2: 43

> Func2: 44

> Func2: 45

> Func2: 46

> Func2: 47

> Func2: 48

> Func2: 49

> Func2: 50
