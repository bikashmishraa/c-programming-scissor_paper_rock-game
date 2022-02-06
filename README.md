#include <stdio.h>
#include <conio.h>
#include <stdlib.h>
#include <math.h>
#include <windows.h>
#include <time.h>
int win=0, lose=0,draw=0;
int SpR(char you, char comp)
{
    if (you == comp)
    {
        Beep(720, 550);
        draw++;
        return 0;
    }
    if (you == 's' && comp == 'p')
    {
        win++;
        return 1;
    }
    else if (you == 's' && comp == 'r')
    {
        lose++;
        return 2;
    }
    if (you == 'p' && comp == 'r')
    {
        win++;
        return 1;
    }
    else if (you == 'p' && comp == 's')
    {
        lose++;
        return 2;
    }
    if (you == 'r' && comp == 's')
    {
        win++;
        return 1;
    }
    else if (you == 'r' && comp == 'p')
    {
        lose++;
        return 2;
    }
    if (you == 'q')
    {
        printf("\t\t\t Good Game\n");
        printf("\t\t\t Your Total Score=%d\n", win);
        printf("\t\t\t Computer Total Score=%d\n", lose);
        printf("\t\t\t Draw Match=%d\n",draw);
    }
}
void color(){
    printf("    0 = Black       8 = Gray");
    printf("1 = Blue        9 = Light Blue\n");
    printf("2 = Green       A = Light Green\n");
    printf("3 = Aqua        B = Light Aqua\n");
    printf("4 = Red         C = Light Red\n");
    printf("5 = Purple      D = Light Purple\n");
    printf("6 = Yellow      E = Light Yellow\n");
    printf("7 = White       F = Bright White\n");
}
int main()
{
    system("color 5F");
    char you, comp,boared;
    int rest;
    printf("Are you board and want to play a game? then press y\n and if no then press N\n");
    scanf("%c",&boared);
    if(boared=='y'){
    printf("\t\t\t*****WELCOME TO THE GAME*******\n");
    printf("\t\t<-----Just Press The Key Below To Choose-------->\n");
    printf("\t\t\t\tIntroduction:\n");
    printf("\t\tPress {'s'} for Scissor {'p'} for Paper and {'r'} for Rock\n \t\t\t\tPress 'q' to Quit Game\n");
    printf("\n");
    printf("1).\t Scissor\n\t\t {'if you choose Scissor and computer Choosed Rock you lose,If Paper You Won else \t\tDraw'}\n ");
    printf("2).\t Paper\n\t\t {'if you choose Paper and computer Choosed Scissor you lose,If Rock You Won else \t\tDraw'}\n ");
    printf("3).\t Rock\n\t\t {'if you choose Rock and computer Choosed Paper you lose,If Scissor You Won else \t\tDraw'}\n ");
    printf("4).\t To Quit Game\n");
    while (you != 'q')
    {

        int roll,choose;
        srand(time(0));
        roll = rand() % 3 + 1;
        if (roll == 1)
        {
            comp = 's';
        }
        else if (roll == 2)
        {
            comp = 'p';
        }
        else
        {
            comp = 'r';
        }
        scanf("%c", &you);
        rest=SpR(you, comp);
        if(rest==0){
            printf("\t\t\t ----------------\n");
            printf("\t\t\t |   Match Draw  |\n");
            printf("\t\t\t ----------------\n");
        }
        else if(rest==1){
        printf("\t\t\t -------------------\n");
        printf("\t\t\t | Congrats You Won |\n");
        printf("\t\t\t -------------------\n");
        printf("\t\tYou Choosed %c And Computer Choosed %c\n", you, comp);
        }
        else if(rest==2){
        printf("\t\t\t -----------------\n");
        printf("\t\t\t | Oops! You lose |\n");
        printf("\t\t\t -----------------\n");
        printf("\t\tYou Choosed %c And Computer Choosed %c\n", you, comp);
        }
    }

    }
    else{
        printf("So what do you want ?\n");
    }
    return 0;
}
