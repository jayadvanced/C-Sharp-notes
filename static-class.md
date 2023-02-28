# Static Class

- Classes that cannot be instantiated or inherited are known as static classes and the static keyword is used before the class name that consists of static data members and static methods.
- It is not possible to create an instance of a static class using the new keyword. The main features of static classes are as follows:
- They can only contain static members.
- They cannot be instantiated or inherited and cannot contain instance constructors. However, the developer can create static constructors to initialize the static members.

```
static class product
{
    public static int ProductId;
    public static string ProductName;
    public static int ProductPrice;
    static product()
    {
        ProductId = 111;
        ProductName = "Guitar";
        ProductPrice = 5000;
    }
    public static void getProductDetails()
    {
        Console.WriteLine("Product id = {0}", ProductId);
        Console.WriteLine("Product Name = {0}", ProductName);
        Console.WriteLine("Product Price = {0}", ProductPrice);
    }
    public static void getDiscount()
    {
        int d_amount = ProductPrice / 10;
        Console.WriteLine("Your discount amount is: {0}", d_amount);
        Console.WriteLine("Total cost of product is: {0}", (ProductPrice - d_amount));
    }
}
```

```
//product p = new product(); //cannot create static class object
product.getProductDetails();
product.getDiscount();

```