# Tic-Tac-Toe

#include <cstdlib>
#include <iostream>
#include <math.h>
#include <string>
#include <ctime>
#include <cctype>
#include <cmath>
using namespace std;

char Box [3] [3];
char Turn = 'X';
char filler ='X';
string Player_1, Player_2;
char decision = 'Y';

int Move;
int total_moves=0;
int winner_found = 0;

void P1_P2_Box();
void P_P_Turn();
void Box_reset();
void Keep_the_turn();
void Chk_winner();

int main ()
{  
cout<<"\n\nTik Tac toe Game "<< endl;
cout<<"Player 1, please enter your full name: ";
cin>> Player_1;

cout<<"\nPlayer 2, please enter your full name: ";
cin>> Player_2;

//Loop to continue while players wants to play
do{
total_moves = 0;
winner_found = 0;
Box_reset();
P1_P2_Box();
P_P_Turn();

} while (decision == 'Y');
}

//Keep the Turn
void keep_the_turn(void)
{
cout<< "\nWhoops, this spot is taken!";
if (Turn == '0')
{ 
filler ='0';
Turn = 'X';
}
  
else
{
filler ='X';
Turn = '0';
}  
}

//Check the winner function
void Chk_winner()
{
if 
(
     (Box [0][0] == Box [0][1]) && (Box [0][1] == Box [0][2]) ||
     (Box [1][0] == Box [1][1]) && (Box [1][1] == Box [1][2]) ||

     (Box [2][0] == Box [2][1]) && (Box [2][1] == Box [2][2]) ||
     (Box [0][0] == Box [1][0]) && (Box [1][0] == Box [2][0]) ||

     (Box [0][1] == Box [1][1]) && (Box [1][1] == Box [2][1]) ||
     (Box [0][2] == Box [1][2]) && (Box [1][2] == Box [2][2]) ||

    (Box [0][0] == Box [1][1]) && (Box [1][1] == Box [2][2]) ||
    (Box [0][2] == Box [1][1]) && (Box [2][2] == Box [2][0])
) 

  
 {
   
if (Turn == 'X')
{
cout<<Player_2<<" has won" << endl;
winner_found = 1;
    

}  
else if (Turn == '0')
{
cout<<Player_1<<" has won" << endl;

//total_moves = 9;
winner_found = 1;
}
}
} 

//Box Reset with original values
//A label for the box in order to showcase
void Box_reset(void)
{
Box [0][0] = '1';
Box [0][1] = '2';
Box [0][2] = '3';
Box [1][0] = '4';
Box [1][1] = '5';
Box [1][2] = '6';
Box [2][0] = '7';
Box [2][1] = '8';
Box [2][2] = '9';

Turn = 'X';
filler = 'X';
}

//Box Draw Function
void P1_P2_Box()
{

//cout<<"\t"<< Player_1 << "[X]" << "\n\t" << Player_2 << "[O]\n\n";
cout<<"\t\t           |            |           \n";
cout<<"\t\t     "<<Box[0][0]<<"     |      "<<Box[0][1]<<"     |     "<<Box[0][2]<<"     \n";
cout<<"\t\t __________|____________|__________ \n";
cout<<"\t\t           |            |           \n";
cout<<"\t\t     "<<Box[1][0]<<"     |      "<<Box[1][1]<<"     |     "<<Box[1][2]<<"     \n";
cout<<"\t\t __________|____________|__________ \n";
cout<<"\t\t           |            |           \n";
cout<<"\t\t     "<<Box[2][0]<<"     |      "<<Box[2][1]<<"     |     "<<Box[2][2]<<"     \n";
cout<<"\t\t __________|____________|__________ \n";

  }


// Person vs Person Function
void P_P_Turn()
{

//Loop to go for 9 moves only 
while (total_moves < 9)
{
if (Turn == 'X')
{ 
cout<<"\n\t " << Player_1 << "[X] turn: ";
filler ='X';
Turn = '0';
}
  
else if (Turn == '0')
{ 
cout<<"\n\t " << Player_2 << "[0] turn: ";
filler = '0';
Turn = 'X';
} 

cin >> Move;

//Fill the box based on entry
switch (Move)
{
case 1: 
{
if (Box [0][0] == '1')
{
Box [0][0] = filler;
P1_P2_Box();
total_moves = total_moves + 1;
Chk_winner();
          
}
else  
{
keep_the_turn();
}  
}
break;
      
case 2: 
{
if (Box [0][1] == '2')
{
Box [0][1] = filler;
P1_P2_Box();
total_moves = total_moves + 1;
Chk_winner();
}
        
else  
{
keep_the_turn();
}  
}
break;
      
case 3: 
{
if (Box [0][2] == '3')
{
Box [0][2] = filler;
P1_P2_Box();
total_moves = total_moves + 1;
Chk_winner();
}
else
{
keep_the_turn();
}
}
break;
case 4: 
{
if( Box [1][0] == '4')
{
Box [1][0] = filler;
P1_P2_Box();
total_moves = total_moves + 1;
Chk_winner();
}
          
else
{
keep_the_turn();
}
}
break;

case 5: 
{
if (Box [1][1] == '5')
{
Box [1][1] = filler;
P1_P2_Box();
total_moves = total_moves + 1;
Chk_winner();
}
        
else
{
keep_the_turn();
}
}
break;

case 6: 
{
if (Box [1][2] == '6')
{
Box [1][2] = filler;
P1_P2_Box();
total_moves = total_moves + 1;
Chk_winner();
}
      
else
{
keep_the_turn();
}
}
break;
    
case 7: 
{
if (Box [2][0] == '7')
{
Box [2][0] = filler;
P1_P2_Box();
total_moves = total_moves + 1;
Chk_winner();
}

else
{
keep_the_turn();
}
          
}
break;
    
case 8: 
{
if (Box [2][1] == '8')
{
Box [2][1] = filler;
P1_P2_Box();
total_moves = total_moves + 1;
Chk_winner();
}
        
else
{
keep_the_turn();
}
} 
    
break;
case 9: 
{ 
if (Box [2][2] == '9')
{
Box [2][2] = filler;
P1_P2_Box();
total_moves = total_moves + 1;
Chk_winner();
}
        
else
{
keep_the_turn();
}
}
break;
    
default: 
cout<<"Your choice is invalid, try again!"<< endl;
break;
}
  
if (winner_found == 1)
{
cout << "Do you want to continue (Y/N)? ";
cin >> decision;
break; 
}

if (total_moves == 9)
{
cout << "It's a draw, Do you want to continue (Y/N)? ";
cin >> decision;
break; 
}
}//swith end
            
}// while loop end
  
