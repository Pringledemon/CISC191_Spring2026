# Code
```java
public class Main
{
    public static void main(String[] args)
    {
        int age = 18;
        String name = "Peter";

        System.out.println("Hello " + name + " you are " + age + " years old, and you'll be " + (age+1) + " years old next year");
    }
}
```
# Stack
| Reference | Contains | Variable |
| :-------: | :------: | :------: |
| 000100 | 18 | age |
# Heap
| Reference | Contains | Variable |
| :-------: | :------- | :------: |
| 010000 | Peter | name |
