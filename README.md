import java.util.Scanner;

public class ATM {
    public static void main(String[] args) {
        int balance = 5000; // Initial balance
        Scanner input = new Scanner(System.in);
        int option;

        while (true) {
            System.out.println("Automated Teller Machine");
            System.out.println("1. Check Balance");
            System.out.println("2. Deposit");
            System.out.println("3. Withdraw");
            System.out.println("4. Quit");
            System.out.print("Choose the operation you want to perform: ");
            option = input.nextInt();

            switch (option) {
                case 1:
                    System.out.println("Your balance is: " + balance);
                    break;
                case 2:
                    System.out.print("Enter amount to deposit: ");
                    int depositAmount = input.nextInt();
                    balance += depositAmount;
                    System.out.println("Amount deposited successfully. Your new balance is: " + balance);
                    break;
                case 3:
                    System.out.print("Enter amount to withdraw: ");
                    int withdrawAmount = input.nextInt();
                    if (withdrawAmount > balance) {
                        System.out.println("Insufficient balance");
                    } else {
                        balance -= withdrawAmount;
                        System.out.println("Amount withdrawn successfully. Your new balance is: " + balance);
                    }
                    break;
                case 4:
                    System.out.println("Thank you for using the ATM. Goodbye!");
                    System.exit(0);
                default:
                    System.out.println("Invalid option. Please try again.");
            }
        }
    }
}
