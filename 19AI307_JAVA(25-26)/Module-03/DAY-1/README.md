# Ex.No:3(A) INHERITANCE AND AGGREGATION

## QUESTION:
A jewelry store tracks gold rates for different types of customers. The base class is Customer with attributes like customerId, name, and purchaseWeight (in grams). There are two types of customers: RegularCustomer and PremiumCustomer. RegularCustomer gets a fixed discount of 2% on the gold rate per gram. PremiumCustomer gets a 5% discount plus a special cashback. The base gold rate per gram is input at runtime. For each customer, calculate the final price they pay:

       
       
      finalPrice = purchaseWeight * (goldRatePerGram - discount)


For PremiumCustomer, additionally show cashback amount (which is 1% of the final price).

## AIM:
To build an inheritance-based Java program that calculates the final price of gold for different types of customers (Regular and Premium), applying respective discounts and showing cashback for premium customers.

## ALGORITHM :
1. Create a base class Customer with attributes: customerId, name, purchaseWeight, and goldRatePerGram.

2. Create method getDiscountRate() in base class returning 0 (default).

3. Create method calculateFinalPrice() that:

        calculates discount per gram → discountAmount = goldRatePerGram * (discountRate/100)

        calculates effective rate → effectiveRate = goldRatePerGram - discountAmount

  returns → finalPrice = purchaseWeight * effectiveRate

4. Override display() in base class to show general customer details.

5. Create child class RegularCustomer:

       Override getDiscountRate() to return 2%.

       Override display() to show customer type as Regular.

6. Create child class PremiumCustomer:






## PROGRAM:
 ```
/*
Program to implement a Inheritance and Aggregation using Java
Developed by: HARSHIDA K S
RegisterNumber:  212224040108
*/
```

## SOURCE CODE:
```java
    double calculateCashback() {
        return calculateFinalPrice() * 0.01;
    }

    @Override
    void display() {
        DecimalFormat df = new DecimalFormat("0.00");
        System.out.println("Customer ID: " + customerId);
        System.out.println("Name: " + name);
        System.out.println("Customer Type: Premium");
        System.out.println("Purchase Weight: " + purchaseWeight + " grams");
        System.out.println("Gold Rate per Gram: " + goldRatePerGram);
        System.out.println("Discount: 5%");
        System.out.println("Final Price: " + df.format(calculateFinalPrice()));
        System.out.println("Cashback: " + df.format(calculateCashback()));
        
    }
}

public class GoldRateSystem {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // Input 1
        String type1 = sc.next();
        Customer cust1;
        if (type1.equalsIgnoreCase("Regular")) {
            cust1 = new RegularCustomer(sc.next(), sc.next(), sc.nextDouble(), sc.nextDouble());
        } else {
            cust1 = new PremiumCustomer(sc.next(), sc.next(), sc.nextDouble(), sc.nextDouble());
        }

        
        cust1.display();
     

        sc.close();
    }
}
```


## OUTPUT:

<img width="884" height="700" alt="image" src="https://github.com/user-attachments/assets/bc4bc233-2418-404a-88cc-490c1d83bc24" />

## RESULT:

Therefore the program successfully applies different discount rules for regular and premium customers.
