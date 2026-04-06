```java
import static java.util.Collections.swap;

public class Main
{
    public static void insertionSort(int[] numbers)
    {
        int temp;
        int comparisons = 0;
        int swaps = 0;

        for (int number : numbers)
        {
            System.out.print(number + " ");
        }
        System.out.println("\n");
        for (int i = 1; i < numbers.length; i++)
        {
            int j = i;

            while (j > 0)
            {
                comparisons++;
                if (numbers[j] < numbers[j - 1])
                {
                    temp = numbers[j];
                    numbers[j] = numbers[j - 1];
                    numbers[j - 1] = temp;
                    swaps++;
                }
                else
                    break;
                j--;
            }
            for (int number : numbers)
            {
                System.out.print(number + " ");
            }
            System.out.print("\n");
        }
        System.out.println("\ncomparisons: " + comparisons + "\nswaps: " + swaps);
    }

    public static void main(String [] args)
    {
        int [] numbers = {3, 2, 1, 9, 5, 8};

        insertionSort(numbers);
    }
}
```
