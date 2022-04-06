# Tic_Tac_Toe


//A Two Player Game Of Tic-Tac-Toe 
#include<iostream>
using namespace std;
char box[10]={'0','1','2','3','4','5','6','7','8','9'};
//		FUNCTION TO GET THE BOARD READY FOR THE GAME
void board()
{
	system("cls");
	cout<<endl<<"**********************************************************************";
	cout<<endl<<"------------------------- TIC TAC TOE ------------------------";
	cout<<endl<<"**********************************************************************";
	cout<<endl<<"\n Symbol Information";
	cout<<endl<<" Player 1 - X \t\t Player 2 - O\n\n\n";
	cout<<"             |             |             "<<endl;
	cout<<"      "<<box[1]<<"      |      "<<box[2]<<"      |      "<<box[3]<<endl;
	cout<<" ------------|-------------|------------"<<endl;
	cout<<"             |             |             "<<endl;
	cout<<"      "<<box[4]<<"      |      "<<box[5]<<"      |      "<<box[6]<<endl;	
	cout<<" ------------|-------------|------------"<<endl;
	cout<<"             |             |             "<<endl;
	cout<<"      "<<box[7]<<"      |      "<<box[8]<<"      |      "<<box[9]<<endl;	
	cout<<"             |             |             "<<endl;

}
//		FUNCTION TO CHECK WHICH PLAYER WINS
//		1	Winner Data
//		0   Draw Game
//		-1  Game In Continuation
int check_win()
{
	if(box[1]!='1'&&box[2]!='2'&&box[3]!='3'&&box[4]!='4'&&box[5]!='5'&&box[6]!='6'&&box[7]!='7'&&box[8]!='8'&&box[9]!='9')
		return 0;
	else if(box[1]==box[2]&&box[2]==box[3])
		return 1;
	else if(box[4]==box[5]&&box[5]==box[6])
		return 1;
	else if(box[7]==box[8]&&box[8]==box[9])
		return 1;
	else if(box[1]==box[5]&&box[5]==box[9])
		return 1;
	else if(box[3]==box[5]&&box[5]==box[7])
		return 1;
	else if(box[1]==box[4]&&box[4]==box[7])
		return 1;
	else if(box[2]==box[5]&&box[5]==box[8])
		return 1;
	else if(box[3]==box[6]&&box[6]==box[9])
		return 1;
	else 
		return -1;
}
int main()
{
	int player=1,ch,res;
	char mark;
	cout<<endl<<" Initializing a Two Player Game Of Tic Tac Toe\n  Get Ready!!!\n";
	do{
		board();
		//if player%2==0 then player2 turn ow player1 turn
		player=(player%2)?1:2;
		cout<<endl<<" Player "<<player<<" Enter The Number From The Board Where You Want To Mark :\t";
		cin>>ch;
		mark=(player==1)?'X':'O';
		if(ch==1&&box[1]=='1')
			box[1]=mark;
		else if(ch==2&&box[2]=='2')
			box[2]=mark;
		else if(ch==3&&box[3]=='3')
			box[3]=mark;
		else if(ch==4&&box[4]=='4')
			box[4]=mark;
		else if(ch==5&&box[5]=='5')
			box[5]=mark;
		else if(ch==6&&box[6]=='6')
			box[6]=mark;
		else if(ch==7&&box[7]=='7')
			box[7]=mark;
		else if(ch==8&&box[8]=='8')
			box[8]=mark;
		else if(ch==9&&box[9]=='9')
			box[9]=mark;
		else{
			cout<<endl<<" The Block Is Already Marked\n\n Choose Again -\t";
			player--;
			cin.ignore();
			cin.get();
		}
		res=check_win();
		player++;
	}while(res==-1);
	board();
	cout<<endl<<"\n\n CALCULATING RESULTS.....\n";
	if(res==1)
		cout<<endl<<" Player - "<<--player<<" WINS THE GAME";
	else
		cout<<endl<<" DRAW GAME NOBODY WINS";
	return 0;
}
