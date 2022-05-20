# HangMan:

Main concept:
Here, we have 6 body parts. For every wrong guess, we lose a lose a body part. If we lose all 6 body parts ,we lose the game.

Algorithm/Logic:
Every time when we enter a character, first it will go into check1 function. If that character is as specified, then it will go into check2 for that character is present in word not + updating the play word if present in word. Then, we will print the body parts hung at that time. Finally, we check for winning case in win sub and losing case. 

Sub's:
1)check1: It will check the character is already guessed or not, return 0 if already guessed 1 if not guessed
2)check2: It will update the play array and make inword =1 if present in selected random word. else it will do no work.
3)win: It will check if there are still "_" character left. If there are no such "_" left it will return 1 else 0;
4)fgd: It will print the body parts which are hung at that point of time by taking argument tries.

If we want to play again, we have to run the code again.
