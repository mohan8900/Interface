# EX-9 Interface

## Aim:
To write a C# program using interface concept

## Algorithm:
## Step 1:
Create an interface name bank

## Step 2:
Declare 2 functions deposit() and withdraw() as abstract methods in the interface.

## Step 3:
Create a class Operations as a Child class and inherit bank

## Step 4:
Create another class Program and inside create the Main function

## Step 5:
Create an object for the operations class

## Step 6:
Get Choice from user for the operation to be performed. Using switch implement the operations

## Step 7:
Using Go-To statement you can run operations again or close the session

## Step 8:
End of the Program

## Program:
```cs
Developed by: A K MOHAN RAJ
Register Number: 2122212300664

using System;

namespace exp9
{
    public interface bank
    {
        public int deposit(int amt);
        public int withdraw(int amt);
    } 

    public class Operations : bank
    {
        public int amt, bal;
        
        public int deposit(int amt)
        {
            this.amt = amt;
            return this.bal + amt;
        }

        public int withdraw(int amt)
        {
            this.amt = amt;
            return this.bal - amt;
        }

        public void lines(int no)
        {
            for (int i = 0; i < no; i++)
            {
                Console.Write("-");
            }
            Console.WriteLine();
        }
    }

    public class Program
    {
        
        public static int Main(string[] args)
        {
            Operations op = new Operations();

            int choice,amt;
            
            Console.Write("Enter Intial Balance: ");
            op.bal = Convert.ToInt32(Console.ReadLine());
            op.lines(20);
            
            operations:
                Console.WriteLine("To Deposit Money - Enter 1");
                Console.WriteLine("To Withdraw Money - Enter 2");
                Console.WriteLine("To View Balance - Enter 3");
                op.lines(20);
                Console.Write("Enter a Number: ");
                choice = Convert.ToInt32(Console.ReadLine());
                op.lines(20);
                switch (choice)
                {
                    case 1:
                        Console.WriteLine("-----DEPOSIT-----");
                        Console.Write("Enter amount: ");
                        amt = Convert.ToInt32(Console.ReadLine());
                        op.bal = op.deposit(amt);
                        Console.WriteLine("New Balance: {0}", op.bal);
                        break;

                    case 2:
                        Console.WriteLine("-----WITHDRAW-----");
                        Console.Write("Enter amount: ");
                        amt = Convert.ToInt32(Console.ReadLine());
                        op.bal = op.withdraw(amt);
                        Console.WriteLine("New Balance: {0}", op.bal);
                        break;

                    case 3:
                        Console.WriteLine("-----BALANCE----");
                        Console.WriteLine("Balance: {0}", op.bal);
                        break;

                    default:
                        Console.WriteLine("Enter a Vaild Choice!!");
                        break;
                }
                op.lines(20);
                Console.WriteLine("Enter 1 to do more operation\nEnter 2 to close session");
                op.lines(20);
                Console.Write("Enter a Numer:");
                int more = Convert.ToInt32(Console.ReadLine());
                op.lines(20);
                if (more == 1)
                    goto operations;
                else
                {
                    Console.WriteLine("Thank You!!");
                    return 0;
                }
        }
    }
}
```
## Output:
![csh1](https://github.com/Vineesh-AI-DS/Interface/assets/93427254/4ff3d79c-07f3-4117-8e3d-b3b81238bb6d)
![csh2](https://github.com/Vineesh-AI-DS/Interface/assets/93427254/1e458c4a-7872-4104-9468-9bdc364a577b)
## Result:
Thus, a C# program using interface concept is written.
