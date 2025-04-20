# Reversi Project README
Declan Javers    
4/20/2025 


## Table of Contents
 
- **Overview:** An overview of this Reversi project 
- **How to Play** The rules of Reversi
- **Features:** Specifications for this Reversi project 
- **Command Line Arguments:** The format of the command line arguments to run this game
- **Set up:** How to run this project
- **State of the Game:** The development update on the game and suggestions for improvement 
- **FAQ:** Get help in the frequently asked questions section 

![Screen Recording 2025-04-20 at 6 50 50 PM](https://github.com/user-attachments/assets/5376dad7-f42b-498a-a3ed-5f2200ca2bfd)

## Overview 

This README provides details on my final project for Northeastern University's CS3500, Object Oriented Design, an implementation of the board game Reversi. This project, aimed to test students' familiarity with design patterns as well as encapsulation and inheritance, was completed over a few weeks in the Fall 2024 semester. 

Reversi is a two player board game where players take turns placing pieces on the board. On your turn, if you place your piece in a line with another one of your pieces and there are opponent pieces in between, “sandwiching” your opponent pieces, you capture the pieces in between and they become your pieces. The goal is to capture more pieces than your opponent.  

- This implementation utilizes Model-View-Controller Architecture to manage the game rules and visualization, while letting each player control their board. 
- The design has unique models for each board type, allowing for flexibility in the design. 
Java Swing is used to visualize the game in order to create an accurate, efficient GUI.
- The game object keeps track of coordinates in three dimensions for the hexagonal implementation, represented as (q, r, s) as opposed to the (x, y) systems of the square design.

<img width="603" alt="image" src="https://github.com/user-attachments/assets/e8029209-4d97-4fc1-bd25-3fc82622d591" />

## How to Play

- **Goal:** To win, a player must have more of their pieces on the board than their opponent when the game ends.
- **Game Ending** The game ends when all playable spaces are filled.
- **Game Play:** Players take turns placing a piece on the board adjacent to an existing piece. 
- **Capturing** If a newly placed piece creates a row or column such that there are opponent pieces sandwiched between two of the moving player's pieces, the opponent pieces in the middle are captured and replaced with pieces of the moving player's color.

<img width="598" alt="image" src="https://github.com/user-attachments/assets/41570da7-0791-45dc-93bc-1b2fb7bced26" />

## Features 

This implementation of Reversi allows for several configurations: 

- **Piece Shapes** 
    - **Hexagonal:** The board will have hexagonal pieces for a traditional experience. Hexagonal boards are fixed at six pieces aside.
    - **Square:** The board will be made up of square pieces, changing the dynamic of the game. Square games can have custom board sizes, with the minimum side length being 4.

* **Players**
    * **Single Player:** The game allows one user to play against an AI agent. The player may select to play with or without hints enabled. 
    * **Two Players**: The game may be set up with two local players. Each player will be able to choose to allow hints, and each player will receive their own window to play their moves. 

- **Hints** 
    - When enabled, users may click cells without placing pieces. Instead of placing a piece on that cell, a number will appear representing how many pieces the user would capture if moving to that place. 

## Command Line Arguments

The command to run the game follows this structure:

```sh  
java -cp bin cs3500.reversi.Reversi <game_type> <size> <player1_type> <player1_hints> <player2_type> <player2_hints>
```
- **game_type:** Must be one of either hexagon or square.
- **size:** An integer, must be larger than 4.
- **player_types:** Must be either AI or human.
- **player_hints:** Either true for hints, or false. Skip this argument for an AI player.


## Set up 

By following these instructions, you can download and run this project on your computer: 

1. **Prerequisites** 

   You must have java installed to run this project. If you do not have java, download it from the [Java website](https://www.java.com/en/download/).
 

2. **Clone the repository** 

   Open your command line and run this command to download this project to your device. 

   ```sh 
   git clone git@github.com:DeclanJavers/Reversi.git

   cd reversi 

3. **Compile the code** 

   Compile the code by running this command to get an executable file. 

    ```sh 
    javac -d bin src/cs3500/reversi/*.java src/cs3500/reversi/*/*.java 
 

4. **Run the game** 

   Set up the game using command line arguments and run the executable using this command. 

    ```sh 
    java -cp bin cs3500.reversi.Reversi hexagon human true ai false

## State of the game 

This project is finished and no further updates are planned to be released. However, there are several ways I would suggest improving the game: 

- **Enhanced AI Players:** Implementing additional players, increased difficulty levels, and different AI play styles would result in a more engaging experience.
- **Upgraded UI:** The current UI is simplistic and built entirely in Java Swing, which leads the game to look a bit rudimentary. A better UI system would provide a nice visual upgrade. 
- **Different Rules:** Adding unique rules would increase the game's replayability and could provide interesting challenges for players.

<img width="624" alt="image" src="https://github.com/user-attachments/assets/f88f7030-dcaa-4af2-a642-74850d8dcfe1" />

## FAQ 

<details> 

  <summary>What board options should I start with?</summary> 

  Reversi is traditionally played with hexagonal pieces, so if you want the traditional experience, start by using hexagonal pieces. However, if you want a simpler start, select square pieces. 

</details> 
 
<details> 

  <summary>How does the AI player move?</summary> 

  The AI will always select the move that wins the most pieces that turn. This is a good strategy, but not the best! 

</details> 

<details> 

  <summary>How does the program respond to invalid command line arguments?</summary> 

  The program throws an error, prompting the user to enter a valid command line argument.

</details> 

 <details> 

  <summary>Can I toggle if hints are allowed mid-game?</summary> 

  No, once a setting is chosen the user will not be able to toggle it during a game.

</details>
