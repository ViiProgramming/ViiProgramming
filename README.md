#include <iostream>
#include <cstdlib>  // Required for rand() and srand()
#include <ctime>  //Required for time()

int main() {
  srand(time(0));  // Seed the random number generator with the current time

  int secretNumber = rand() % 100 + 1;  // Generate a random number between 1 and 100

  int guess;
  int attempts = 0;  // Initialize the attempts counter

  std::cout << "Welcome to the Number Guessing Game! Try to guess the secret number between 1 and 100." << std::endl;

  while (true) {  // Infinite loop until the correct guess is made
    std::cout << "Enter your guess: ";
    std::cin >> guess;  // Read player's guess

    attempts++;  // Increase the number of attempts

    if (guess == secretNumber) {  // Check if the guess is correct
        std::cout << "Congratulations! You guessed the number " << secretNumber << " in " << attempts << " attempts." << std::endl;
        break;  // Exit the loop when the correct guess is made
    } else if (guess < secretNumber) {
        std::cout << "Too low. Try again." << std::endl;  // Provide feedback for a low guess
    } else {
        std::cout << "Too high. Try again." << std::endl;  // Provide feedback for a high guess
    }
  }

  return 0;
}
