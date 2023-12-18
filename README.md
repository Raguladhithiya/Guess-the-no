#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
    int numberToGuess, playerGuess, attempts = 0;
    
    // Seed the random number generator with the current time
    srand(time(NULL));
    
    // Generate a random number between 1 and 100
    numberToGuess = rand() % 100 + 1;
    
    printf("Welcome to the Number Guessing Game!\n");
    
    do {
        // Get player's guess
        printf("Enter your guess (between 1 and 100): ");
        scanf("%d", &playerGuess);
        
        // Increment the attempts counter
        attempts++;
        
        // Check if the guess is correct, too low, or too high
        if (playerGuess == numberToGuess) {
            printf("Congratulations! You guessed the number in %d attempts.\n", attempts);
        } else if (playerGuess < numberToGuess) {
            printf("Too low! Try again.\n");
        } else {
            printf("Too high! Try again.\n");
        }
        
    } while (playerGuess != numberToGuess);

    return 0;
}
