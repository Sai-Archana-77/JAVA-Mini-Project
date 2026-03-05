## JAVA MINI PROJECT

## TITLE:Bank Account Simulator using Java Pogramming.

## SOURCE CODE:

```

import java.util.Scanner;

// BankAccount class
class BankAccount {

    private String accountHolder;
    private int accountNumber;
    private double balance;

    // Constructor
    BankAccount(String name, int accNo, double initialBalance) {
        accountHolder = name;
        accountNumber = accNo;
        balance = initialBalance;
    }

    // Deposit method
    public void deposit(double amount) {
        if (amount > 0) {
            balance = balance + amount;
            System.out.println("Amount Deposited: " + amount);
        } else {
            System.out.println("Invalid deposit amount.");
        }
    }

    // Withdraw method
    public void withdraw(double amount) {
        if (amount > balance) {
            System.out.println("Insufficient Balance.");
        } 
        else if (amount <= 0) {
            System.out.println("Invalid amount.");
        } 
        else {
            balance = balance - amount;
            System.out.println("Amount Withdrawn: " + amount);
        }
    }

    // Display account details
    public void displayAccount() {
        System.out.println("\nAccount Holder: " + accountHolder);
        System.out.println("Account Number: " + accountNumber);
        System.out.println("Current Balance: " + balance);
    }
}

// Main class
public class BankAccountSimulator {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.println("----- BANK ACCOUNT SIMULATOR -----");

        System.out.print("Enter Account Holder Name: ");
        String name = sc.nextLine();

        System.out.print("Enter Account Number: ");
        int accNo = sc.nextInt();

        System.out.print("Enter Initial Balance: ");
        double balance = sc.nextDouble();

        BankAccount account = new BankAccount(name, accNo, balance);

        int choice;

        do {
            System.out.println("\n1. Deposit");
            System.out.println("2. Withdraw");
            System.out.println("3. Check Balance");
            System.out.println("4. Exit");

            System.out.print("Enter your choice: ");
            choice = sc.nextInt();

            switch (choice) {

                case 1:
                    System.out.print("Enter amount to deposit: ");
                    double deposit = sc.nextDouble();
                    account.deposit(deposit);
                    break;

                case 2:
                    System.out.print("Enter amount to withdraw: ");
                    double withdraw = sc.nextDouble();
                    account.withdraw(withdraw);
                    break;

                case 3:
                    account.displayAccount();
                    break;

                case 4:
                    System.out.println("Thank you for using the Bank Simulator.");
                    break;

                default:
                    System.out.println("Invalid choice.");
            }

        } while (choice != 4);

        sc.close();
    }
}

```

## OUTPUT:

<img width="1366" height="768" alt="Mini Project output1" src="https://github.com/user-attachments/assets/c391aa84-e0a2-4f85-bca1-1909c002a1f5" />
<img width="1366" height="768" alt="Mini Project output2" src="https://github.com/user-attachments/assets/27829e85-eb0f-4e3b-b028-07148e5e9fb0" />
