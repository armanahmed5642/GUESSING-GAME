# GUESSING-GAME
import random

def play_guessing_game():
    print("====================================")
    print("🎯 WELCOME TO THE NUMBER GUESSING GAME! 🎯")
    print("====================================")
    print("I am thinking of a number between 1 and 100.")
    
    # Generate a random secret number
    secret_number = random.randint(1, 100)
    attempts = 0
    
    while True:
        # Get input from the user safely
        user_input = input("\nEnter your guess (or type 'quit' to exit): ").strip()
        
        # Check if the user wants to give up
        if user_input.lower() == 'quit':
            print(f"👋 Giving up so soon? The number was {secret_number}. Better luck next time!")
            break
            
        # Validate that the input is a number
        try:
            guess = int(user_input)
        except ValueError:
            print("❌ Invalid input! Please enter a valid whole number.")
            continue
            
        # Increment attempt counter
        attempts += 1
        
        # Check the user's guess against the secret number
        if guess < 1 or guess > 100:
            print("⚠️ Out of bounds! Please guess a number between 1 and 100.")
        elif guess < secret_number:
            print("📈 Too low! Try a higher number.")
        elif guess > secret_number:
            print("📉 Too high! Try a lower number.")
        else:
            print(f"🎉 CONGRATULATIONS! You found the number {secret_number} in {attempts} attempts!")
            break

if __name__ == "__main__":
    play_guessing_game()
