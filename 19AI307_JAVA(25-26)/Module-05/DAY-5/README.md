# Ex.No:5(E) MULTITHREADING -SYNCHRONIZATION

## QUESTION:
Synchronize deposit method in a BankAccount class, simulate deposits from multiple threads.

Input:

3 100 200 300
Output:

Final Balance: 600

## AIM:
To write a Java program that synchronizes deposits from multiple threads to compute the final balance.

## ALGORITHM :

1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read the number of deposit operations.
4.	Create a BankAccount object with a synchronized deposit() method.
5.	Create a thread pool with n threads.
6.	For each deposit amount entered by the user, submit a task to the thread pool that calls account.deposit(amount).
7.	Shut down the executor and wait until all threads finish execution.
8.	Retrieve and print the final account balance.
9.	End the program.


## PROGRAM:

```
Program to implement a Synchronization concept using Java
Developed by: Sathyaa R
RegisterNumber: 212223100052
```

## SOURCE CODE:

```
import java.util.*;
import java.util.concurrent.*;

class BankAccount 
{
    private int balance = 0;
    public synchronized void deposit(int amount) 
    {
        balance += amount;
    }
    public int getBalance() 
    {
        return balance;
    }
}

public class BankDepositSync 
{
    public static void main(String[] args) throws Exception 
    {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        BankAccount account = new BankAccount();
        ExecutorService executor = Executors.newFixedThreadPool(n);

        for (int i = 0; i < n; i++) 
        {
            int amount = sc.nextInt();
            executor.execute(() -> account.deposit(amount));
        }
        executor.shutdown();
        executor.awaitTermination(1, TimeUnit.SECONDS);
        System.out.println("Final Balance: " + account.getBalance());
    }
}
```


## OUTPUT:

<img width="602" height="502" alt="image" src="https://github.com/user-attachments/assets/a98abce5-72c6-448d-ba5c-a36ad9295282" />


## RESULT:
Thus, the program that synchronizes deposits from multiple threads to compute the final balance is written and executed successfully.
