# COP-2334-1-Module-5-Programming-Group-Assignment
This is a GitHub repository link for the Programming Group Assignment from Module 5.

/libraries used in order to set precision and output and input
#include <iostream>
#include <iomanip>

int main(){
    //namespace
    using namespace std;

    //declaration of variables
    float balance, annualInterestRate, deposit, withdrawal;
    int months;

    //user prompts
    cout << "Please enter the balance of your account\n";
    cin >> balance;
    cout << "Please enter your annual interest rate as a percentage\n";
    cin >> annualInterestRate;
    annualInterestRate /= 100;
    cout << "Please enter the amount of months that have passed\n";
    cin >> months;

    cout << "You will now be prompted to enter more information for each month\n\n";

    //for loop with nested conditionals to avoid inputs < 0 (Negatives)
    //there are also some formatting things included to make it look pretty
    for(int i=0; i<months; i++){
        cout << "*** Month " << i + 1 << " ***\n\n";
        cout << "Please enter the amount deposited this month\n";
        cin >> deposit;
        while(deposit < 0){
            cout << "Please input a valid amount\n";
            cin >> deposit;
        }
        cout << "Please enter the amount withdrawn this month\n";
        cin >> withdrawal;
        while(withdrawal < 0){
            cout << "Please input a valid amount\n";
            cin >> withdrawal;
        }
        balance += deposit;
        balance -= withdrawal;

        balance+= (annualInterestRate / 12) * balance;

        cout << "\n";

    }

    //final output of balance
    cout << "Your balance post interest calculation is: $" << fixed << setprecision(2) << balance;

}
