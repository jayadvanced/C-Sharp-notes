# Dictionary

> Now we want to create a collection in which we don’t want to access elements through index.

> We want to store data in key value format where keys are user-defined.

> We want to insert same type of data in a collection.

```
using System.Collection.Generic;
```

```
internal class Program
{
    static void Main(string[] args)
    {
        Dictionary<string, string> myDict = new Dictionary<string, string>();
        myDict["a"] = "Hello";
        myDict.Add("b", "How are You");

        Console.WriteLine(myDict["a"]);
        Console.WriteLine(myDict["b"]);

        foreach (KeyValuePair<string, string> item in myDict)
        {
            Console.WriteLine("Key is:" + item.Key + " " + "Value is:" + item.Value);
        }

        foreach(var item in myDict)
        {
            Console.WriteLine("Key is:" + item.Key + " " + "Value is:" + item.Value);
        }
        Console.ReadLine();
    }
}
```

Output:

> Hello

> How are You

> Key is:a Value is:Hello

> Key is:b Value is:How are You

> Key is:a Value is:Hello

> Key is:b Value is:How are You


- In Dictionary, the key cannot be null, but value can be.

- In Dictionary, key must be unique. 