# Ex.No:4(B)  IMPLEMENT SOLID PRINCIPLES IN JAVA PROGRAM 

## QUESTION:
In a large office, multiple departments send print jobs to a shared central printer. To manage load and prevent collision, a Print Spooler Manager handles all job submissions.

The IT team insists that there should be only one spooler manager instance in the entire system. Regardless of how many jobs or departments exist, all jobs must pass through this one manager.

Your task is to simulate a singleton print job queue. Each print job submitted increases the queue count.

Hidden Clue:
Use Singleton to manage shared access.

Count and log each print job submission.

Validate that state is preserved across all accesses.

Input Format:
First line: Integer n – number of print jobs

Next n lines: Each line contains the department name submitting the print job.

Output Format:
For each job, print:


## AIM:
To create a Java program that uses a singleton spooler to count and log print jobs from multiple departments.

## ALGORITHM :

1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read the number of print jobs n from the user.
4.	For each job, read the department name submitting the print request.
5.	Access the single shared instance of PrintSpoolerManager using getInstance().
6.	Call submitJob() to increase the global queue count.
7.	Print the department name along with the updated total job count.
8.	Repeat until all n print job submissions are processed.
9.	End the program.


## PROGRAM:

```
Program to implement a SOLID Principles in Java Program
Developed by: Sathyaa R
RegisterNumber: 212223100052
```

## SOURCE CODE:

```
import java.util.*;

class PrintSpoolerManager 
{
    private static PrintSpoolerManager instance;
    private int jobCount = 0;

    private PrintSpoolerManager() {}

    public static PrintSpoolerManager getInstance() 
    {
        if (instance == null) 
        {
            instance = new PrintSpoolerManager();
        }
        return instance;
    }
    public int submitJob(String department) 
    {
        jobCount++;
        return jobCount;
    }
}

public class prog 
{
    public static void main(String[] args) 
    {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        sc.nextLine();

        for (int i = 0; i < n; i++) 
        {
            String dept = sc.nextLine();
            PrintSpoolerManager spooler = PrintSpoolerManager.getInstance();
            int total = spooler.submitJob(dept);
            System.out.println(dept + " submitted a print job. Total Jobs in Queue: " + total);
        }
    }
}
```


## OUTPUT:

<img width="1743" height="589" alt="image" src="https://github.com/user-attachments/assets/5d6a347d-271c-469e-8f01-06a144b1f02d" />


## RESULT:
Thus, the program to create a Java program that uses a singleton spooler to count and log print jobs from multiple departments is written and executed successfully.
