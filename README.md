#include <iostream>
#include <iomanip>
using namespace std;
class ATM{
private:
    double money;
public:
    ATM()
    {
        money=0;
    }
    void Deposit()
    {
        double x;
        cout<<"Enter the amount of money: ";
        cin>>x;
        if (x<0)
            cout<<"Error: Please enter a positive amount."<<endl;
        else
        {
            money+=x;
            cout<<"(The operation was completed successfully)"<<endl;
        }

    }
    void withdraw()
    {
        double x;
        cout<<"Enter the amount of money: ";
        cin>>x;

        if(x<0)
            cout<<"Error: Please enter a positive amount."<<endl;
        else if  (money<x)
        {
            cout<<"Error your money is less then that amount."<<endl;
        }
        else
        {
            money-=x;
            cout<<"(The operation was completed successfully)"<<endl;
        }
    }
    void displayMoney()
    {
        cout << fixed << setprecision(2);
        cout<<"You have "<<money<<"$"<<endl;
        cout<<"(The operation was completed successfully)"<<endl;
    }
};
int main()
{
    ATM ob1;
    int ch;
    char again;
    do
    {
        cout<<"------------------------"<<endl;
        cout<<"Choose command:- "<<endl;
        cout<<"1-Deposit money"<<endl;
        cout<<"2-Withdraw money"<<endl;
        cout<<"3-Show the money"<<endl;
        cout<<"4-Exit"<<endl;
        cout<<"------------------------"<<endl;
        cout<<"Enter the command : ";
        cin>>ch;
        if (ch==1)
        {
            ob1.Deposit();
        }
        else if (ch==2)
        {
            ob1.withdraw();
        }
        else if (ch==3)
        {
            ob1.displayMoney();
        }
        else if (ch==4)
        {
            cout<<"Thank you"<<endl;
            break;
        }
        else
        {
            cout<<"Error you should enter one option from the above options only."<<endl;
        }
        if (ch!=4)
        {
        cout<<"Do you want another entry? (y / n) : ";
        cin>>again;
        while(again!='y'&&again!='n'&&again!='Y'&&again!='N')
        {
          cout<<"Enter (y) or (n) only : ";
          cin>>again;
        }

        }
    }
    while(again=='y'||again=='Y');
    return 0;
}
