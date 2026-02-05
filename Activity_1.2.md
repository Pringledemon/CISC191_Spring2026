```java
import java.util.Scanner;

public class Main
{
    public static void main(String[] args)
    {
        Scanner input = new Scanner(System.in);
        //Part 1
        int days;
        System.out.print("Enter number of days: ");
        days = input.nextInt();
        double sum = 0;
        double[] tempsUnsorted = new double[days];
        for(int i = 0; i < days; i++)
        {
            System.out.print("Enter temperature for day " + (i+1) + ": ");
            tempsUnsorted[i] = input.nextDouble();
            sum += tempsUnsorted[i];
        }
        //Part 2
        double mean = sum/days;
        //Part 3
        double[] tempsSorted = tempsUnsorted.clone();
        for(int i = 0; i < tempsSorted.length-1; i++)
        {
            for(int j = i+1; j < tempsSorted.length; j++)
            {
                if(tempsSorted[i] > tempsSorted[j])
                {
                    double temp = tempsSorted[i];
                    tempsSorted[i] = tempsSorted[j];
                    tempsSorted[j] = temp;
                }
            }
        }
        System.out.print("\nSorted Temperatures: ");
        for(double temperature : tempsSorted)
        {
            System.out.print(temperature + " ");
        }
        System.out.println("\n\nMean: " + mean);
        //Part 4
        double median;
        if(tempsSorted.length%2 == 1)
            median = tempsSorted[tempsSorted.length/2];
        else
            median = ((tempsSorted[tempsSorted.length/2] + tempsSorted[(tempsSorted.length/2)-1]))/2;
        System.out.println("Median: " + median);
        //Part 5
        double range = tempsSorted[tempsSorted.length-1] - tempsSorted[0];
        System.out.println("Range: " + range);
        //Part 6
        double preVariance = 0;
        for (double x : tempsSorted)
        {
            preVariance += Math.pow((x-mean), 2);
        }
        double variance = preVariance/tempsSorted.length;
        System.out.println("Variance: " + variance);
        //Part 7
        double standardDeviation = Math.sqrt(variance);
        System.out.println("Standard Deviation: " + standardDeviation);
        //Part 8
        if(standardDeviation < 2)
            System.out.println("\nTemperatures are very consistent");
        else if(standardDeviation < 5)
            System.out.println("\nTemperatures show moderate variation");
        else
            System.out.println("\nTemperatures vary significantly");
    }
}
```
