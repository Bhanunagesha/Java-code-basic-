Programming in Java Lab manual – P18ISL48 
Puttaswamy B S, Assistant Professor, Dept. of IS&E, PESCE, Mandya - 571401 Page 1
1 a. Write a java program to check whether a given number is “prime 
number” and “palindrome number or not”
import java.util.Scanner;
import java.io.*;
public class q1a 
 {
 public static void main(String[] args)
 {
 Scanner input = new Scanner(System.in);
 System.out.println("Enter a number to check given number is prime number or 
palindrome number or not");
 int num =input.nextInt();
 System.out.println("Enter your choice");
 System.out.println("1.for checking prime Number");
 System.out.println("2. for checking Palindrome Number");
 System.out.println("enter your choice :");
 int a= input.nextInt();
 switch (a)
 { 
 case 1:
 int flag=0;
 for(int i=2;i<num;i++)
 {
 if(num%i==0)
 {
 System.out.println(num+" is not a Prime Number");
 flag = 1;
 break;
 }
 }
 if(flag==0)
 System.out.println(num+" is a Prime Number");
 break;
{
System.out.println("Withdraw is not possible because maintain 
minimum balance");
System.out.println("Available Balance is : " + balance);
 }
 else if (amt>balance)
 {
 System.out.println("Insufficient Balance");
System.out.println("Available Balance is : " + balance);
}
else
{
double newbal = balance - amt;
System.out.println("Balance Before Withdrawal : " + 
balance);
System.out.println("Balance After Withdrawal : " + newbal);
balance = newbal;
 }
}
public void display()
 {
System.out.println("Account Holder Name : " + name);
System.out.println("Balance is : " + balance);
}
public static void main(String argsp[])
{
Pg1b b = new Pg1b();
 Scanner sc = new Scanner(System.in);
 int a,amt;
 do
 {
1 b. Write a java program to design a class to represent a bank account 
and include the following members. Date members are: Name of 
depositor, Account Number, Type of account and Balance amount in 
the account. Methods are: To assign initial values, to deposit an 
account, to withdraw an amount after checking balance and to 
display the name and balance.
import java.util.*;
class Pg1b
{
String name,type;
double accno,balance = 500.0;
public void read()
{
Scanner sc = new Scanner(System.in);
System.out.println("Enter Account Number : ");
accno = sc.nextDouble();
System.out.println("Enter Name of Depositor : ");
name = sc.next();
System.out.println("Enter Account Type : ");
type = sc.next();
}
public void deposit(int amt)
{
double newbal = balance + amt;
System.out.println("Balance Before Deposit : " + balance);
System.out.println("Balance After Deposit : " + newbal);
balance = newbal;
}
public void withdraw(int amt)
{
if(amt<=500 )
Programming in Java Lab manual – P18ISL48 
Puttaswamy B S, Assistant Professor, Dept. of IS&E, PESCE, Mandya - 571401 Page 2
 case 2:
 int k = num;
 int reverse=0,rem;
 while(num > 0)
 {
 rem = num % 10;
 reverse = reverse * 10 + rem;
 num = num / 10;
 }
 if(reverse == k)
 System.out.println(k+" is a Palindrome Number");
 else
 System.out.println(k+" is not a Palindrome Number");
 break;
 }
 }
}
System.out.println("Select:\n1 - Enter Account Details \n2 - Deposit \n3 -
Withdraw \n4 - Balance \n5 - Exit");
 a = sc.nextInt();
 switch(a)
 {
case 1:
 {
b.read();
 break;
 }
 case 2:
 {
 System.out.println("Enter Deposit Amount : ");
 amt = sc.nextInt();
 b.deposit(amt);
 break;
 }
 case 3:
 {
 System.out.println("Enter Withdrawal Amount : ");
 amt = sc.nextInt();
 b.withdraw(amt);
 break;
 }
 case 4:
 {
 b.display();
 break;
 }
 }
}while(a!=5);
2 b. Develop a Java application to generate Electricity bill. Create a class 
with the following members: Consumer no., consumer name, 
previous month reading, current month reading, type of EB 
connection (i.e. domestic or commercial). 
 Compute the bill amount using the following tariff:
 If the type of the EB connection is domestic, calculate the amount 
to be paid as follows:
  First 100 units - Rs. 1 per unit
 101-200 units - Rs. 2.50 per unit
  201 -500 units - Rs. 4 per unit
  501 units - Rs. 6 per unit
 If the type of the EB connection is commercial, calculate the amount 
to be paid as follows:
  First 100 units - Rs. 2 per unit
  101-200 units - Rs. 4.50 per unit
  201 -500 units - Rs. 6 per unit
  501 units - Rs. 7 per unit
import java.io.*;
import java.util.*;
class ElectricityBill
{
double bill;
double domesticbillcalc (int units)
{
if(units<100)
bill = units * 1 ;
else if(units <= 200)
bill = 100 * 1 + (units - 100) * 2.50 ;
else if(units <= 500)
bill = 100 * 1 + 200 * 2.50 + (units - 200) * 4 ;
else
2 a. Write a Java program to sort an array of positive integers of a given 
array, in the sorted array the value of the first element should be 
maximum, second value should be minimum value, third should be 
second maximum, fourth second be second minimum and so on. 
import java.util.Arrays;
public class Pg2a
{
 static int[] rearrange(int[] new_arra, int n)
 {
 int temp[] = new int[n];
 int small_num = 0, large_num = n-1;
 boolean flag = true;
 for (int i=0; i < n; i++)
 {
 if (flag)
 temp[i] = new_arra[large_num--];
 else
 temp[i] = new_arra[small_num++];
 flag = !flag;
 }
 return temp;
 }
 public static void main(String[] args) 
 {
 int nums[] = new int[]{10, 20, 30, 40, 50, 60, 70, 80, 90, 100};
 int result[];
 System.out.println("Original Array ");
 System.out.println(Arrays.toString(nums));
 result = rearrange(nums,nums.length);
 System.out.println("New Array ");
 System.out.println(Arrays.toString(result));
String ptype=c.next();
System.out.println("Enter the Consumer Number :");
String consno=c.next();
System.out.println("Enter the Consumer Name :");
String consname=c.next();
System.out.println("Enter the Previous Month Reading :");
int pmr=c.nextInt();
System.out.println("Enter the Current Month Reading :");
int cmr=c.nextInt();
int units = cmr-pmr;
ElectricityBill b = new ElectricityBill();
if(ptype.equalsIgnoreCase("DOMESTIC"))
{
b.show(ptype,consno,consname,pmr,cmr,units);
b.domesticbillcalc(units);
System.out.println("Bill to pay : " + b.bill);
}
else if(ptype.equalsIgnoreCase("COMMERCIAL"))
{
b.show(ptype,consno,consname,pmr,cmr,units);
b.commercialbillcalc(units);
System.out.println("Bill to pay : " + b.bill);
}
}
}
bill = 100 * 1 + 200 * 2.50 + 500 * 4 + (units - 500) * 6 ;
return bill;
}
double commercialbillcalc (int units)
{
if(units<100)
bill = units * 2 ;
else if(units <= 200)
bill = 100 * 1 + (units - 100) * 4.50 ;
else if(units <= 500)
bill = 100 * 1 + 200 * 4.50 + (units - 200) * 6 ;
else
bill = 100 * 1 + 200 * 4.50 + 500 * 6 + (units - 500) * 7 ;
return bill;
} void show(String ptype,String consno,String consname,int pmr,int cmr,int 
units)
{
System.out.println("Type of Connection : " + ptype);
System.out.println("Consumer Number : " + consno);
System.out.println("Customer Name : " + consname);
System.out.println("Previous Month Reading : " + pmr);
System.out.println("Current Month Reading : " + cmr);
System.out.println("Units Consumed : " + units);
}
}
class Pg2b
{
public static void main(String[] args)
{
Scanner c = new Scanner(System.in);
System.out.println("Enter the Type of Connection :");
[5/23, 1:33 PM] +91 79757 14004: System.out.println(key + " found at index = " +res);
 else
 System.out.println(key + " not found");
 int a[]={33,3,4,5};
 int b[]={33,13,4,5};
 System.out.println("Array A");
 for (int x: a)
 System.out.println(x);
 System.out.println("Array B");
 for (int x: b)
 System.out.println(x);
 r=Arrays.equals(a,b);
 if(r==true)
 System.out.println("Arrays a and b are equal");
 else
 System.out.println("Arrays a and b are not equal"); 
 }
 }
[5/23, 1:33 PM] +91 79757 14004: {
 comm = 5.0 / 100.0 * sal;
 }
 else if (sal <= 80000) 
 {
 comm = 8.0 / 100.0 * sal;
 }
 else if (sal <= 100000) 
 {
 comm = 10.0 / 100.0 * sal;
 }
 Else
 {
 comm = 12.0 / 100.0 * sal;
 }
 }
 
 void display() 
 {
 System.out.println("Employee name: " + name);
 System.out.println("Employee Number: " + emp_no);
 System.out.println("Monthly Sales: " + sal);
 System.out.println("Commission: " + comm);
 }
 
 public static void main(String args[]) 
 {
 Commission obj = new Commission();
 obj.input();
 obj.compute();
 obj.display();
[5/23, 1:33 PM] +91 79757 14004: 3 a. Write a program to read an array of n elements and implement 
following operations using Arrays class methods. 
 i) Perform Binary Search by reading element to be searched 
 ii) Initialize two arrays and check if the arrays are equal or not.
import java.util.Arrays;
import java.util.*;
public class Pg3a
{
 public static void main(String[] args)
 {
 int n,key,res;
 Boolean r; 
 System.out.println("Enter number of Array Elements");
 Scanner inp = new Scanner(System.in);
 n=inp.nextInt();
 int arr[]=new int[n];
 System.out.println("Enter Array Elements");
 for(int i=0;i<n;i++)
 arr[i]=inp.nextInt();
 System.out.println("Array Elements entered are");
 for (int i=0;i<n;i++) 
 System.out.println(arr[i]);
 System.out.println("Perform Binary Search");
 Arrays.sort(arr);
 System.out.println("Sorted Array");
 for (int i=0;i<n;i++) 
 System.out.println(arr[i]);
 System.out.println("Enter Element to be searched");
 key=inp.nextInt();
 res=Arrays.binarySearch(arr,key);
 if(res>=0 && res<=n-1)
[5/23, 1:33 PM] +91 79757 14004: 4 a. Write a Java program to separate even and odd numbers of a given 
array of integers. Put all even numbers first, and then odd numbers. 
Also find the number of even and odd integers in a given array of 
integers. Array elements are user Inputs.
import java.util.Scanner;
import java.util.Arrays;
class Pg4a
{
public static void main (String args[])
 {
 int counter=0;
 Scanner scan=new Scanner(System.in); //create a scanner object for input
 System.out.print("Enter the array size :\n");
 int size=scan.nextInt();//reads input from user for array size
 System.out.print("Enter the elements of the array :\n");
 int arr[]=new int[size];
 for(int i=0; i<arr.length; i++)
 {
 arr[i]=scan.nextInt();
 }//reads input from user for array elements
System.out.print("Even numbers are: \n");
for(int i=0; i<size; i++)
 {
 if(arr[i]%2==0)
 {//separates even numbers
 System.out.println(arr[i]);
 counter++;
 }
 }
System.out.println("Number of even numbers : "+counter);
System.out.print("Odd numbers are: \n");
[5/23, 1:33 PM] +91 79757 14004: 3 b. A sales person is received commission based on the sales he makes as 
shown by the following table:
Sale Commission
Up to ₹50,000 5% on sales value
More than ₹50,000 and up to ₹80,000 8% on sales value
More than ₹80,000 and up to ₹1,00,000 10% on sales value
More than ₹1,00,000 12% on sales value
Write a java program to define a class commission contains employee 
name, employee number and sales data member and methods input(), 
compute() and display() methods. Write a main method to create object of 
a class and call the above member methods.
import java.util.Scanner;
public class Commission
{
 String name;
 int emp_no;
 int sal;
 double comm;
 
 void input() {
 Scanner in = new Scanner(System.in);
 System.out.print("Enter employee name: ");
 name = in.nextLine();
 System.out.print("Enter employee number: ");
 emp_no = in.nextInt();
 System.out.print("Enter monthly sales value: ");
 sal = in.nextInt();
 }
 void compute() 
 {
 if (sal <= 50000)
[5/23, 1:33 PM] +91 79757 14004: for(int i=0; i<size; i++)
 {
 if(arr[i]%2==1)
 {//separates odd numbers
 System.out.println(arr[i]);
 }
 }
System.out.println("Number of odd numbers : "+(size-counter));
}
}
[5/23, 1:33 PM] +91 79757 14004: hours = days*24;
}
void compay()
{
show();
System.out.println("Salary is :" + rate*hours);
}
}// end of class 'DailyWorker'
class SalariedWorker extends Worker 
{
int rate;
SalariedWorker(int no, String n, int r)
{
super(no,n);
rate = r;
}
void compay(int hours)
{
show();
System.out.println("Week pay is :" + rate*hours);
}
}// end of class 'SalariedWorker'
class Pg6b 
{
public static void main(String[] args) 
{
int days;
Scanner in = new Scanner(System.in);
System.out.println("enter the number of days a daily worker worked in a week");
days = in.nextInt();
DailyWorker d = new DailyWorker(233,"Arjun",75,days);
[5/23, 1:33 PM] +91 79757 14004: SalariedWorker s = new SalariedWorker(234,"Bhuvan",100);
d.compay();
s.compay(40);
} }
[5/23, 1:33 PM] +91 79757 14004: 5 b. Write a program to create an abstract class shape with two instance 
variables d(length of the side of polygon)and sides(no. of sides of a 
polygon),constructor and abstract method area. Create subclass 
polygon and circle. For polygon class create object references for 
triangle, square and hexagon. Invoke method area for objects of 
polygon and circle classes. Write constructors for subclasses.
abstract class shape
{
double d;
int sides;
shape(double d1,int s)
{
d=d1;
sides=s;
}
abstract double area();
}
class polygon extends shape
{
polygon(double d1,int s)
{
super(d1,s);
}
double area()
{
return sides*d*d/(4*Math.tan(3.14159/sides));
}
}
class circle extends shape
{
circle(double d1,int s)
[5/23, 1:33 PM] +91 79757 14004: 5 a. Write a java program to determine the addition of two matrices (using 
for loop).
import java.util.Scanner;
import java.io.*;
class AddMatrix
{
public static void main(String args[])
{
int row, col,i,j;
Scanner in = new Scanner(System.in);
System.out.println("Enter the number of rows");
row = in.nextInt();
System.out.println("Enter the number columns");
col = in.nextInt();
int mat1[][] = new int[row][col];
int mat2[][] = new int[row][col];
int res[][] = new int[row][col];
System.out.println("Enter the elements of matrix1");
for ( i= 0 ; i < row ; i++ )
{ 
for ( j= 0 ; j < col ;j++ )
mat1[i][j] = in.nextInt();
System.out.println();
}
System.out.println("Enter the elements of matrix2");
for ( i= 0 ; i < row ; i++ )
{
for ( j= 0 ; j < col ;j++ )
mat2[i][j] = in.nextInt();
System.out.println();
}
[5/23, 1:33 PM] +91 79757 14004: 4 b. Write a class Worker and derive class DailyWorker and SalariedWorker 
from it. Every worker has a name and salary_rate. Write a method 
comPay(int hours) to compute the week pay of every worker. A daily 
worker is paid on the basis of number of days he work. The 
SalariedWorker gets paid the wage for 40hours a week no matter 
what actual hours is. Test this program to calculate the pay of 
workers. Write the program using the concept of polymorphism.
import java.io.*; 
import java.util.Scanner;
class Worker 
{
String name;
int empno;
Worker(int no, String n)
{
empno = no;
name = n;
}
void show() 
{
System.out.println("Employee number:" + empno);
System.out.println("Employee name:" + name);
}
}// end of class 'Worker'
class DailyWorker extends Worker 
{
int rate,hours;
DailyWorker(int no, String n, int r,int days)
{
super(no,n);
rate = r;
[5/23, 1:33 PM] +91 79757 14004: for ( i= 0 ; i < row ; i++ )
for ( j= 0 ; j < col ;j++ )
res[i][j] = mat1[i][j] + mat2[i][j] ; 
System.out.println("Sum of matrices:-");
for ( i= 0 ; i < row ; i++ )
{ 
for ( j= 0 ; j < col ;j++ )
System.out.print(res[i][j]+"\t");
System.out.println();
}
}
}
[5/23, 1:33 PM] +91 79757 14004: {
super(d1,s);
}
double area()
{
return (3.14159*d*d*sides);
} }
class Pg7b
{
public static void main(String[] args)
{
circle c=new circle(10.0,1);
polygon t=new polygon(10.0,3);
polygon s=new polygon(10.0,4);
polygon h=new polygon(10.0,6);
System.out.println("Area of Circle="+c.area());
System.out.println("Area of Triangle="+t.area());
System.out.println("Area of Square="+s.area());
System.out.println("Area of Hexagon="+h.area());
} }
