#include <iostream>
#include <string>
#include <cstdlib>
#include <ctime>

using namespace std;

// Function to print the current state of the hangman gallows
void drawHangman(int wrongGuesses) {
    cout << "\n";
    cout << "  +---+\n";
    cout << "  |   |\n";
    cout << "  " << (wrongGuesses >= 1 ? "O" : " ") << "   |\n";
    cout << " " << (wrongGuesses >= 3 ? "/" : " ") << (wrongGuesses >= 2 ? "|" : " ") << (wrongGuesses >= 4 ? "\\" : " ") << "  |\n";
    cout << " " << (wrongGuesses >= 5 ? "/" : " ") << " " << (wrongGuesses >= 6 ? "\\" : " ") << "  |\n";
    cout << "     ===\n";
    cout << "\n";
}

int main() {
    // Seed the random number generator
    srand(static_cast<unsigned int>(time(0)));

    // A fixed array of secret words instead of a vector
    const int WORD_LIST_SIZE = 8;
    string wordList[WORD_LIST_SIZE] = {
        "programming", "computer", "developer", "algorithm", 
        "variable", "function", "pointer", "compiler"
    };

    // Pick a random word from the array
    string secretWord = wordList[rand() % WORD_LIST_SIZE];
    
    // Create a string filled with underscores to represent hidden letters
    string guessedWord(secretWord.length(), '_');

    int wrongGuesses = 0;
    const int maxGuesses = 6;

    // Fixed array to track guessed letters up to a maximum possible alphabet size
    char lettersGuessed[26];
    int uniqueGuessesCount = 0;

    cout << "=============================\n";
    cout << "    Welcome to C++ Hangman   \n";
    cout << "=============================\n";

    // Main game loop
    while (wrongGuesses < maxGuesses && guessedWord != secretWord) {
        drawHangman(wrongGuesses);
        
        // Display current progress with spaces for readability
        cout << "Word: ";
        for (int i = 0; i < guessedWord.length(); ++i) {
            cout << guessedWord[i] << " ";
        }
        cout << "\n";

        // Display previously guessed letters using a basic loop
        cout << "Guessed letters: ";
        for (int i = 0; i < uniqueGuessesCount; ++i) {
            cout << lettersGuessed[i] << " ";
        }
        cout << "\n";

        // Get player input
        cout << "Enter a letter: ";
        char guess;
        cin >> guess;
        guess = tolower(guess); // Ensure input is case-insensitive

        // Check if the letter was already guessed using a manual loop instead of std::find
        bool alreadyGuessed = false;
        for (int i = 0; i < uniqueGuessesCount; ++i) {
            if (lettersGuessed[i] == guess) {
                alreadyGuessed = true;
                break;
            }
        }

        if (alreadyGuessed) {
            cout << "\nYou already guessed '" << guess << "'. Try a different one!\n";
            continue;
        }

        // Add the new guess to our array track
        lettersGuessed[uniqueGuessesCount] = guess;
        uniqueGuessesCount++;

        // Check if the guessed letter is in the secret word
        bool found = false;
        for (int i = 0; i < secretWord.length(); ++i) {
            if (secretWord[i] == guess) {
                guessedWord[i] = guess;
                found = true;
            }
        }

        if (found) {
            cout << "\nGood guess!\n";
        } else {
            cout << "\nWrong guess!\n";
            wrongGuesses++;
        }
    }

    // End game screen
    drawHangman(wrongGuesses);

    if (guessedWord == secretWord) {
        cout << "?? Congratulations! You guessed the word: " << secretWord << "\n";
    } else {
        cout << "?? Game Over! The word was: " << secretWord << "\n";
    }

    return 0;
}
