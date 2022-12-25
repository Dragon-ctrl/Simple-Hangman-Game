import string
import random

#Create a list of words
words = ["apple","banana","grapes","watermelon","strawberry"]

#Create a function to pick a random word from the list
def pick_random_word():
    return random.choice(words)

#Create a function to check if the user input is a single letter
def is_letter(user_input):
    return len(user_input) == 1 and user_input.isalpha()

#Create a function to check if the letter is in the word
def check_letter(letter, word):
    if letter in word:
        return True
    else:
        return False

#Create a function to print the correct outcomes
def print_outcome(word, guessed_letters):
    for letter in word:
        if letter in guessed_letters:
            print(letter, end="")
        else:
            print("_", end="")
    print("")

#Create a function to play the hangman game
def play_hangman():
    #Pick a random word from the list
    word = pick_random_word()
    #Create a variable to set the number of guesses
    num_guesses = 5
    #Create a variable to store all the guessed letters
    guessed_letters = []
    
    #Loop until either the user runs out of guesses or guesses the word
    while num_guesses > 0 and not all_letters_guessed(word, guessed_letters):
        
        #Print the number of guesses
        print("You have " + str(num_guesses) + " guesses left")
        #Print the letters already guessed
        print("Letters already guessed:", guessed_letters)
        #Print the outcome
        print_outcome(word, guessed_letters)
        
        #Get the user input
        user_input = input("Guess a letter: ")
        #Check if the user input is a single letter
        if is_letter(user_input):
            #Check if the letter is in the word
            if check_letter(user_input, word):
                #If the letter is in the word, add it to the guessed_letters list
                guessed_letters.append(user_input)
            else:
                #If the letter is not in the word, decrease the number of guesses
                num_guesses -= 1
        else:
            #If the user input is not a single letter, skip this turn
            print("Please enter a single letter")
            
    #Print the outcome
    print_outcome(word, guessed_letters)
    
    #Check if the user won or lost
    if num_guesses > 0:
        print("You win!")
    else:
        print("You lose!")

#Create a function to check if all the letters are guessed
def all_letters_guessed(word, guessed_letters):
    for letter in word:
        if letter not in guessed_letters:
            return False
    return True

#Call the play_hangman function
play_hangman()
