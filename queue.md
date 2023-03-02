# Queue

```
static void Main(string[] args)
{
    Queue myQueue = new Queue();
    myQueue.Enqueue("Jay");
    myQueue.Enqueue('J');
    myQueue.Enqueue(28);
    myQueue.Enqueue(true);

    Console.WriteLine(myQueue.Count);

    foreach (object item in myQueue)
    {
        Console.WriteLine(item);
    }

    Console.WriteLine("---------------------");
    myQueue.Dequeue();

    foreach(object item in myQueue)
    {
        Console.WriteLine(item);
    }
}
```

> Output:

> 4

> Jay

> J

> 28

> True

> ---------------------

> J

> 28

> True
