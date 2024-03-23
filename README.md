import random

def generate_computer_choice():
    return random.choice(["rock", "paper", "scissors", "lizard", "Spock"])

def determine_winner(player_choice, computer_choice):
    if player_choice == computer_choice:
        return "It's a tie!"
    elif (player_choice == "rock" and (computer_choice == "scissors" or computer_choice == "lizard")) or \
         (player_choice == "paper" and (computer_choice == "rock" or computer_choice == "Spock")) or \
         (player_choice == "scissors" and (computer_choice == "paper" or computer_choice == "lizard")) or \
         (player_choice == "lizard" and (computer_choice == "paper" or computer_choice == "Spock")) or \
         (player_choice == "Spock" and (computer_choice == "rock" or computer_choice == "scissors")):
        return "Player wins!"
    else:
        return "Computer wins!"

def play_game():
    print("Welcome to Rock-paper-scissors-lizard-Spock!")
    player_choice = input("Enter your choice (rock, paper, scissors, lizard, or Spock): ").lower()
    if player_choice not in ["rock", "paper", "scissors", "lizard", "Spock"]:
        print("Invalid choice! Please choose from rock, paper, scissors, lizard, or Spock.")
        return
    computer_choice = generate_computer_choice()
    print("Computer chooses:", computer_choice)
    print(determine_winner(player_choice, computer_choice))

play_game()
