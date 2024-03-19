import random
print("welcome to the Number Guessing Game!")
print("I am thinking of number between 1 to 100.")
rand_number = random.randint(1,100)
difficulty = input("Choose the difficulty. Type 'easy' or 'hard' ").lower()
if difficulty == "hard":
    live = 5
    print(f"You have {live} attempts left to guess the number")
else:
    live = 10
    print(f"You have {live} attempts left to guess the number")
isGame = True
while isGame:
    user_guess = int(input("Make a guess: "))
    if user_guess > rand_number:
        print("Too High")
        print("Guess again.")
        live -= 1
        if live == 0:
            print("You are out of attempts. Sorry")
            isGame = False
        else:
            print(f"You have {live} attempts left to guess the number")
            
    elif user_guess == rand_number:
        print("You guessed it. Hurry!")
        isGame = False
    else:
        print("Too low")
        print("Guess again.")
        live -= 1
        if live == 0:
            print("You are out of attempts. Sorry")
            isGame = False
        else:
            print(f"You have {live} attempts left to guess the number")
