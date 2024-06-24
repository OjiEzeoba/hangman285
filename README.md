# Milestone Project work

# Project Title: My Favourate Fruits Game Picker
This is a fruit game project aimed at developing a guessing game where a player thinks of his or her favourite fruit and the other player guess the friut name for a limited number of time.
Or the computer thinks of a world and the players/user tries to guess it.
## Table of Contents
- [Description](#description)
- [Installation](#installation)
- [Usage](#usage)
- [File Structure](#file-structure)
- [License](#license)

## Description

**FMy Favourate Fruits Game Picker** allows users to randomly select a fruit from a predefined list of favorite fruits. The project also includes input validation to ensure that user inputs are valid single alphabetical characters. This project demonstrates basic Python skills, including list manipulation, user input handling, and input validation.

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

favorite_fruits = ['Apple', 'Mango', 'Peach', 'Black Grape', 'Pineapple']
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

# Hangman
Hangman is a classic game in which a player thinks of a word and the other player tries to guess that word within a certain amount of attempts.

This is an implementation of the Hangman game, where the computer thinks of a word and the user tries to guess it. 
