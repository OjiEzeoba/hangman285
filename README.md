# Milestone Project work
# Hangman
Hangman is a classic game in which a player thinks of a word and the other player tries to guess that word within a certain amount of attempts.


# Project Title: My Favourate Fruits Game Picker(Milestone2)
This is a fruit game project aimed at developing a guessing game where a player thinks of his or her favourite fruit and the other player guess the friut name for a limited number of time.
Or the computer thinks of a world and the players/user tries to guess it.
## Table of Contents
- [Description](#description)
- [Installation](#installation)
- [Usage](#usage)
- [File Structure](#file-structure)
- [License](#license)

## Description

**My Favourate Fruits Game Picker** allows users to randomly select a fruit from a predefined list of favorite fruits. The project also includes input validation to ensure that user inputs are valid single alphabetical characters. This project demonstrates basic Python skills, including list manipulation, user input handling, and input validation.

### What it does
- Creates a list of favorite fruits.
- Randomly selects a fruit from the list.
- Prompts the user to guess a letter and validates the input.

### Aim of the project
- To practice basic Python programming concepts.
- To learn how to handle user inputs and validate them.
- To understand the use of random module and conditional statements in Python.

### What you learned
- Creating and manipulating lists in Python.
- Taking and validating user inputs.
- Using the `random` module to select a random item from a list.
- Writing basic conditional statements.


```
import random
favorite_fruits = ['Apple', 'Mango', 'Peach', 'BlackGrape', 'Pineapple']
word_list = favorite_fruits
print(word_list)
word = random.choice(word_list)
print("Randon selected fruit:", word)
guess = input("Enter a single letter: ")
print("Entered letter is:", guess)
if len(guess) == 1 and guess.isalpha():
    
    print("Good guess!")
else:
   
    print("Oops! That is not a valid input.")
```


# Project Title:Hangman Letter guessing game(Milestone3)
## Description
In this game the user is prompts to guess a letter and validate it. If correct/valid. It will be checked if the guessed letter is in the word radomly selected from the list already defined.
if the guessed letter is in the secret word, an appropriate message will be printed.Otherwise it Continuously prompts the user to guess a letter until a valid guess is provided. Then checks the guess against the word.

```
import random


words = ['Apple', 'Mango', 'Peach', 'BlackGrape', 'Pineapple']
secret_word = random.choice(words)

while True:
    
    guess = input("Guess a letter: ")

    if guess.isalpha() and len(guess) == 1:
        
        if guess in secret_word:
           
            print(f"Good guess! {guess} is in the word.")
        else:
           
            print(f"Sorry, {guess} is not in the word. Try again.")
        break 
    else:
      
        print("Invalid letter. Please, enter a single alphabetical character.")
    break
else:
        
        print("Invalid letter. Please, enter a single alphabetical character.")
    


if guess in secret_word:
    print(f"Good guess! {guess} is in the word.")
else:
    print(f"Sorry, {guess} is not in the word. Try again.")


def ask_for_input():
    while True:
       
        guess = input("Guess a letter: ")

       
        if guess.isalpha() and len(guess) == 1:
           
            check_guess(guess)
            break
        else:
           
            print("Invalid letter. Please, enter a single alphabetical character.")


ask_for_input()
```



# Project Title:Hangman Game (Milestone4)


## Table of Contents
- [Description](#description)
- [Installation](#installation)
- [Usage](#usage)
- [File Structure](#file-structure)
- [License](#license)

## Description
The Hangman Game is a Python implementation of the classic word guessing game. In this game, the player tries to guess a hidden word by suggesting letters one at a time. The game provides feedback on the correctness of the guesses, and the player has a limited number of incorrect guesses before the game is over.

### Aim of the Project
The aim of this project is to create an interactive console-based Hangman game that allows players to guess letters and receive feedback on their guesses. This project helps in understanding and applying basic Python programming concepts such as loops, conditionals, functions, and classes.

```
import random

class Hangman:
    def __init__(self, word_list, num_lives=5):
        """
        Initialize the Hangman game attributes.

        Parameters:
        word_list (list): List of words to choose from.
        num_lives (int): Number of lives the player has. Default is 5.
        """
        self.word_list = word_list
        self.num_lives = num_lives
        self.word = random.choice(word_list)
        self.word_guessed = ['_'] * len(self.word)
        self.num_letters = len(set(self.word))
        self.list_of_guesses = []


    def check_guess(self, guess):
        """
        Check if the guessed letter is in the secret word.

        Parameters:
        guess (str): The letter guessed by the user.

        Returns:
        None
        """
        guess = guess.lower()
        if guess in self.word:
            print(f"Good guess! {guess} is in the word.")
         # Update word_guessed to reveal the correct guess
            for i, letter in enumerate(self.word):
                if letter == guess:
                    self.word_guessed[i] = guess
            # Decrease num_letters by 1
            self.num_letters -= 1
        else:
            self.num_lives -= 1
            print(f"Sorry, {guess} is not in the word. Try again.")
            print(f"You have {self.num_lives} lives left.")
        print(f"Current word: {' '.join(self.word_guessed)}")

    def ask_for_input(self):
        """
        Prompt the user to guess a letter and validate the input.

        This method continuously asks the user for a guess until a valid single alphabetical character
        is provided. Once a valid guess is made, it checks the guess against the secret word.

        Returns:
        None
        """
        while True:
            guess = input("Guess a letter: ")

            if not guess.isalpha() or len(guess) != 1:
                print("Invalid letter. Please, enter a single alphabetical character.")
            elif guess in self.list_of_guesses:
                print("You already tried that letter!")
            else:
                self.check_guess(guess)
                self.list_of_guesses.append(guess)
                break


word_list = ['Apple', 'Mango', 'Peach', 'BlackGrape', 'Pineapple']
game = Hangman(word_list)
game.ask_for_input()
```

# Milestone5
```
    def check_guess(self, guess):
        """
        Check if the guessed letter is in the secret word.

        Parameters:
        guess (str): The letter guessed by the user.

        Returns:
        None
        """
        guess = guess.lower()
        if guess in self.word:
            print(f"Good guess! {guess} is in the word.")
            # Update word_guessed to reveal the correct guess
            for i, letter in enumerate(self.word):
                if letter == guess:
                    self.word_guessed[i] = guess
            # Decrease num_letters by 1
            self.num_letters -= 1
        else:
            self.num_lives -= 1
            print(f"Sorry, {guess} is not in the word.")
            print(f"You have {self.num_lives} lives left.")
        print(f"Current word: {' '.join(self.word_guessed)}")

    def ask_for_input(self):
        """
        Prompt the user to guess a letter and validate the input.

        This method continuously asks the user for a guess until a valid single alphabetical character
        is provided. Once a valid guess is made, it checks the guess against the secret word.

        Returns:
        None
        """
        while True:
            guess = input("Guess a letter: ")

            if not guess.isalpha() or len(guess) != 1:
                print("Invalid letter. Please, enter a single alphabetical character.")
            elif guess in self.list_of_guesses:
                print("You already tried that letter!")
            else:
                self.check_guess(guess)
                self.list_of_guesses.append(guess)
                break

def play_game(word_list):
    """
    Run the Hangman game.

    Parameters:
    word_list (list): List of words to choose from.

    Returns:
    None
    """
    num_lives = 5
    game = Hangman(word_list, num_lives)
    
    while True:
        if game.num_lives == 0:
            print('You lost!')
            break
        elif game.num_letters > 0:
            game.ask_for_input()
        else:
            print('Congratulations. You won the game!')
            break

# Example usage:
if __name__ == "__main__":
    word_list = ['Apple', 'Mango', 'Peach', 'BlackGrape', 'Pineapple']
    play_game(word_list)
```

# Hangman
Hangman is a classic game in which a player thinks of a word and the other player tries to guess that word within a certain amount of attempts.
