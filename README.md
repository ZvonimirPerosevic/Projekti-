public class Customer {
    private String customerName;
    private String accountNumber;
    private double balance;

    
    public Customer(String customerName, String accountNumber, double balance) {
        this.customerName = customerName;
        this.accountNumber = accountNumber;
        this.balance = balance;
    }

    
    public void deposit(double amount) {
        if (amount > 0) {
            this.balance += amount;
            System.out.printf("Deposited $%.2f. New balance: $%.2f%n", amount, this.balance);
        } else {
            System.out.println("Error: Invalid deposit amount. Deposit amount must be a positive value.");
        }
    }

   
    public void withdraw(double amount) {
        if (amount > 0 && amount <= this.balance) {
            this.balance -= amount;
            System.out.printf("Withdrew $%.2f. New balance: $%.2f%n", amount, this.balance);
        } else if (amount <= 0) {
            System.out.println("Error: Invalid withdrawal amount. Withdrawal amount must be a positive value.");
        } else {
            System.out.println("Error: Insufficient funds for withdrawal.");
        }
    }

    
    public void displayAccountInfo() {
        System.out.printf("Account Information:%nAccount Number: %s%nAccount Holder: %s%nBalance: $%.2f%n",
                this.accountNumber, this.customerName, this.balance);
    }

    
    public static void main(String[] args) {
        
        Customer customer1 = new Customer("John Doe", "123456789", 0.0);

        
        customer1.deposit(1000.0);
        customer1.withdraw(500.0);
        customer1.deposit(200.0);

        
        customer1.displayAccountInfo();
    }
}
