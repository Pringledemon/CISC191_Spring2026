```java
import java.util.LinkedList;
import java.util.Deque;
import java.util.Scanner;

public class Main
{
    public static void main(String[] args)
    {
        Deque<Character> pali = new LinkedList<Character>();
        Scanner scan = new Scanner(System.in);
        boolean flag = true;

        System.out.print("Enter word: ");
        String temp = scan.nextLine();
        for(int i = 0; i < temp.length(); i++)
        {
            pali.add(temp.charAt(i));
        }
        for(int i = 0; i < temp.length()/2; i++)
        {
            if(pali.pollFirst() != pali.pollLast())
            {
                flag = false;
                break;
            }
        }
        if(flag)
            System.out.println("Yes, " + temp + " is a palindrome.");
        else
            System.out.println("No, " + temp + " is not a palindrome.");
    }
}
```
