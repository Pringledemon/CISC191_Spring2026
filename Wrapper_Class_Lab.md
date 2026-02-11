```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        //1.1
        int num1 = 5;
        Integer num2 = Integer.valueOf(num1);
        System.out.println(num1 + "\n" + num2 + "\n");
        //1.2
        Integer num3 = 10;
        int num4 = num3;
        System.out.println(num3 + "\n" + num4 + "\n");
        //Reflection
        //  1. Wrapper types have methods and can hold null while primitive don't have methods and can't hold null.
        //  2. Autoboxing happens when a primitive is directly assigned to a wrapper.
        //2.1
        String num5 = "123";
        Integer num6 = Integer.parseInt(num5);
        System.out.println(num6 + 10 + "\n");
        //2.2
        System.out.println(Integer.MAX_VALUE + "\n" + Integer.MIN_VALUE + "\n");
        //Reflection
        //The constants are useful because its useful to know limits also the two methods help with readability of programming
        //3
        ArrayList<Integer> list = new ArrayList<>();
        list.add(1);
        list.add(4);
        list.add(5);
        int total = 0;
        for (Integer integer : list)
        {
            total += integer;
        }
        System.out.println(total + "\n");
        //Reflection
        //We can't use ArrayList<int> because ArrayList only accepts objects and int is a primitive type
        //4
        Character let = 'a';
        System.out.println(Character.isUpperCase(let));
        System.out.println(Character.isDigit(let));
        System.out.println(Character.isLetter(let));
    }
}
```
