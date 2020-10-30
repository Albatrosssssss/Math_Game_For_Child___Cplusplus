#include <bits/stdc++.h>
#include <cstdlib>
#include <time.h>
#include <conio.h>
using namespace std;

int level(){
    enterChoice:
    cout << "1. Easy\n2. Medium\n3.Hard\n";
    int chooseLevel;
    cin >> chooseLevel;
    if(chooseLevel > 0 && chooseLevel < 4){
        return chooseLevel;
    }else{
        cout << "Invalid\n";
        goto enterChoice;
    }
}
void calculation(int choice, int level){
    srand(time(0));
    int  num1 = rand(), num2 = rand();
    if(level ==1){
        num1 %= 10; num2 %= 10;
        num1++; num2++;
    }else if(level ==2){
        num1 %= 100; num2 %= 100;
        num1++; num2++;
    }else if(level ==3){
        num1 %= 1000; num2 %= 1000;
        num1++; num2++;
    }
    
    double guessAns;
    double ans;
    if(choice == 1){
        cout << num1 << " + " << num2 << " = ?\n"; 
        cin >> guessAns;
        ans = num1 + num2;
        if(ans == guessAns){
            cout << "Right"<<endl;
        }else{
            cout << "Wrong\nCorrect Ans : " << ans << "\n";
        }
    }
    else if(choice == 2){
        cout << num1 << " - " << num2 << " = ?\n";
        cin >> guessAns;
        ans = num1 - num2;
        if (ans == guessAns){
            cout << "Right"<<endl;
        }else{
            cout << "Wrong\nCorrect Ans : "<< ans << "\n";
        }
        }
    else if(choice == 3){
        cout << num1 << " / " << num2 << " = ?\n";
        cin >> guessAns;
         ans = (double)num1 / num2;
        if (ans == guessAns){
            cout << "Right"<<endl;
        }else{
            cout << "Wrong\nCorrect Ans : "<< ans << "\n";
        }
        }    
    else if(choice == 4){
        cout << num1 << " * " << num2 << " = ?\n";
        cin >> guessAns;
        ans = num1 * num2;
        if (ans == guessAns){
            cout << "Right"<<endl;
        }else{
            cout << "Wrong\nCorrect Ans : "<< ans << "\n";
        }
        }
    }

int main()
{
    
    cout <<"Chose a Game to Play"<<endl;
    cout <<"1.Addition Gaame"<<endl;
    cout <<"2.Substractiion Game"<<endl;
    cout <<"3.Divition Game"<<endl;
    cout <<"4.Multiplication Game"<<endl;
    cout <<"Enter your choise in (1 to 4)"<<endl;
    
    int choice, gameLevel=0;
    cin >> choice;
    if(choice == 1){
        cout << "Addition"<<endl;
        gameLevel = level();
    }
    else if (choice == 2){
        cout<< "Substractiion"<<endl; 
        gameLevel = level();
        
    }
    else if (choice == 3){
        cout<< "Divition"<<endl; 
        gameLevel = level();
    }
    else if (choice == 4){
        cout<< "Multiplication"<<endl; 
        gameLevel = level();
    }
    calculation(choice, gameLevel);
    
  
    
   
}





