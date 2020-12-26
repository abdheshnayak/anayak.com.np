---
layout: post
sn: 1
type: cpptuts
title: "All basic C programs | part-1"
subtitle: "CPP Tutorials | Prgbook"
description: "more than 60 basic C Program question with answer."

---

**Q1.write a program to print a message "Hello world " in c language.**

**For Turbo++**

```cpp
#include<studio.h>
#include<conio.h>
void main()
{
  printf("Hello world");
  getch ();
}
```

**For Other compilers**
```cpp
#include<stdio.h>
int main()
{
  printf("Hello World");
  return 0;
}
```
**Q2.Write a program to calculate summ of two numbers in c language.**

**For turbo++**
```cpp
#include<studio.h>
#include<conio.h>
void main()
{
Int  a,b,c;
printf("Enter the two numbers to calculate sum");
scanf("%d%d",a,b);
c=a+b;
printf("sum is %d",c);
getch ();
}
```
**For Other Compilers**

```cpp
#include<studio.h>
int main()
{
Int  a,b,c;
printf("Enter the two numbers to calculate sum");
scanf("%d%d",a,b);
c=a+b;
printf("sum is %d",c);
}
```

**Q3.Write a program to print Integer in c language.**

```cpp
#include < stdio.h >

int main()
{
  int a;

  printf("Enter an integer ");
  scanf("%d", &a);
  //takes an integer from user

  printf("Integer that you have entered is %d ", a);

  return 0;
}
```

**Q4.Write a program to calculate area of triangle in C language.**

```cpp
#include < stdio.h >

void main()
{
  int height, base;
  float ans;/*ans may come in fractions*/

  printf("Enter height and base");
  scanf("%d %d",&height, &base);
  ans= (1/2)*height*base;
  /* mathematical formula*/

  printf("Area if triangle is %f",ans);
}
```

**Q5.Write a program to Check integer Odd or Even in C language.**
```cpp
#include < stdio.h >

main()
{
  int n;

  printf("Enter an integer ");
  scanf("%d",&n);

/*if n is completely divisible by 2 then prints even otherwise n is odd*/
  if ( n%2 == 0 )
    printf("Even ");
  else
    printf("Odd ");

  return 0;
}
```

**Q6. Write a program to Add subtract multiply divide in C language.**
```cpp
#include < stdio.h >

int main()
{
  int first, second, add, subtract, multiply;
  float divide;

  printf("Enter two integers ");
  scanf("%d%d", &first, &second);

  add = first + second;
  subtract = first - second;
  multiply = first * second;
  divide = first / (float)second;
  //typecasting

  printf("Sum = %d ",add);
  printf("Difference = %d ",subtract);
  printf("Multiplication = %d ",multiply);
  printf("Division = %.2f ",divide);

  return 0;
}
```
**Q7. Write a program to Add n numbers in C language.**
```cpp
#include < stdio.h >

int main()
{
  int n, sum = 0, c, value;

  printf("Enter the number of integers you want to add ");
  scanf("%d", &n);

  printf("Enter %d integers ",n);

  for (c = 1; c <= n; c++)
  {
  scanf("%d",&value);
  sum = sum + value;
  /*adding each no in sum*/
  }

  printf("Sum of entered integers = %d ",sum);

  return 0;
}
```

**Q8. Write a program to Add digits in C language.**
```cpp
#include < stdio.h >

int main()
{
  int n, sum = 0, remainder;

  printf("Enter an integer ");
  scanf("%d",&n);

  while(n != 0)
  {
  remainder = n % 10;
 /*stores unit place digit to remainder*/
  sum = sum + remainder;
  n = n / 10;
 /*dividing no to discard unit place digit*/
  }

  printf("Sum of digits of entered number = %d ",sum);

  return 0;
}
```

**Q9. Write a program to find Greatest of 3 numbers in C language.**

```cpp
#include < stdio.h >

void main()
{
  int a,b,c;

  printf("enter any three numbers: ");
  scanf("%d%d%d",&a, &b, &c);
  if(a>b&&a>c)
  /*if a is greater than b & c*/
  printf("greatest number is: %d",a);
  else if(b>c)
  /*if not a then if b is greater than c*/
  printf("greatest number is: %d",b);
  else
  /*if a & b are not greater*/
  printf("greatest number is: %d",c);
}
```
**Q10. Write a program to Swapping two numbers in C language.**
```cpp
#include < stdio.h >

int main()
{
  int x, y, temp;

  printf("Enter the value of x and y ");
  scanf("%d%d", &x, &y);

  printf("Before Swapping x = %d y = %d ",x,y);

  temp = x;
  x = y;
  y = temp;
/*using temp to swap
storing x to temp and y to x then moving temp to y*/

  printf("After Swapping x = %d y = %d ",x,y);

  return 0;
}
```

