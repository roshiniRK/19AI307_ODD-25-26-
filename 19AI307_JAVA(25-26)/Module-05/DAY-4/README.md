# Ex.No:5(D) THREAD PRIORITY

## QUESTION:
Write a java program to determine the priority and name of the current thread.

Note : Read the threadname from the User


## AIM:
To write a java program to determine the priority and name of the current thread.


## ALGORITHM :

1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read a thread name from the user.
4.	Get the reference to the current thread using Thread.currentThread().
5.	Set the thread’s name to the user-entered value.
6.	Retrieve the thread’s priority and display it.
7.	Display the thread’s name and print the thread object.
8.	End the program.


## PROGRAM:

```
Program to implement a Thread Priority Concept using Java
Developed by: Sathyaa R
RegisterNumber: 212223100052
```

## SOURCE CODE:

```
import java.util.*;

public class CurrentThreadExample 
{
    public static void main(String[] args) 
    {
        Scanner sc = new Scanner(System.in);
        String name = sc.nextLine();

        Thread t = Thread.currentThread();
        t.setName(name);

        System.out.println("Priority of Thread: " + t.getPriority());
        System.out.println("Name of Thread: " + t.getName());
        System.out.println(t);
    }
}
```


## OUTPUT:

<img width="861" height="255" alt="image" src="https://github.com/user-attachments/assets/9ca2fd82-cd0b-4d0b-b95e-f81cf9a69c7f" />


## RESULT:
Thus, the program to determine the priority and name of the current thread is written and executed successfully.
