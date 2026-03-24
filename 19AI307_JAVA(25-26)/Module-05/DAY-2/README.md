# Ex.No:5(B) SERIALIZATION AND DESERIALIZATION 

## QUESTION:
Write a Java program to serialize a collection of objects (like ArrayList<Student>) into a file.

## AIM:
To write a Java program to serialize a collection of objects into a file.

## ALGORITHM :

1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read the number of students.
4.	For each student, read id, name, and marks, then add the Student object to an ArrayList.
5.	Create an ObjectOutputStream and write the whole ArrayList to a file (serialization).
6.	Close the output stream.
7.	Create an ObjectInputStream and read the ArrayList back from the file (deserialization).
8.	Display all deserialized students.
9.	End the program.


## PROGRAM:

```
Program to implement a Serialization and Deserialization using Java
Developed by: Sathyaa R
RegisterNumber: 212223100052
```

## SOURCE CODE:

```
import java.io.*;
import java.util.*;

class Student implements Serializable 
{
    private static final long serialVersionUID = 1L;
    private int id;
    private String name;
    private double marks;

    public Student(int id, String name, double marks) 
    {
        this.id = id;
        this.name = name;
        this.marks = marks;
    }
    @Override
    public String toString() 
    {
        return "Student{id=" + id + ", name='" + name + "', marks=" + marks + "}";
    }
}

public class StudentSerializationUserInput 
{
    public static void serializeStudents(List<Student> students, String fileName) 
    {
        try (ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream(fileName))) 
        {
            oos.writeObject(students);
            System.out.println("Students serialized successfully into: " + fileName);
        } 
        catch (IOException e) 
        {
            System.out.println("Error during serialization: " + e.getMessage());
        }
    }

    @SuppressWarnings("unchecked")
    public static List<Student> deserializeStudents(String fileName) 
    {
        List<Student> students = null;
        try (ObjectInputStream ois = new ObjectInputStream(new FileInputStream(fileName))) 
        {
            students = (List<Student>) ois.readObject();
            System.out.println("Students deserialized successfully from: " + fileName);
        } 
        catch (IOException | ClassNotFoundException e) 
        {
            System.out.println("Error during deserialization: " + e.getMessage());
        }
        return students;
    }

    public static void main(String[] args) 
    {
        Scanner scanner = new Scanner(System.in);
        List<Student> students = new ArrayList<>();
        int n = scanner.nextInt();
        scanner.nextLine(); 

        for (int i = 0; i < n; i++) 
        {
            int id = scanner.nextInt();
            scanner.nextLine(); 
            String name = scanner.nextLine();
            double marks = scanner.nextDouble();
            if (i < n - 1) scanner.nextLine();
            students.add(new Student(id, name, marks));
        }

        String fileName = "students.dat";
        serializeStudents(students, fileName);
        List<Student> deserializedStudents = deserializeStudents(fileName);
        
        if (deserializedStudents != null) 
        {
            System.out.println("\nDeserialized Students:");
            for (Student s : deserializedStudents) 
            {
                System.out.println(s);
            }
        }
        scanner.close();
    }
}
```


## OUTPUT:

<img width="1539" height="583" alt="image" src="https://github.com/user-attachments/assets/391682ba-fe49-4209-8752-b47d1392b5cc" />


## RESULT:
Thus, the program to serialize a collection of objects into a file is written and executed successfully.
