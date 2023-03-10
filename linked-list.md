# Linked list

<img src="images\linked_list.png">

```
LinkedList<int> list = new LinkedList<int>();

list.AddFirst(1);
list.AddFirst(2);

foreach (int i in list)
{
    Console.WriteLine(i);
}

var first = list.First;
list.AddAfter(first, 5);
list.AddBefore(first, 10);

var node = list.First;

while (node != null)
{

    Console.WriteLine(node.Value);
    node = node.Next;
}
```

Output:

> 2

> 1
------
> 10

> 2

> 5

> 1