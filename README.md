# game-development


import random
import time

# Function to display the grid
def display_grid(mole_position):
    grid = ['[ ]' for _ in range(9)]  # Create a 3x3 grid (9 positions)
    grid[mole_position] = '[M]'  # Place the mole at the random position
    for i in range(0, 9, 3):  # Print in 3x3 grid format
        print(" ".join(grid[i:i+3]))

# Function to play the game
def play_game():
    print("Welcome to Whack-a-Mole!")
    print("Try to hit the mole by entering the number (1-9) where it appears.")
    print("The game will last for 30 seconds.")
    print("You can whack the mole by typing the number where it appears in the grid.")
    
    # Set the game timer
    start_time = time.time()
    time_limit = 30  # 30 seconds to play
    score = 0

    while time.time() - start_time < time_limit:
        # Randomly choose mole's position (0 to 8, representing grid positions 1 to 9)
        mole_position = random.randint(0, 8)
        display_grid(mole_position)

        # Get player input
        try:
            user_input = int(input("Whack the mole! Enter a number (1-9): "))
            if 1 <= user_input <= 9:
                if user_input - 1 == mole_position:
                    score += 1
                    print("You hit the mole!")
                else:
                    print("Missed! Try again.")
            else:
                print("Invalid input. Please enter a number between 1 and 9.")
        except ValueError:
            print("Invalid input. Please enter a valid number.")

        print(f"Your current score: {score}")
        print("-" * 30)

    print(f"Time's up! Your final score is: {score}")
    print("Thanks for playing Whack-a-Mole!")

if name == "main":
    play_game()

    
“Thrilled to share my first step into Python game development! 🚀 Just brought an exciting idea to life, combining creativity, problem-solving, and lots of learning.  Introducing my latest project: a Whack-a-Mole game built with Python and Pygame!   #Python #GameDevelopment #WhackAMole #LearningJourney”
