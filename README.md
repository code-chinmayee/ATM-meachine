import java.util.Scanner;

public class ATM {
    public static void main(String[] args) {
        // Initialize variables
        double balance = 1000.00; // Initial balance
        int choice;
        double amount;
        Scanner scanner = new Scanner(System.in);

        System.out.println("Welcome to the ATM!");
        
        do {
            // Display menu
            System.out.println("\nATM Main Menu:");
            System.out.println("1. Check Balance");
            System.out.println("2. Deposit Money");
            System.out.println("3. Withdraw Money");
            System.out.println("4. Exit");
            System.out.print("Enter your choice: ");
            choice = scanner.nextInt();

            switch (choice) {
                case 1:
                    // Check balance
                    System.out.println("Your current balance is: $" + balance);
                    break;

                case 2:
                    // Deposit money
                    System.out.print("Enter the amount to deposit: ");
                    amount = scanner.nextDouble();
                    if (amount > 0) {
                        balance += amount;
                        System.out.println("Successfully deposited $" + amount);
                    } else {
                        System.out.println("Invalid amount. Please enter a positive value.");
                    }
                    break;

                case 3:
                    // Withdraw money
                    System.out.print("Enter the amount to withdraw: ");
                    amount = scanner.nextDouble();
                    if (amount > 0 && amount <= balance) {
                        balance -= amount;
                        System.out.println("Successfully withdrew $" + amount);
                    } else if (amount > balance) {
                        System.out.println("Insufficient balance.");
                    } else {
                        System.out.println("Invalid amount. Please enter a positive value.");
                    }
                    break;

                case 4:
                    // Exit
                    System.out.println("Thank you for using the ATM. Goodbye!");
                    break;

                default:
                    System.out.println("Invalid choice. Please select a valid option.");
            }
        } while (choice != 4);

        scanner.close();
    }
}
