# README - Hangman Game in C++

## Overview

This project is a simple console-based Hangman game developed in C++. The game randomly selects a word, and the player must guess the word one letter at a time before running out of attempts.

The project is designed for beginners to practice fundamental programming concepts such as loops, conditions, arrays/strings, functions, and game logic in C++.


# Features
* Random word generation
* Letter-by-letter guessing system
* Tracks correct and incorrect guesses
* Displays remaining attempts
* Prevents repeated guesses
* Win and lose conditions
* Simple console-based interface


# Concepts Used
This project demonstrates the following C++ concepts:
* Variables and Data Types
* Conditional Statements (`if`, `else`)
* Loops (`for`, `while`)
* Arrays / Strings
* Functions
* Random Number Generation
* Input and Output (`cin`, `cout`)
* Basic Game Logic


# How the Game Works
1. The program randomly selects a word from a predefined list.
2. The hidden word is displayed using underscores (`_`).
3. The player guesses one alphabet at a time.
4. If the guessed letter exists in the word:

   * The letter is revealed.
5. If the guessed letter is incorrect:

   * The player loses one attempt.
6. The game continues until:

   * The player guesses the full word, or
   * The player runs out of attempts.


# Example Gameplay

```bash
Word: _ _ _ _ _
Guess a letter: a

Correct Guess!

Word: a _ _ _ _
Remaining Attempts: 5
```

---

# File Structure

```bash
hangman.cpp   # Main source code file
README.md     # Project documentation
```

---

# How to Run

## Compile the Program

```bash
g++ hangman.cpp -o hangman
```

## Run the Program

```bash
./hangman
```

--

# Requirements
* C++ Compiler (G++, MinGW, or any standard C++ compiler)
* Terminal / Command Prompt

# Learning Outcomes
By building this project, you can learn:
* Basic game development logic
* Problem-solving in C++
* Working with strings and loops
* Handling user input
* Writing interactive console applications
  
# Future Improvements
Possible upgrades for this project:
* Difficulty levels
* Categories for words
* ASCII hangman graphics
* Multiplayer mode
* Score system
* File handling for word storage
