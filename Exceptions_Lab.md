Exception Class
```java
public class NegativeSteps extends Exception
{
    public NegativeSteps(String message)
    {
        super(message);
    }
}
```
Main
```java
import java.util.Scanner;

public class Main
{
    public static Double stepsToMiles(int Steps) throws NegativeSteps
    {
        if (Steps < 0.0)
        {
            throw new NegativeSteps("Exception: Negative step count entered.");
        }
        return (double)(Steps/2000.0);
    }
    public static void main(String[] args)
    {
        Scanner scan = new Scanner(System.in);

        System.out.print("Enter amount of steps: ");
        int Steps = scan.nextInt();
        try
        {
            double miles = stepsToMiles(Steps);
            System.out.printf("%.2f", miles);
        }
        catch (NegativeSteps e)
        {
            System.out.print(e.getMessage());
        }
    }
}

```
