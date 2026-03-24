# Ex.No:5(C)  FILE HANDLING USING JAVA
## QUESTION:
Write a program to write multiple lines to a file using FileWriter.

## AIM:
To write a program to write multiple lines to a file using FileWriter.

## ALGORITHM :

1.	Start the program.
2.	Create a Scanner to read user input.
3.	Open a FileWriter to write data into multilines.txt.
4.	Continuously read a line from the user.
5.	If the user enters "exit", stop reading further input.
6.	Otherwise, write the line to the file followed by a newline.
7.	Close the writer, close the scanner.
8.	End the program.


## PROGRAM:

```
Program to implement a File Handling using Java
Developed by: Sathyaa R
RegisterNumber: 212223100052
```

## SOURCE CODE:

```
import java.io.FileWriter;
import java.io.IOException;
import java.util.Scanner;

public class WriteMultipleLines
{
    public static void main(String[] args)
    {
        Scanner sc = new Scanner(System.in);
        try
        {
            FileWriter writer = new FileWriter("multilines.txt");
            while (true)
            {
                String line = sc.nextLine();
                if (line.equalsIgnoreCase("exit"))
                {
                    break;
                }
                writer.write(line + System.lineSeparator());
            }
            writer.close();
            System.out.println("File written successfully to multilines.txt");
        }
        catch (IOException e)
        {
            System.out.println("An error occurred: " + e.getMessage());
        }
        finally
        {
            sc.close();
        }
    }
}
```


## OUTPUT:

<img width="1511" height="290" alt="image" src="https://github.com/user-attachments/assets/3c6a6748-50db-4268-b88f-c7fbb983b379" />


## RESULT:
Thus, the program to write multiple lines to a file using FileWriter is written and executed successfully.
