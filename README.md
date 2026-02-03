#include <cs50.h>
#include <stdio.h>
#include <string.h>
#include <ctype.h>
#include <time.h>

//string attributes[] = {"Health", "Strength", };
string charCharacteristics[] = {"Empath", "Social", "Courage", };
string weapons[] = {"Sword", "Lance", "Bow", "Axe", "Staff"};

//Weapon Attack Lists
string weaponAttacks[][2] = {
{"Swing", "Stab"}, //Sword
{"Thrust", ""}, //Lance
{"Shoot", ""}, //Bow
{"Slash", "Chop"},  //Axe
{"Thrust", "Cast"}  //Staff
};



int chooseWeapon(){
    for(int i = 0; i < 5; i++){
        printf("%i. %s\n", i + 1, weapons[i]);
    }
       string weapon = get_string("Choose a Weapon: \n");
        for(int i = 0; i < 5; i++){
            if(strcmp(weapon, weapons[i]) == 0){
            printf("\n\033[1;31m%s Selected!\033[0m\n\n", weapons[i]);
            return i;
        }
    }
    printf("%s is not is your arsenal... Pick one that is\n", weapon);
    return -1;

}

int weaponArt(){
    for(int i = 0; i < 5; i++){
        if(i == 0){
printf("" //art from https://www.asciiart.eu/weapons/swords
"      /| ________________\n"
"O|===|* >________________>\n"
"      \\|\n\n");
    } else if (i == 2){
        printf(""
"   (\n"
"    \\\n"
"     )\n"
"##-------->\n"
"    )\n"
"   /\n"
"  (\n");
    }

    }
    return 0;
}

int main(void){
    printf("\033[1;35m");
    string playerName = get_string("\n \nWelcome to \033[1;35m[NAME OF GAME]\033[0m\nPlease enter the name of your character: \n");
        for(int i = 0; i < strlen(playerName); i++){
            if(isalpha(playerName[i])){
                printf("\n \n\033[1;33mHello, %s!! Let's get this adventure started!\n \n\033[0m", playerName);
            }
        }

        printf("Now, what weapon shall you wield?\n \n");

        int weaponChoice = chooseWeapon(); //return value of i = what weapon you chose
        weaponArt();
       //chooseWeapon();




return 0;
}
