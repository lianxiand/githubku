# githubku
nothing
c++初学者
因为某些原因来到了github，希望可以从中学到一些课堂外的知识‘
this all,thanks.

这是一个模拟抽奖的c++程序，应该可以供您使用，不过他只支持三位数；
#include <iostream>
#include <ctime>
#include <cstdlib>
using namespace std;
int main()
{  srand(time(0));
  int lottery = rand() % 1000;
  cout << "Enter your lottery pick (three digits) :";
  int guess;
  cin >> guess;
  cout << "The lottert is : "<<lottery<<endl;
  
  int lottery1 = lottery / 100;
  int lottery2 = lottery % 100 / 10;
  int lottery3 = lottery % 10;
  
  int guess1 = guess / 100;
  int guess2 = guess % 100 / 10;
  int guess3 = guess % 10;
  
  if (guess == lottery)
    cout << "Exact match: you win $10,000" <<endl;
    else if ((guess1==lottery1&&guess2==lottery3&&guess3==lottery2)||(guess1==lottery2&&guess2==lottery3&&guess3==lottery1)||(guess1==lottery2&&guess2==lottery1&&guess3==lottery3)
	||(guess1==lottery3&&guess2==lottery2&&guess3==lottery1)||(guess1==lottery3&&guess2==lottery1&&guess3==lottery2))
	cout << "Match all right: you win $3,000" <<endl;
	else if (guess1==lottery1||guess1==lottery2||guess1==lottery3||guess2==lottery1||guess2==lottery2||guess2==lottery3||guess3==lottery1||guess3==lottery2||guess3==lottery3)
	cout << "Match one digits: you win $1,000" <<endl;
	else
	cout << "Sorry,no match"<<endl;
	return 0;
}
