# Ex.No:4(A) EXCEPTION HANDLING

## QUESTION:
Read 4 inputs, each expected to be an integer. If the input is not an integer, catch the exception and print "Invalid input".

## AIM:
To write a Java program to read four inputs as integers and display “Invalid input” whenever a non-integer value is entered.


## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a Scanner to read user input.
4.	Use a loop to read 4 separate inputs from the user one by one.
5.	For each input, attempt to convert the string to an integer using Integer.parseInt().
6.	If conversion succeeds, print "Input accepted: value".
7.	If a NumberFormatException occurs, print "Invalid input".
8.	Repeat steps 5-7 until all four inputs are processed.
9.	End the program.


## PROGRAM:

```
Program to implement a Exception Handling using Java
Developed by: Sathyaa R
RegisterNumber: 212223100052
```

## SOURCE CODE:

```
import java.util.*;
public class prog
{
    public static void main(String[] argv)
    {
        Scanner sc = new Scanner(System.in);
        try
        {
            int a = Integer.parseInt(sc.nextLine());
           System.out.println("Input accepted: "+a);
        }
        catch(NumberFormatException e)
        {
            System.out.println("Invalid input");
        }
        
    }
}
```


## OUTPUT:

<img width="637" height="316" alt="image" src="https://github.com/user-attachments/assets/92db1420-7be0-4aff-9940-77945a917c9e" />


## RESULT:
Thus, the program to read four inputs as integers and display “Invalid input” whenever a non-integer value is entered is written and executed successfully.
