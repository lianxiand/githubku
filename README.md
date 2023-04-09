# githubku
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



使用函数指针参数调用函数示例：
#include <iostream>
using namespace std;
#include <cmath>
typedef double funType( double );
funType circlePerimeter;
funType circleArea;
funType ballArea;
funType ballVolume;
double callFun(funType*,double);
int main()
{ double r;
 cout << "enter the radius: ";
 cin >> r;
 cout << "the perimeter of circle is: " << callFun(circlePerimeter,r) << endl;
 cout << "the area of circle is: " << callFun(circleArea,r) << endl;
 cout << "enter the radius of a ball: ";
 cin >> r;
 cout << "the area of the ball is: " << callFun(ballArea,r) << endl;
 cout << "the volume of the ball is: "<< callFun(ballVolume,r) << endl; 
}
const double pi = 3.14159;
double callFun(funType*qf,double r)
{return qf(r);
}
double circlePerimeter(double radius)
{return 2*pi*radius;
}
double circleArea(double radius)
{return pi*radius*radius;
}
double ballArea(double radius)
{return 4*pi*radius*radius;
}
double ballVolume(double radius)
{return 4.0/3*pi*pow(radius,3);
}

现在遇到了问题；
我需要使用c++来编写代码，计算PI的值；
如下所示；
但是当输出到第九个数字的时候，就会出现数据紊乱，明显的不对，但是我不知道应该如何去修改；
#include <iostream>
#include <iomanip>
#include <cmath>
using namespace std;
int f1(int n)
{if(n == 0)
{
return 1;}
else {int result =1;

for (int i=n+1;i<=2*n;++i)
{
  result *=i;}
 return result;
}}//n的阶乘 
int f2(int m)
{if (m == 0)
{  return 1;}
  else if (m >= 1)
{ return m*f2(m-1);}
}//n+1累乘到2n 
int main()
{long double s=0.0,PIS = 0.0;
for (int n=1;n <= 10;++n)
{
  s=pow(2,2*n)*f2(n)/pow(n,0.5)/f1(n);
  PIS = pow (s,2);
 cout << "n = " <<setw(3) << n << ",\tPI = " << fixed << setprecision(10) << PIS <<endl;}
 return 0;
}
