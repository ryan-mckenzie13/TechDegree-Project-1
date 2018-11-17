#Techdegree Project 1
#Guessing Game
import random

def start_game():
# write your code inside this function.
    print("*"*40)
    print("   WELCOME TO THE NUMBER GUESSING GAME")
    print("*"*40)
    print("RULES\n1. Pick a number 1-10\n2. Have Fun")
    answer=random.randint(1,10)
    attempt=0
    guessing_game= 'yes'
    game_round=1
    while guessing_game =='yes':
            
            try:
#Trying to meet exceeds expectations with keeping number 1-10
                player_guess=int(input("Please guess a number 1-10:  "))
                if player_guess <1 or player_guess> 10:
                    raise ValueError("Value must be number 1-10")
                
            except ValueError as err:
                attempt=attempt+1
                print("{}".format(err))
            else:
                       
                if player_guess == answer:
                    attempt=attempt+1
                    print("Congrats you got it!  It took you {} tries.".format(attempt))
#Trying to meet exceeds expectations with high score calculation                    
                    if game_round== 1:
                        print("The current highscore is {}!".format(attempt))
                        high_score=0
                        high_score=attempt
                    else:
                        if attempt<= high_score:
                            print("The current highscore is {}".format(attempt))
                        else:
                            print("The current highscore is {}".format(high_score))
#Trying to meet exceeds expectations with prompt to play again!
                    guessing_game=input("Would you like to play again? Yes/No:  ")
                    guessing_game=guessing_game.lower()
                    if guessing_game=='yes':
                        answer=random.randint(1,10)
                        game_round=game_round+1
                        attempt=0
                        continue
                        
                    else:
                        print("Thanks for playing, the game is now ending")
                    break
            
                if player_guess <  answer:
                    attempt=attempt+1
                    print("Good guess but the number is higher!")
                    continue
                if player_guess > answer:
                    attempt=attempt+1
                    print("Good guess but the number is lower!")
                    continue
                
                   

if __name__ == '__main__':
    # Kick off the program by calling the start_game function.4
    start_game()
