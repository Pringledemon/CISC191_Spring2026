```java
public class Main
{
    public static int comparisons = 0;

    public static void merge(int [] numbers, int i, int j, int k)
    {
        int mergedSize = k - i + 1;
        int mergedNumbers [] = new int[mergedSize];
        int mergePos;
        int leftPos;
        int rightPos;

        mergePos = 0;
        leftPos = i;
        rightPos = j + 1;

        while (leftPos <= j && rightPos <= k)
        {
            if (numbers[leftPos] < numbers[rightPos])
            {
                mergedNumbers[mergePos] = numbers[leftPos];
                leftPos++;
                comparisons++;
            }
            else
            {
                mergedNumbers[mergePos] = numbers[rightPos];
                rightPos++;
                comparisons++;
            }
            mergePos++;
        }
        while (leftPos <= j)
        {
            mergedNumbers[mergePos] = numbers[leftPos];
            leftPos++;
            mergePos++;
        }
        while (rightPos <= k)
        {
            mergedNumbers[mergePos] = numbers[rightPos];
            rightPos++;
            mergePos++;
        }
        for (mergePos = 0; mergePos < mergedSize; ++mergePos)
        {
            numbers[i + mergePos] = mergedNumbers[mergePos];
        }
    }
    public static void mergeSort(int [] numbers, int i, int k)
    {
        int j;

        if (i < k)
        {
            j = (i + k) / 2;

            mergeSort(numbers, i, j);
            mergeSort(numbers, j + 1, k);

            merge(numbers, i, j, k);
        }
    }
    public static void main(String [] args)
    {
        int [] numbers = {4, 3, 2, 1};

        System.out.print("UNSORTED: ");
        for (int i = 0; i < numbers.length; i++)
        {
            System.out.print(numbers[i] + " ");
        }
        System.out.println("\n");

        mergeSort(numbers, 0, numbers.length - 1);

        System.out.print("SORTED: ");
        for (int i = 0; i < numbers.length; i++)
        {
            System.out.print(numbers[i] + " ");
        }
        System.out.println();
        System.out.println("comparisons: " + comparisons);
    }
}
```
