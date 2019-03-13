# chapter_5-functions
#include <iostream>
#include <ctime>
#include <windows.h>
#include <string>


using namespace std;

// in tis game i have used a character called 'Kupo (^o^) with different type of face just to describe its state in each case! that character will interact with the player, give him information about his current state and the action the user would like to perform ! So i hope you will enjoy the game and 'Kupo (^-^) as well !! that idea comes from a game i like playing FF (Final Fantasy ) !

int health = 40;
int totalTreasure=0;

void story();
char AskYesNo(string question);
int RollDie(int sides = 6);
void Dead(); // dead message
void quit(); // message before quiting the adventure!
void ooops(); // message for receiving damages !

int main()
{
    story();
char answer;

    do {
        char answer = AskYesNo("\n'Kupo (^-^) : Are you ready for a new Quest !?");
        cout << "\'Kupo (^-^) : your answer is :\t" <<answer <<endl;

        srand(time(0));
        int attack = RollDie(12);
        int block =  RollDie(12);


        if (answer == 'y' || answer == 'Y'){


                // if statement will allow me to compare attack and block !! following that the result will be added into health and treasure
                if (block > attack){
                    int treasure = block; // number of block is added to total treasure!
                    cout << "\n'Kupo (^o^) : Way to go !! You've successfully blocked the attack !! " <<endl;


                    totalTreasure = totalTreasure + block;//I assigned totalTreasure to the current totalTreasure+block!that will end up with the total value!
                    cout << "'Kupo (^o^) : Your HP is now [" << health<< "] and you have [" << totalTreasure<<"] treasures" <<endl;

                }else if (block < attack){
                    health = health - attack; // number of attack is subtracted from health!

                    ooops();
                    cout << "!!! That hurts ! You've undergone [" << attack << "] point damages !!"<<endl;

                            if (health <=0){
                                Dead(); // Dead message
                                break;

                             }else {cout << "'Kupo (^-^) : Your HP is now [" << health<< "] and you have [" << totalTreasure << "] treasures !!" <<endl;
                            }
                }else {
                    continue; // it can happen that attack = block; so it will jump that case and go back to the loop

                }
                    health = health;



        } else {
                quit(); // message before the quest ends !
                break; // to exit the scope
        }

    }while(answer != 'n' || answer != 'N');
    // 'n or N' will quit the function and end the scope !!



    return 0;
}


// That will allow me to tell the beginning of the story
void story ()
{
    cout << "\t\t\t     WEL";
    Sleep(750);
    cout << "COME";
    Sleep(750);
    cout << "!";
    Sleep(750);
    cout << "!" <<endl;
    Sleep(750);
    cout << "'Kupo (^-^) : Hey whats up dude, I see you have totally recovery from your rest !!" <<endl;
    Sleep(750);
    cout <<"'Kupo (^o^) : Let's check your HP and treasure !!!";
    Sleep(750);
    cout << "\n'Kupo (^.^) : ";
    Sleep(750);
    cout << "Chec";
    Sleep(750);
    cout << "kin";
    Sleep(750);
    cout << "g";
    Sleep(750);
    cout << ".";
    Sleep(750);
    cout << ".";
    Sleep(750);
    cout << ".";
    Sleep(750);
    cout << "!!";
    Sleep(750);
    cout << "\n'Kupo (^o^): You've got  [" << health<< "] HP and [" << totalTreasure<< "] treasures !!!"<<endl;
}


char AskYesNo(string question)
{
    char inp;
    do {
            cout << question << "[Y/N]:\t";
            cin >> inp;
    }while ((inp != 'y' && inp != 'Y') && (inp != 'n' && inp != 'N'));


    return inp;
}

//Create a function that will generate randomly different number; I will add int parameter named sides with default value of 6.

int RollDie(int sides ){
    int die = rand() %sides + 1;

    return die;
}

void Dead()
{
    Sleep(750);
    cout << "'Kupo (*~*) : Ooops !! You're Dead !!" <<endl;

}

void quit()
{
     Sleep(750);
                    cout << "\n'Kupo (^ö^) : ";
                    Sleep(750);
                    cout << "You are quiting the Quest !! "<<endl;
                    Sleep(750);
                    cout << "'Kupo (^o^) : ";
                    Sleep(750);
                    cout << "I hope you had fun !!";
                    Sleep(750);
                    cout << "\n'Kupo (^o^) : ";
                    cout << "Let's see your HP and the #number of treasure you have obtained !" <<endl;
                    Sleep(750);
                    cout << "'Kupo (^o^) : ";
                    Sleep(750);
                    cout << "Hmmmm !!";
                    Sleep(750);
                    cout << "That sounds ";
                    Sleep(750);
                    cout << "interesting !!" <<endl;
                    Sleep(750);
                    cout << "'Kupo (^o^) : ";
                    Sleep(750);
                    cout << "Your HP is [" << health << "]";
                    Sleep(750);
                    cout << " with [" << totalTreasure <<"] ";
                    Sleep (750);
                    cout << "treasures !!"<<endl;
                    Sleep(750);
                    cout << "\n\n\t             'Kupo (^o^) : ";
                    Sleep(755);
                    cout << "See ";
                    Sleep(750);
                    cout << "you ";
                    Sleep(750);
                    cout << "soon !!" << endl;
                    Sleep(750);
                    cout << "\n\n\t             'Kupo (^o^) : ";
                    Sleep(755);
                    cout << "THANK";
                    Sleep (850);
                    cout << " YOU ";
                    Sleep(750);
                    cout << "!";
                    Sleep(750);
                    cout << "!" <<endl;

}

void ooops()
{
    cout << "\n'Kupo (*x*) : ";
                    cout << "O";
                    Sleep(750);
                    cout << "o";
                    Sleep(750);
                    cout << "o";
                    Sleep(750);
                    cout << "p";
                    Sleep(750);
                    cout << "s";
                    Sleep(750);
}
