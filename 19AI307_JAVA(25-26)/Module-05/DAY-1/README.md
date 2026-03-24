# Ex.No:5(A) INPUTSTREAMREADER 

## QUESTION:
Write a program to read user input from the keyboard using InputStreamReader.

## AIM:
To write a program to read user input from the keyboard using InputStreamReader. 

## ALGORITHM :

1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create an InputStreamReader object to read bytes from the keyboard and convert them to characters.
4.	Wrap it inside a BufferedReader to read text efficiently.
5.	Read a line of text (the user’s name) using readLine().
6.	Store the input in a variable.
7.	Display the message "Hello, <name>!" on the screen and close the BufferedReader.
8.	End the program.


## PROGRAM:

```
Program to implement a InputStreamReader using Java
Developed by: Sathyaa R
RegisterNumber: 212223100052
```

## SOURCE CODE:

```
import java.io.*;

public class ReadUsingInputStreamReader
{
    public static void main(String[] argv)
    {
        try
        {
            InputStreamReader isr = new InputStreamReader(System.in);
            BufferedReader br = new BufferedReader(isr);
            String name = br.readLine();
            System.out.println("Hello, " + name + "!");
            br.close();
        }
        catch (IOException e)
        {
            e.printStackTrace();
        }
    }
}
```


## OUTPUT:

<img width="485" height="220" alt="image" src="https://github.com/user-attachments/assets/02309a6c-f2cc-47be-bebe-216637fbfbcd" />


## RESULT:
Thus, the program to read user input from the keyboard using InputStreamReader is written and executed successfully.
