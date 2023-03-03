# Params

- It is used as Parameter. which can take variable number of argument.

- Only one Params keyword is allowed and no additional Params will be allowed in function declaration after a params keyword.

```
namespace LearningNeverEnd8
{
    internal class Program
    {
        public static int add(params int[] nums)
        {
            int sum = 0;
            foreach(int i in nums)
            {
                sum += i;
            }

            return sum;
        }
        static void Main(string[] args)
        {
            Console.WriteLine(Program.add(10, 20, 30, 40));
            Console.ReadLine();
        }
    }
}
```
Output:

> 100