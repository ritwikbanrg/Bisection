# Bisection
/*A program to find a root of a polynomial by using bisection method. (If it lies between -10 to +10, updates are welcome)*/
#include<stdio.h>
#include<conio.h>
#include<iostream.h>
#include<math.h>
class function
{
int p1,p2,p3,p4;
public:
void define()
{
cout<<"Enter coefficients for cubic equation";
cin>>p1>>p2>>p3>>p4;
}
double generate(double op)
{
double result=(p1*pow(op,3))+(p2*pow(op,2))+(p3*pow(op,1))+p4;
return result;
}
};
void main()
{
clrscr();
double x,xres,a=-10.0,b=-9.0;
int i,j;
function f;
f.define();
for(i=-10;i<=10;i++)
{
b++;a++;
if((f.generate(a)*f.generate(b))<0)
break;
}
for(i=0;i<50;i++)
{
x=(a+b)/2;
xres=f.generate(x);
if(xres<0.0)
a=x;
else
b=x;
}
cout<<x;
getch();
}
