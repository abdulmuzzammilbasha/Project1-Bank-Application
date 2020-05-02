# Project1-Bank-Application
Bank application to deposit, withdraw, check last transaction and to check balance using java code.

import java.util.Scanner;
import java.lang.Math;

public class Main
{
  public static void main (String[]args)
  {
		/**************************************************
		This is a bank application
		In this application you can 
		1.check the balance
		2.deposit amount in your account
		3.withdraw amount in your account
		4.check the last transaction of your account
		**************************************************/
		
    BankApp bankAppObj = new BankApp ("XYZ", 12345);
      bankAppObj.perform ();
  }
}

   //BankApp class has 5 meathods

class BankApp
{
  Scanner scan = new Scanner (System.in);
  //1.BankApp() constructor to show the menu and to display the welcome message

    BankApp (String st, int acn)
  {

    System.out.println ("Welcome " + st + " Your account number is " + acn);
    System.out.println ("Please select the options you want to perform");
    System.out.println
      ("----------------------------------------------------------------------");
    System.out.println ("1.Check the balance");
    System.out.println ("2.Deposit amount in your account");
    System.out.println ("3.Withdraw amount in your account");
    System.out.println ("4.Check the last transaction of your account");
    System.out.println ("5. Exit");
    System.out.println
      ("----------------------------------------------------------------------");
  }

  float blanceAmount = 0;
  float lastTransactionAmount = 0;
  
  
  void checkBalance ()
  {
    System.out.println ("Your Balance is " + blanceAmount);
    System.out.println
      ("----------------------------------------------------------------------");
    System.out.println ("1.Check the balance");
    System.out.println ("2.Deposit amount in your account");
    System.out.println ("3.Withdraw amount in your account");
    System.out.println ("4.Check the last transaction of your account");
    System.out.println ("5. Exit");
    System.out.println
      ("----------------------------------------------------------------------");

  }

  
  void deposit ()
  {
  System.out.println ("Enter the AMOUNT you want to deposit");
    float amount = scan.nextFloat();
    blanceAmount = blanceAmount + amount;
    lastTransactionAmount = amount;
  System.out.println ("Rupees " + amount + " deposited into your account and the current balance is " + blanceAmount);
    System.out.println
      ("----------------------------------------------------------------------");
    System.out.println ("1.Check the balance");
    System.out.println ("2.Deposit amount in your account");
    System.out.println ("3.Withdraw amount in your account");
    System.out.println ("4.Check the last transaction of your account");
    System.out.println ("5. Exit");
    System.out.println
      ("----------------------------------------------------------------------");

  }

  
  void withdaw ()
  {
      System.out.println ("Enter the AMOUNT you want to withdraw");
    float amount = scan.nextFloat();
    blanceAmount = blanceAmount - amount;
    lastTransactionAmount = -amount;
  System.out.println ("Rupees " + amount + " withdrawn from your account and the current balance is " + blanceAmount);
    System.out.println
      ("----------------------------------------------------------------------");
    System.out.println ("1.Check the balance");
    System.out.println ("2.Deposit amount in your account");
    System.out.println ("3.Withdraw amount in your account");
    System.out.println ("4.Check the last transaction of your account");
    System.out.println ("5. Exit");
    System.out.println
      ("----------------------------------------------------------------------");

  }

  void lastTransaction ()
  {

    if (lastTransactionAmount < 0)
      System.out.println ("The Last transaction was : Withdrawn Rupees " +
			  Math.abs (lastTransactionAmount));
    else if (lastTransactionAmount > 0)
      System.out.println ("The Last transaction was : Deposited Rupees " +
			  lastTransactionAmount);
    else
      System.out.println ("No transaction occured");
    System.out.println
      ("----------------------------------------------------------------------");
    System.out.println ("1.Check the balance");
    System.out.println ("2.Deposit amount in your account");
    System.out.println ("3.Withdraw amount in your account");
    System.out.println ("4.Check the last transaction of your account");
    System.out.println ("5. Exit");
    System.out.println
      ("----------------------------------------------------------------------");
  }

  /*perform() meathod gets the input from the user and call the meathod accordinly be passing the value
     by using do while loop and switch in dowhile which is excuted according to the options selected.
     .
   */

  void perform ()
  {
    int option = 0;


    do
      {

	option = scan.nextInt ();
	switch (option)
	  {
	  case 1:
	    checkBalance ();
	    break;
	  case 2:
	    deposit ();
	    break;
	  case 3:
	    withdaw ();
	    break;
	  case 4:
	    lastTransaction ();
	    break;
	  case 5:
	    System.out.println ("Thankyou for using this application");
	    break;
	  default:
	    System.out.println ("OOPS! INVALID OPTIONS SELECTED");
	    System.out.println ("Select form the below options");
	    System.out.println
	      ("----------------------------------------------------------------------");
	    System.out.println ("1.Check the balance");
	    System.out.println ("2.Deposit amount in your account");
	    System.out.println ("3.Withdraw amount in your account");
	    System.out.
	      println ("4.Check the last transaction of your account");
	    System.out.println ("5. Exit");
	    System.out.println
	      ("----------------------------------------------------------------------");
	  }
      }
    while (option != 5);

  }
}
