# Dependency Injection

## TIGHT COUPLING
Tight coupling is when a group of classes are highly dependent on one another.

## LOOSE COUPLING
Loose coupling means that the classes are independent of each other.

### How to avoid tight coupling?
By using dependency injection

<img src="images\dependency-injection.png">

- Dependency injection is achieved by using interfaces.
- Interfaces are a powerful tool to use for decoupling(tight coupling convert to loose  coupling).
- Dependency Injection is basically providing the objects that an object needs, instead of having it construct the objects themselves.
- DI is a technique whereby one object supplies the dependencies of another object.
- With the help of DI we can write loosely coupled code.

<img src="images\dependency-injection-types.png">

## Tightly coupled program
```
namespace DependencyInjection{
    class CurrentAccount{
        public void PrintDetails(){
            Console.WriteLine("Details of Current Account");
        }
    }
    class SavingAccount{
        public void PrintDetails(){
            Console.WriteLine("Details of Saving Account");
        }
    }
    class Account{
        CurrentAccount ca = new CurrentAccount();
        SavingAccount sa = new SavingAccount();

        public void PrintAccounts(){
            ca.PrintDetails();
            sa.PrintDetails();
        }
    }

    class Program{
        static void Main(string[] args){
                Account a = new Account();
                a.PrintAccounts();
                Console.ReadLine();
        }
    }
}
```

Output:
>Details of Current Account

>Details of Saving Account

## There are 3 types of DI in C#

## 1. Constructor Injection

```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace DependencyInjectionCsharp
{
    public interface IAccount
    {
        void PrintDetails();
    }

    class CurrentAccount : IAccount
    {
        public void PrintDetails()
        {
            Console.WriteLine("Details Of Current Account..");
        }
    }
    class SavingAccount : IAccount
    {
        public void PrintDetails()
        {
            Console.WriteLine("Details Of Saving Account..");
        }
    }

    class Account
    {
        private IAccount account;

        public Account(IAccount account) // Parameterized Constructor
        {
            this.account = account;
        }

        public void PrintAccounts()
        {
            account.PrintDetails();
        }

    }

    class Program
    {
        static void Main(string[] args)
        {
            IAccount ca = new CurrentAccount();
            Account a = new Account(ca);
            a.PrintAccounts();

            IAccount sa = new SavingAccount();
            Account a2 = new Account(sa);
            a2.PrintAccounts();

            Console.ReadLine();
        }
    }
}
```

## 2. Setter or property Injection

```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace DependencyInjectionCsharp
{
    public interface IAccount
    {
        void PrintDetails();
    }

    class CurrentAccount : IAccount
    {
        public void PrintDetails()
        {
            Console.WriteLine("Details Of Current Account..");
        }
    }
    class SavingAccount : IAccount
    {
        public void PrintDetails()
        {
            Console.WriteLine("Details Of Saving Account..");
        }
    }

    class Account
    {
        public IAccount account { get; set; }

        public void PrintAccounts()
        {
            account.PrintDetails();
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            Account sa = new Account();
            sa.account = new SavingAccount();
            sa.PrintAccounts();

            Account ca = new Account();
            ca.account = new CurrentAccount();
            ca.PrintAccounts();

            Console.ReadLine();
        }
    }
}
```

## 3. Method Injection

```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace DependencyInjectionCsharp
{
    public interface IAccount
    {
        void PrintDetails();
    }

    class CurrentAccount : IAccount
    {
        public void PrintDetails()
        {
            Console.WriteLine("Details Of Current Account..");
        }
    }
    class SavingAccount : IAccount
    {
        public void PrintDetails()
        {
            Console.WriteLine("Details Of Saving Account..");
        }
    }

    class Account
    {
        public void PrintAccounts(IAccount account)
        {
            account.PrintDetails();
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            Account sa = new Account();
            sa.PrintAccounts(new SavingAccount());

            Account ca = new Account();
            ca.PrintAccounts(new CurrentAccount());

            Console.ReadLine();
        }
    }
}
```