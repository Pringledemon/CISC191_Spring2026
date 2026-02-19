# Part 1
```java
ArrayList<Integer> scores = new ArrayList<>();

        scores.add(85);
        scores.add(92);
        scores.add(78);
        scores.add(90);
        scores.add(88);

        System.out.print("Scores: ");
        for(int score: scores)
        {
            System.out.print(score + " ");
        }
        System.out.println("\nSize: " + scores.size());
```
### Concept Check Answers
- Arraylist doesn't have a set size while arrays have set size
- Arraylist cannot store primitive data types directly
# Part 2
```java
for(int i = 0; i < scores.size(); i++)
        {
            System.out.print(scores.get(i) + " ");
        }
        System.out.print("\n");
        for(int score: scores)
        {
            System.out.print(score + " ");
        }
        System.out.print("\n");
        scores.forEach(score -> System.out.print(score + " "));
```
### Discussion Question Answers
-The traditional for loop traversal method gives direct access to the index. It matters because it allows me to directly access a specific thing the array
# Part 3
```java
scores.set(scores.indexOf(78), 80);
        scores.remove(Integer.valueOf(92));

        System.out.println("\n" + scores);
```
### Answers
-The indexes of everything after the number removed decreases by one
-O(n)
# Part 4
```java
public static int linearSearch(ArrayList<Integer> list, int find)
    {
        for (int i = 0; i < list.size(); i++)
        {
            if (list.get(i) == find)
            {
                return i;
            }
        }
        return -1;
    }
```
### Answers
-I don't know
# Part 5
```java
scores.add(0, 95);
scores.add(2, 70);
scores.add(100);

System.out.println(scores);
```
# Part 6
```java
import java.util.ArrayList;
import java.util.Scanner;

public class StudentManager
{
    public static void main(String[] args)
    {
        Scanner scanner = new Scanner(System.in);
        ArrayList<String> students = new ArrayList<>();
        int num;

        do
        {
            System.out.println("\n1. Add Student");
            System.out.println("2. Remove Student");
            System.out.println("3. Search Student");
            System.out.println("4. Display All");
            System.out.println("5. Exit");
            System.out.print("Choice: ");
            num = scanner.nextInt();
            scanner.nextLine();

            switch (num)
            {
                case 1:
                    System.out.print("Enter name: ");
                    students.add(scanner.nextLine());
                    break;
                case 2:
                    System.out.print("Enter name to remove: ");
                    students.remove(scanner.nextLine());
                    break;
                case 3:
                    System.out.print("Enter name to search: ");
                    String name = scanner.nextLine();
                    if (students.contains(name))
                        System.out.println("Student found.");
                    else
                        System.out.println("Student not found.");
                    break;
                case 4:
                    System.out.println("Students: " + students);
                    break;
            }
        }
        while(num != 5);
        {
            scanner.close();
        }
    }
}
```
