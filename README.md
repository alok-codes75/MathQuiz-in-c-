# MathQuiz-in-c-
/*----------------------------------------------------
Project Name : Mathematics Quiz Game
Language     : C Programming
Developer    : Alok Kumar
Description  : A console-based mathematics quiz game
               that generates random questions and
               evaluates user performance.
----------------------------------------------------*/


#include<stdio.h>
#include<stdlib.h>
#include<time.h>

    int first(){
        int choice;
        printf("=== WELCOME TO MATHEMATICS QUIZ === \n");
        printf("_____Select Your Problem_____\n");

        printf("1. Addition problem \n");
        printf("2. Subtraction problem \n");
        printf("3. Multiplication problem \n");
        

        printf("Enter Your choice: ");
        scanf("%d", &choice);

        return choice;
    }
    
    int main(){
        int choice;
        int num1, num2;
        int correctAnswer;
        int userAnswer;
        int score=0;

        srand(time(NULL));

             choice = first();
             if(choice<1 || choice>4){
                printf("Invalid Choice...\n");
                return 0;
             }

             printf("\n ==== QUIZ STARTED ==== \n");
             for(int i=1; i<=5; i++){
                num1=rand()%100+1;
                num2=rand()%100+1;

                printf("\nProblem %d: \n ", i);

                switch (choice)
                {
                case 1:
                    printf("%d+%d = ", num1, num2);
                    correctAnswer=num1+num2;
                    break;
                case 2:
                    printf("%d - %d = ", num1, num2);
                    correctAnswer=num1-num2;
                    break;
                case 3:
                    printf("%d * %d= ", num1,num2);
                    correctAnswer=num1*num2;
                    break;
                }
        scanf("%d", &userAnswer);

            if(userAnswer==correctAnswer){
                 printf("Great! Your Answer is Absolutely Correct\n");
                    score++;
                }
            else{
                 printf("Wrong Answer!\n");
                 printf("Correct Answer is = %d\n", correctAnswer);
                }
             }
        printf("\n_____SCORE CARD_____\n");
        printf("Your Score is: %d/5\n", score);

             if(score==5){
                printf("Excellent! Perfect score\n");
             } 
             else if (score>=3){
                printf("Good! need to more practice...");
             }
             else{
                printf("fail ! keep practicing....");
            }
        return 0;
    }

