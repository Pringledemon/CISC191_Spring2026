```java
import java.util.HashMap;
import java.util.Scanner;

public class Main
{
    public static HashMap<String, Integer> permute(String word)
    {

        HashMap<String, Integer> check = new HashMap<>();
        if(word.length() == 1)
        {
            check.put(word, 1);
        }
        else
        {
            for(int i = 0; i < word.length(); i++)
            {
                String pre = word.substring(0, i);
                String post = word.substring(i+1);
                String remaining = pre + post;

                for (String key : permute(remaining).keySet() )
                {
                    check.put(word.charAt(i) + key, i);
                }
            }
        }
        return check;
    }
    public static void main(String[] args)
    {
        Scanner scan = new Scanner(System.in);

        System.out.print("Enter a word: ");
        String word = scan.nextLine();

        for (String key : permute(word).keySet() )
        {
            if(!key.equals(word))
                System.out.println(key);
        }
    }
}
```