**Q11. Write a Program using Nested If Else in C language.**

```cpp
#include < stdio.h >
void main()
{
  int marks;
  printf("Enter your marks : ");
  scanf("%d",&marks);

  if(marks>100)
/*marks greater than 100*/
    printf("Not valid marks");

  else if(marks>=80)
/*marks between 80 & 99*/
    printf("your grade is A");

  else if(marks >=70)
/*marks between 70 & 79*/
    printf("your grade is B");

  else if(marks>=50)
/*marks between 50 & 69*/
    printf("your grade is C");

  else if(marks>=35)
/*marks between 35 & 49*/
    printf("your grade is D");

  else
/*marks less than 35*/
    printf("your grade is E");
}
```

**Q12. Write a Program to Calculate percentage in C language.**

```cpp
#include < stdio.h >

void main()
{
  int s1, s2, s3, s4, s5, sum, total = 500;
  float per;
  printf(" Enter marks of 5 subjects : ");
  scanf("%d %d %d %d %d", &s1, &s2, &s3, &s4, &s5);

  sum = s1 + s2 + s3 + s4 + s5;
  printf(" Sum : %d", sum);

  per = (sum * 100)/500;
  /* percentage formula*/
  printf(" Percentage : %f", per);
}
```

**Q13. Write a Program to Calculate Gross salary In C language.**

```cpp
#include < stdio.h >

void main()
{
  int gross_salary, basic, da, ta;

  printf("Enter basic salary : ");
  scanf("%d", &basic);

  da = (10 * basic)/100;
  ta = (12 * basic)/100;

  gross_salary = basic + da + ta;
  printf(" Gross salary : %d",gross_salary);
}
```

**Q14. Write a Program to Calculate Simple interest In C language.**

```cpp
#include < stdio.h >

void main()
{
  int amount, rate, time, ans;

  printf(" Enter Principal Amount : ");
  scanf("%d", &amount);

  printf(" Enter Rate of Interest : ");
  scanf("%d", &rate);

  printf(" Enter Period of Time : ");
  scanf("%d", &time);

  ans = (amount * rate * time)/100;
  /*Simple interest formula*/
  printf(" Simple Interest : %d",ans);
}
```

**Q15. Write a Program to calculate Area of Circle In C language.**

```cpp
#include < stdio.h >
#include < math.h >
#define PI 3.142

void main()
{
  float radius, area;

  printf("Enter the radius of a circle \n");
  scanf("%f", &radius);

  area = PI * pow(radius, 2);

  printf("Area of a circle = %5.2f\n", area);
}
```

**Q16. Write a Program to calculate Area of Rectangle In C language.**

```cpp
#include < stdio.h >
#include < conio.h >

int main() {
  int length, breadth, area;

  printf(" Enter the Length of Rectangle : ");
  scanf("%d", &length);

  printf(" Enter the Breadth of Rectangle : ");
  scanf("%d", &breadth);

  area = length * breadth;
  printf(" Area of Rectangle : %d", area);

  return (0);
}
```

**Q17. Write a Program to calculate Area of Square in c language.**

```cpp
#include < stdio.h > 

int main() {

  int side, area;

  printf(" Enter the Length of Side : ");

  scanf("%d", &side);

  area = side * side;

  printf(" Area of Square : %d", area);

  return (0);

}
```

**Q18. Write a program to calculate Volume of Cube In C language.**

```cpp
#include < stdio.h >
void main()
{
  float a;
  float surface_area,volume;
  printf("Enter size of any side of a cube : ");
  scanf("%f",&a);
  surface_area = 6 * (a * a);
  volume = a * a * a;
  printf("Surface area of cube is: %.3f",surface_area);
  printf(" Volume of cube is : %.3f",volume);
}
```

**Q19. Write a Program to calculate Volume of Cylinder In C language.**

```cpp
#include < stdio.h >
void main()
{
  float vol,pie=3.14;
  float r,h;
  printf("ENTER THE VALUE OF RADIOUS :- ");
  scanf("%f",&r);
  printf("ENTER THE VALUE OF HEIGHT :- ");
  scanf("%f",&h);
  vol = pie * r * r * h;
  printf("VOLUME OF CYLINDER IS :- %3.2f ",vol);
}
```

**Q20. Write a Program to calculate Volume of Sphere in C language.**
```cpp
#include < stdio.h > 
#include < math.h > 
void main()
{
  float radius,pie,volume;
  pie=3.1416;
  printf("Enter the radius:");
  if(scanf("%f",&radius)==1)
  {
    volume=(4/3)*pie*pow(radius,3);
    printf("The volume is :%6.2f",volume);
  }
  else
  {
    printf("error ,enter correct value");
  }
}
```