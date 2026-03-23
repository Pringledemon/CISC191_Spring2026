# Version 1.0
### Parent Class
```java
public class Item
{
    private String itemName, companyName;

    Item()
    {
    }
    Item(String itemName, String companyName)
    {
        this.itemName = itemName;
        this.companyName = companyName;
    }
    void updateAll(String itemName, String companyName)
    {
        this.itemName = itemName;
        this.companyName = companyName;
    }
    void updateItemName(String itemName)
    {
        this.itemName = itemName;
    }
    void updatecompanyName(String companyName)
    {
        this.companyName = companyName;
    }
    String displayItemName()
    {
        return itemName;
    }
    String displayCompanyName()
    {
        return companyName;
    }
    String displayAll()
    {
        return "Item Name: " + this.itemName + ", Company Name: " + companyName;
    }
}
```
### PainKillers Class
```java
public class PainKillers extends Item
{
        private String expiryDate, ageGroup;

        PainKillers()
        {
        }
        PainKillers(String itemName, String companyName, String expiryDate, String ageGroup)
        {
            super(itemName, companyName);
            this.expiryDate = expiryDate;
            this.ageGroup = ageGroup;
        }
        void updateAll(String itemName, String companyName, String expiryDate, String ageGroup)
        {
            super.updateAll(itemName, companyName);
            this.expiryDate = expiryDate;
            this.ageGroup = ageGroup;
        }
        void updateExpiryDate(String expiryDate)
        {
            this.expiryDate = expiryDate;
        }
        void updateAgeGroup(String ageGroup)
        {
            this.ageGroup = ageGroup;
        }
        String displayExpiryDate()
        {
            return expiryDate;
        }
        String displayAgeGroup()
        {
            return ageGroup;
        }
        String displayAll()
        {
            return super.displayAll() + ", Expiry Date: " + expiryDate + ", Age Group: " + ageGroup;
        }
}
```
### Bandage Class
```java
public class Bandage extends Item
{
    private String expiryDate, ageGroup;
    private boolean waterProof;

    Bandage()
    {
    }
    Bandage(String itemName, String companyName, String expiryDate, String ageGroup, boolean waterProof)
    {
        super(itemName, companyName);
        this.expiryDate = expiryDate;
        this.ageGroup = ageGroup;
        this.waterProof = waterProof;
    }
    void updateAll(String itemName, String companyName, String expiryDate, String ageGroup, boolean waterProof)
    {
        super.updateAll(itemName, companyName);
        this.expiryDate = expiryDate;
        this.ageGroup = ageGroup;
        this.waterProof = waterProof;
    }
    void updateExpiryDate(String expiryDate)
    {
        this.expiryDate = expiryDate;
    }
    void updateAgeGroup(String ageGroup)
    {
        this.ageGroup = ageGroup;
    }
    void updateWaterProof(boolean waterProof)
    {
        this.waterProof = waterProof;
    }
    String displayExpiryDate()
    {
        return expiryDate;
    }
    String displayAgeGroup()
    {
        return ageGroup;
    }
    boolean displayWaterProof()
    {
        return waterProof;
    }
    String displayAll()
    {
        return super.displayAll() + ", Expiry Date: " + expiryDate + ", Age Group: " + ageGroup + "Water Proof (True/False): " + waterProof;
    }
}
```
### Equipment Class
```java
public class Equipment extends Item
{
    private double weight;

    Equipment()
    {
    }
    Equipment(String itemName, String companyName, double weight)
    {
        super(itemName, companyName);
        this.weight = weight;
    }
    void updateAll(String itemName, String companyName, double weight)
    {
        super.updateAll(itemName, companyName);
        this.weight = weight;
    }
    void updateWeight(double weight)
    {
        this.weight = weight;
    }
    double displayWeight()
    {
        return weight;
    }
    String displayAll()
    {
        return super.displayAll() + ", Weight: " + weight;
    }
}

```
# Version 2.0
### Main Class
```java
import java.util.InputMismatchException;
import java.util.Scanner;

public class Main
{

    public static void main(String[] args)
    {
        Scanner scan = new Scanner(System.in);
        String section;

        try
        {
            do
            {
                System.out.print("Enter Section(PainKillers, Bandage, Equipment, Exit): ");
                section = scan.nextLine();

                switch (section)
                {
                    case "PainKillers":
                        System.out.print("Enter Item Name: ");
                        String itemNameP = scan.nextLine();
                        System.out.print("Enter Company Name: ");
                        String companyNameP = scan.nextLine();
                        System.out.print("Enter Expiry Date: ");
                        String ExpiryDateP = scan.nextLine();
                        System.out.print("Enter Age Group: ");
                        String AgeGroupP = scan.nextLine();
                        PainKillers painKiller = new PainKillers(itemNameP, companyNameP, ExpiryDateP, AgeGroupP);
                        break;
                    case "Bandage":
                        System.out.print("Enter Item Name: ");
                        String itemNameB = scan.nextLine();
                        System.out.print("Enter Company Name: ");
                        String companyNameB = scan.nextLine();
                        System.out.print("Enter Expiry Date: ");
                        String ExpiryDateB = scan.nextLine();
                        System.out.print("Enter Age Group: ");
                        String AgeGroupB = scan.nextLine();
                        System.out.print("Water Proof(T/F): ");
                        boolean WaterProofB = scan.nextBoolean();
                        Bandage bandage = new Bandage(itemNameB, companyNameB, ExpiryDateB, AgeGroupB, WaterProofB);
                        break;
                    case "Equipment":
                        System.out.print("Enter Item Name: ");
                        String itemNameE = scan.nextLine();
                        System.out.print("Enter Company Name: ");
                        String companyNameE = scan.nextLine();
                        System.out.print("Enter Weight(lbs): ");
                        double weightE = scan.nextDouble();
                        Equipment equipment = new Equipment(itemNameE, companyNameE, weightE);
                        break;
                    case "Exit":
                        break;
                    default:
                        System.out.println("Please enter a valid choice");
                        break;
                }
            }
            while (!section.equals("Exit"));
            {
                scan.close();
            }
        }
        catch(InputMismatchException e)
        {
            System.out.println("Enter Valid Input");
        }
    }
}
```
# Version 3.0
### Main Class
```java
import java.util.InputMismatchException;
import java.util.Scanner;

public class Main
{

    public static void main(String[] args)
    {
        Scanner scan = new Scanner(System.in);
        String section;

        try
        {
            do
            {
                System.out.print("Enter Section(PainKillers, Bandage, Equipment, Exit): ");
                section = scan.nextLine();

                switch (section)
                {
                    case "PainKillers":
                        System.out.print("Enter Item Name: ");
                        String itemNameP = scan.nextLine();
                        System.out.print("Enter Company Name: ");
                        String companyNameP = scan.nextLine();
                        System.out.print("Enter Expiry Date: ");
                        String ExpiryDateP = scan.nextLine();
                        System.out.print("Enter Age Group: ");
                        String AgeGroupP = scan.nextLine();
                        PainKillers painKiller = new PainKillers(itemNameP, companyNameP, ExpiryDateP, AgeGroupP);
                        break;
                    case "Bandage":
                        System.out.print("Enter Item Name: ");
                        String itemNameB = scan.nextLine();
                        System.out.print("Enter Company Name: ");
                        String companyNameB = scan.nextLine();
                        System.out.print("Enter Expiry Date: ");
                        String ExpiryDateB = scan.nextLine();
                        System.out.print("Enter Age Group: ");
                        String AgeGroupB = scan.nextLine();
                        System.out.print("Water Proof(T/F): ");
                        boolean WaterProofB = scan.nextBoolean();
                        Bandage bandage = new Bandage(itemNameB, companyNameB, ExpiryDateB, AgeGroupB, WaterProofB);
                        break;
                    case "Equipment":
                        System.out.print("Enter Item Name: ");
                        String itemNameE = scan.nextLine();
                        System.out.print("Enter Company Name: ");
                        String companyNameE = scan.nextLine();
                        System.out.print("Enter Weight(lbs): ");
                        double weightE = scan.nextDouble();
                        if(weightE < 0.0)
                        {
                            throw new NegativeWeight();
                        }
                        Equipment equipment = new Equipment(itemNameE, companyNameE, weightE);
                        break;
                    case "Exit":
                        break;
                    default:
                        System.out.println("Please enter a valid choice");
                        break;
                }
            }
            while (!section.equals("Exit"));
            {
                scan.close();
            }
        }
        catch(InputMismatchException e)
        {
            System.out.println("Enter Valid Input");
        }
        catch(NegativeWeight e)
        {
            System.out.println("Enter Non-Negative Weight");
        }
    }
}
```
### Custom Exception
```java
public class NegativeWeight extends Exception
{
    NegativeWeight()
    {
    }
}
```
