# Ex.No:4(C)  COMPOSITION IN JAVA

## QUESTION:
A student can enroll in multiple courses. The relationship is many-to-many via association.
If No Courses were assigned, print "No courses enrolled." 

## AIM:
To develop a Java program that models a many-to-many student–course association and displays “No courses enrolled” when no courses are assigned.


## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read the student's name and create a Student object.
4.	Read the number of courses the student wants to enroll in.
5.	For each course, read the course name and create a Course object.
6.	Enroll each created course into the student using student.enroll().
7.	After all inputs, call student.showCourses() to display enrolled courses.
8.	If no courses were added, print "No courses enrolled."
9.	End the program.


## PROGRAM:

```
Program to implement a Composition Concepts in Java
Developed by: Sathyaa R
RegisterNumber: 212223100052
```

## SOURCE CODE:

```
import java.util.*;

public class AssociationExample 
{
    public static void main(String[] args) 
    {
        Scanner sc = new Scanner(System.in);
        String studentName = sc.nextLine();
        Student student = new Student(studentName);

        int n = sc.nextInt();
        sc.nextLine();

        for (int i = 0; i < n; i++) 
        {
            String course = sc.nextLine();
            student.enroll(new Course(course));
        }
        student.showCourses();
        sc.close();
    }
}

class Course 
{
    private String name;
    public Course(String name) 
    {
        this.name = name;
    }
    public String getCourseName() 
    {
        return name;
    }
}

class Student 
{
    private String name;
    private List<Course> courses;

    public Student(String name) 
    {
        this.name = name;
        this.courses = new ArrayList<>();
    }
    public void enroll(Course c) 
    {
        courses.add(c);
    }

    public void showCourses() 
    {
        if (courses.isEmpty()) 
        {
            System.out.println(name + "'s enrolled courses:");
            System.out.println("No courses enrolled.");
        } 
        else 
        {
            System.out.println(name + "'s enrolled courses:");
            for (Course c : courses) 
            {
                System.out.println("- " + c.getCourseName());
            }
        }
    }
}
```


## OUTPUT:

<img width="762" height="295" alt="image" src="https://github.com/user-attachments/assets/ea07feac-835c-4789-80c7-e06029d41e03" />


## RESULT:
Thus, the program that models a many-to-many student–course association and displays “No courses enrolled” when no courses are assigned is written and executed successfully.
