# Ex.No:4(D) DESIGN PATTERN  ---- BEHAVIOUR PATTERN

## QUESTION:
Write a DAO class for a Contact model with fields like name and phone. Implement a method to return all contacts starting with a specific letter.

## AIM:
To write a Java program that provides a DAO for managing contacts and retrieving all contacts whose names start with a specified letter.


## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read the number of contacts and create a ContactDAO object.
4.	For each contact, read its name and phone number, then add it to the DAO using addContact().
5.	Read the input letter used for filtering.
6.	Call getContactsStartingWith(letter) to retrieve all contacts whose names start with the given letter.
7.	Traverse the returned list and print the name and phone of each matching contact.
8.	End the program.


## PROGRAM:

```
Program to implement a Behaviour Pattern using Java
Developed by: Roshini R K
RegisterNumber: 212222230123
```

## SOURCE CODE:

```
import java.util.*;

class Contact 
{
    private String name;
    private String phone;

    public Contact(String name, String phone) 
    {
        this.name = name;
        this.phone = phone;
    }
    public String getName() 
    {
        return name;
    }
    public String getPhone() 
    {
        return phone;
    }
}

interface ContactDAO 
{
    void addContact(Contact contact);
    List<Contact> getContactsStartingWith(char letter);
}

class ContactDAOImpl implements ContactDAO 
{
    private List<Contact> contactList = new ArrayList<>();

    public void addContact(Contact contact) 
    {
        contactList.add(contact);
    }
    public List<Contact> getContactsStartingWith(char letter) 
    {
        List<Contact> result = new ArrayList<>();
        for (Contact c : contactList) 
        {
            if (Character.toLowerCase(c.getName().charAt(0)) == Character.toLowerCase(letter)) {
                result.add(c);
            }
        }
        return result;
    }
}

public class ContactManager 
{
    public static void main(String[] args) 
    {
        Scanner sc = new Scanner(System.in);
        ContactDAO dao = new ContactDAOImpl();
        int n = sc.nextInt();
        sc.nextLine(); 

        for (int i = 0; i < n; i++) 
        {
            String name = sc.nextLine();
            String phone = sc.nextLine();
            dao.addContact(new Contact(name, phone));
        }
        char letter = sc.next().charAt(0);
        List<Contact> filteredContacts = dao.getContactsStartingWith(letter);
        
        for (Contact c : filteredContacts) 
        {
            System.out.println(c.getName());
            System.out.println(c.getPhone());
        }
        sc.close();
    }
}
```


## OUTPUT:

<img width="472" height="824" alt="image" src="https://github.com/user-attachments/assets/1ad7d8d2-922b-4187-96b5-0b5330764624" />


## RESULT:
Thus, the program that provides a DAO for managing contacts and retrieving all contacts whose names start with a specified letter is written and executed successfully.
