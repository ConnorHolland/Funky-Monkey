# Homework 8

###COMSC 1033 Homework 6
#####Introduction
	Homework 6 focused on how to make a math game in java. The math game was made using previously learned java
	tricks. The only new trick introduced was the use of +=, *=, and /= operators. These operators allow 
	previously defined variables to be changed incrementally. Through the use of the java tricks learned I was
	able to write a code that begins by asking a simple math question. If answered correctly the program awards
	points and asks a harder question. If incorrect, the program awards a smaller amount of points and follows 
	up by asking an easier question. The program asks a total of four questions and lets the player know their 
	final score.
#####Code
```java
package development;
import java.util.*;
public class devlopment {
public static void main(String[] args) {
Scanner input = new Scanner(System.in);
	
//Introduce game and explain rules	
	System.out.println("Hello. Lets play a math game!");
	System.out.println("I'll ask you four questions and award you points for their difficulty.");
	System.out.println("Answering all questions correctly will award you the most points.");
	System.out.println("Answering questions correctly will cause the next question to be more difficult.");
	System.out.println("Similarly, answering incorrectly will cause the next problem to be easier!");
	System.out.println("Make sure your answers are in integer format.");
	System.out.println("Also make sure you do not use a calculator, only mental math!\n");
	
	
//Setup the point system and numbers generated
int difficulty = 1000;
int base = 10;
int points = 0;
int correct = 50;
int wrong = 15;

//Define integers for round 1
int q1n1 = (int) (base + Math.random()*difficulty*8.9/100);
int q1n2 = (int) (base + Math.random()*difficulty*8.9/100);
int q1ans = q1n1 + q1n2;

//Ask question, provide feedback to user, and award points
	System.out.println("Lets begin round 1. Your first question is:");
	System.out.print(q1n1 + " + " + q1n2 + " = ");
int q1guess = input.nextInt();
	if (q1guess == q1ans) {
		System.out.println("Correct! You have earned " + correct + " points.");
		System.out.println("You now have " + (points = points + correct) + " points.");
			difficulty *= 10;
			base *= 10;
			correct += 10;
	}else{
		System.out.println("Wrong... You have earned " + wrong + " points.");
		System.out.println("You now have " + (points = points + wrong) + " points.");
			difficulty /= 10;
			base /= 10;
			correct -= 10;
		 }

//Define integers for round 2
int q2n1 = (int) (base + Math.random()*difficulty*8.9/100);
int q2n2 = (int) (base + Math.random()*difficulty*8.9)/100;
int q2ans = q2n1 + q2n2;

//Ask question, provide feedback to user, and award points
	System.out.println("\nLets move on to round 2.");
	System.out.println("Your next question is:");
	System.out.print(q2n1 + " + " + q2n2 + " = ");
int q2guess = input.nextInt();
	if (q2guess == q2ans) {
		System.out.println("Correct! You have earned " + correct + " points.");
		System.out.println("You now have " + (points = points + correct) + " points.");
			difficulty *= 10;
			base *= 10;
			correct += 10;
	}else{
		System.out.println("Wrong... You have earned " + wrong + " points.");
		System.out.println("You now have " + (points = points + wrong) + " points.");
			difficulty /= 10;
			base /= 10;
			correct -= 10;
		 }
		 
//Define integers for round 3
int q3n1 = (int) (base + Math.random()*difficulty*8.9/100);
int q3n2 = (int) (base + Math.random()*difficulty*8.9/100);
int q3ans = q3n1 + q3n2;

//Ask question, provide feedback to user, and award points
	System.out.println("\nHalfway done, keep it up!");
	System.out.println("The third question is:");
	System.out.print(q3n1 + " + " + q3n2 + " = ");
int q3guess = input.nextInt();
	if (q3guess == q3ans) {
		System.out.println("Correct! You have earned " + correct + " points.");
	System.out.println("You now have " + (points = points + correct) + " points.");
	difficulty *= 10;
	base *= 10;
	correct += 10;
	}else{
		System.out.println("Wrong... You have earned " + wrong + " points.");
		System.out.println("You now have " + (points = points + wrong) + " points.");
			difficulty /= 10;
			base /= 10;
			correct -= 10;
		 }
	
//Define integers for round 4	
int q4n1 = (int) (base + Math.random()*difficulty*8.9/100);
int q4n2 = (int) (base + Math.random()*difficulty*8.9/100);
int q4ans = q4n1 + q4n2;

//Ask question, provide feedback to user, and award points
	System.out.println("\nOne question left, lets finish strong!");
	System.out.println("The final question is:");
	System.out.print(q4n1 + " + " + q4n2 + " = ");
int q4guess = input.nextInt();
	if (q4guess == q4ans) {
		System.out.println("Correct! You have earned " + correct + " points.");
		System.out.println("Your final score is  " + (points = points + correct) + " points.");
			difficulty *= 10;
			base *= 10;
			correct += 10;
	}else{
		System.out.println("Wrong... You have earned " + wrong + " points.");
		System.out.println("Your final score is " + (points = points + wrong) + " points.");
			difficulty /= 10;
			base /= 10;
			correct -= 10;
		 }	
		 
//End the game
	System.out.println("\nCongratulations and thanks for playing! We should do it again sometime :)");
}}
```

#####Console
**Trial 1:**
Hello. Lets play a math game!
I'll ask you four questions and award you points for their difficulty.
Answering all questions correctly will award you the most points.
Answering questions correctly will cause the next question to be more difficult.
Similarly, answering incorrectly will cause the next problem to be easier!
Make sure your answers are in integer format.
Also make sure you do not use a calculator, only mental math!

Lets begin round 1. Your first question is:
42 + 43 = 85
Correct! You have earned 50 points.
You now have 50 points.

Lets move on to round 2.
Your next question is:
612 + 745 = 1357
Correct! You have earned 60 points.
You now have 110 points.

Halfway done, keep it up!
The third question is:
1078 + 7322 = 8400
Correct! You have earned 70 points.
You now have 180 points.

One question left, lets finish strong!
The final question is:
41157 + 98562 = 139719
Correct! You have earned 80 points.
Your final score is  260 points.

Congratulations and thanks for playing! We should do it again sometime :)


**Trial 2:**
Hello. Lets play a math game!
I'll ask you four questions and award you points for their difficulty.
Answering all questions correctly will award you the most points.
Answering questions correctly will cause the next question to be more difficult.
Similarly, answering incorrectly will cause the next problem to be easier!
Make sure your answers are in integer format.
Also make sure you do not use a calculator, only mental math!

Lets begin round 1. Your first question is:
97 + 27 = 4
Wrong... You have earned 15 points.
You now have 15 points.

Lets move on to round 2.
Your next question is:
1 + 3 = 5
Wrong... You have earned 15 points.
You now have 30 points.

Halfway done, keep it up!
The third question is:
0 + 0 = 4
Wrong... You have earned 15 points.
You now have 45 points.

One question left, lets finish strong!
The final question is:
0 + 0 = 4
Wrong... You have earned 15 points.
Your final score is 60 points.

Congratulations and thanks for playing! We should do it again sometime :)
 
#####Summary
	This homework did not require learning anything new other than the aforementioned += operators. I was
	able to write the entire program in very little time. After I wrote it I went back in the code and
	formatted it. I was able to place all the variables in locations that could be found intuitively. I 
	did not require the use of GIT to accomplish this homework.

