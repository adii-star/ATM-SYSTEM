# ATM-SYSTEM
C program to build ATM system

#include <stdio.h>
int main() {
	int accountNo, pin, choice;
	char name[50];
	float balance = 5000.0, amount;
	printf("Enter Account Number: ");
	scanf("%d", &accountNo);
	printf("Enter Name: ");
	scanf("%s", name);
	printf("Enter PIN: ");
	scanf("%d", &pin);
	if(pin == 1234) {
    	printf("\n--- Welcome to ATM System ---\n");
    	printf("1. Check Balance\n");
    	printf("2. Deposit Money\n");
    	printf("3. Withdraw Money\n");
    	printf("Enter your choice: ");
    	scanf("%d", &choice);
    	if(choice == 1) {
        	printf("\nYour Current Balance is: ₹%.2f\n", balance);
    	}
    	else if(choice == 2) {
        	printf("Enter amount to deposit: ₹");
        	scanf("%f", &amount);
        	balance += amount;
        	printf("Deposit Successful! New Balance: ₹%.2f\n", balance);
    	}
    	else if(choice == 3) {
        	printf("Enter amount to withdraw: ₹");
        	scanf("%f", &amount);
        	if(amount <= balance) {
            	balance -= amount;
                printf("Withdrawal Successful! Remaining Balance: ₹%.2f\n", balance);
        	}
    	else {
                printf("Insufficient Balance!\n");
        	}
    	}
    	else {
        	printf("Invalid Choice!\n");
    	}
	}
	else {
    	printf("Incorrect PIN! Access Denied.\n");
	}
	return 0;
}


