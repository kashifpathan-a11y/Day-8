# Day-8
#include <stdio.h>

int main() {
    int choice;
    float balance = 10000.0; 
    float amount;
    
    printf("===== Welcome to Simple Bank System =====\n");


    do {
        
        printf("\n******** MENU ********\n");
        printf("1. Deposit Money\n");
        printf("2. Withdraw Money\n");
        printf("3. Check Balance\n");
        printf("4. Exit\n");
        printf("Enter your choice (1-4): ");
        scanf("%d", &choice);

        switch(choice) {
            case 1:
                
                printf("Enter amount to deposit: ₹");
                scanf("%f", &amount);

                if (amount > 0) {
                    
                    if (amount > 25000) {
                        float bonus = amount * 0.01; 
                        printf("You earned a bonus of ₹%.2f!\n", bonus);
                        amount += bonus;
                    }
                    balance += amount;
                    balance -= 5; 
                    printf("₹5 service charge applied.\n");
                    printf("Deposit successful! New balance: ₹%.2f\n", balance);
                } else {
                    printf("Invalid amount! Please enter a positive value.\n");
                }
                break;

            case 2:
                
                printf("Enter amount to withdraw: ₹");
                scanf("%f", &amount);

                if (amount > 0) {
                    if (amount > balance) {
                        printf(" Insufficient balance! Withdrawal denied.\n");
                    } else {
                        balance -= amount;
                        balance -= 5; 
                        printf("₹5 service charge applied.\n");
                        printf("Withdrawal successful! New balance: ₹%.2f\n", balance);
                    }
                } else {
                    printf("Invalid amount! Please enter a positive value.\n");
                }
                break;

            case 3:
                
                printf("Your current balance is: ₹%.2f\n", balance);
                break;

            case 4:
                
                printf("Thank you for using Simple Bank System. Goodbye!\n");
                break;

            default:
                printf("Invalid choice! Please select 1–4.\n");
        }

    } while (choice != 4);

    return 0;
}
