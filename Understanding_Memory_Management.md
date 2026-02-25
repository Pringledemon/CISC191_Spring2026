# Part 1
```java
public class MemoryTest1 {
    public static void main(String[] args) {
        int x = 10;
        String name = "Danish";
        Student s1 = new Student("Ali", 20);

        modify(x, s1);

        System.out.println("x = " + x);
        System.out.println("Student age = " + s1.age);
    }

    static void modify(int x, Student s) {
        x = 50;
        s.age = 99;
    }
}

class Student {
    String name;
    int age;

    Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```
### Questions
1. Stack
2. Stack
3. Heap
4. Because it is stored in stack
5. Because it is stored in heap
# Part 2
```java
public class MemoryTest2 {
    public static void main(String[] args) {
        Student s1 = new Student("Sara", 22);
        Student s2 = s1;

        s2.age = 30;

        System.out.println(s1.age);
    }
}
```
1. One object
2. Two references
3. Because they are referencing the same thing
# Part 3
```java
public class MemoryTest3 {
    public static void main(String[] args) {
        Student s1 = new Student("John", 18);
        Student s2 = new Student("Emma", 19);

        s1 = s2;
    }
}
```
### Questions 
1. Two objects
2. s1 object is eligible for garbage collection
3. Line 6
4. No, Java does not immediately delete it
# Part 4
```java
import java.util.ArrayList;

public class MemoryLeakExample {

    static ArrayList<Student> students = new ArrayList<>();

    public static void main(String[] args) {

        for(int i = 0; i < 100000; i++) {
            students.add(new Student("Student" + i, i));
        }

        System.out.println("Done creating students");
    }
}
```
### Questions
1. Because the ArrayList is static
2. I would remove the word static before the creation of the ArrayList students
##### modified
```java
import java.util.ArrayList;

public class MemoryLeakExample {

    ArrayList<Student> students = new ArrayList<>();

    public static void main(String[] args) {

        for(int i = 0; i < 100000; i++) {
            students.add(new Student("Student" + i, i));
        }

        System.out.println("Done creating students");
    }
}
```
# Part 5
```java
import java.util.ArrayList;

public class MemoryPressure {
    public static void main(String[] args) {

        ArrayList<int[]> list = new ArrayList<>();

        while(true) {
            list.add(new int[1000000]);
        }
    }
}
```
### Questions
1. java.lang.outOFMemoryError occurs
2. Because Java runs out of memory to allocate
3. -Xmx
# Part 6
### Questions
1. It's automated
2. Memory optimization
3. Gives direct control to the coder
4. Reference that can't be garbage collected
