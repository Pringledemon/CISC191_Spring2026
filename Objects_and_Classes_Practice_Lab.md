# Part 1
```java
public class Student
{
    private String name;
    private int age;
    private double gpa;

    Student(String name, int age, double gpa)
    {
        this.name = name;
        this.age = age;
        this.gpa = gpa;
    }
    public String getName()
    {
        return name;
    }
    public void setName(String name)
    {
        this.name = name;
    }
    public int getAge()
    {
        return age;
    }
    public void setAge(int age)
    {
        this.age = age;
    }
    public double getGpa()
    {
        return gpa;
    }
    public void setGpa(double gpa)
    {
        this.gpa = gpa;
    }
    public void displayInfo()
    {
        System.out.println("Name: " + name + " Age: " + age + " Gpa: " + gpa);
    }
    public String toString()
    {
        return "Student{name: " + name + "', age: " + age + ", gpa: " + gpa + "}";
    }
}
```
# Part 2
```java
public class Main
{
    public static void main(String[] args)
    {

        Student s1 = new Student("Alice", 20, 3.8);
        s1.displayInfo();

        s1.setGpa(3.9);
        System.out.println(s1);

        Student s2 = s1;
        s2.setName("Bob");

        System.out.println("s1: " + s1);
        System.out.println("s2: " + s2);
    }
}
```
# Part 3
```java
import java.util.ArrayList;

public class Main
{

    public static void main(String[] args)
    {

        ArrayList<Student> students = new ArrayList<>();

        students.add(new Student("Alice", 24, 3.7));
        students.add(new Student("Bob", 21, 3.1));
        students.add(new Student("James", 22, 4.5));
        
        for (int i = 0; i < students.size(); i++)
        {
            System.out.println(students.get(i));
        }
        for (Student stu : students)
        {
            System.out.println(stu);
        }
    }
}
```
# Part 4
```java
public class BankAccount
{
    private String accountHolder;
    private double balance;
    private static int totalAccounts = 0;

    public BankAccount(String accountHolder, double balance)
    {
        this.accountHolder = accountHolder;
        this.balance = balance;
        totalAccounts++;
    }
    public void deposit(double amount)
    {
        if (amount > 0)
        {
            balance += amount;
            System.out.println("Deposit successful.");
        }
    }
    public void withdraw(double amount)
    {
        if (amount > balance)
        {
            System.out.println("Insufficient funds.");
        }
        else
        {
            balance -= amount;
            System.out.println("Withdrawal successful.");
        }
    }
    public double getBalance()
    {
        return balance;
    }
    public static int getTotalAccounts()
    {
        return totalAccounts;
    }
    public String toString() 
    {
        return "BankAccount{holder: " + accountHolder + ", balance: " + balance + "}";
    }
}
```
# Part 6
1. A class is a blueprint, and an object is an instance of the blueprint
2. Objects are stored in heap memory
3. The new word allocates memory
4. Encapsulation is important because it protects the internal state
5. toString() provides meaningful object representation when printed
