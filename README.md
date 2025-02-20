Abstract

This report outlines the development process of the game "Lost in the Maze: A PYGAME Adventure," a 2D maze navigation game. It covers the game's concept, design, implementation, and the challenges encountered during development. The report aims to provide a comprehensive overview that enables understanding and playing the game without direct access to its source code.

Table of Contents

Introduction to my Game

Modules

Directory Structure

Running Instructions

Prerequisites

Game Navigation and Gameplay

Various Implementations in the Code

Customizations in the Game

References

Introduction to my Game

This game aims to complete the levels of The Horse Castle as quickly as possible. The high scores equivalent - Least Time Taken are also based on this.

Modules

The external modules used are:

pygame-ce - The frequently updated pygame community edition version of pygame is a set of Python modules designed for writing video games.

Random - A module that implements pseudo-random number generators for various distributions.

Sys - A module that provides access to some variables used or maintained by the interpreter and functions that interact with the interpreter.

Time - A module that provides various time-related functions.

os - A module that provides a portable way of using operating system-dependent functionality.

heapq - A module that implements heap queues. I used this module to implement the priority queue for the A* algorithm.

Directory Structure

The project directory is as follows:

.
├── Modules
│   ├── MainMenu.py
│   ├── PlayGame.py
│   ├── Preferences.py
│   └── Scores.py
├── media
│   ├── fonts
│   ├── images
│   ├── sounds
│   └── videos
├── data
│   ├── path.txt
│   └── LeastTimes.txt
├── game.py
└── settings.py

game.py - The main game loop.

settings.py - Contains all the global variables and modules necessary for the game to function smoothly.

Modules - The programs that manage various game parts.

media - Contains all the images, sounds, and fonts used in the game.

data - Contains the path of the castle levels and the High ScoreCard (Least Time Taken).

Running Instructions

Prerequisites

Note: It is assumed that Python is already installed.

Setting up venv

python -m venv venv
python -m pip install -r dependencies.txt

To run the game, use The Horse Castle executable.

./HorseCastle

Game Navigation and Gameplay

Note: To ensure easy navigation between various screens, a back button is introduced which smoothly takes you to the previous screen.

Intro Screen

The game starts with an Intro Screen:



Main Menu

After loading, you will be greeted with a Main Menu, from which you can choose to:

Play

See the Fastest Solves in each Level

Customize the Game: Mute or Unmute

Quit

You can select any of these by pressing on these buttons:



Game Level Selection

We have three levels of the castle from which you can choose:



The Game!

The game starts, waiting for you to navigate using the arrow keys or [W A S D]. The goal is to reach the castle exit in the opposite corner. The Score is measured in terms of the time taken to go to the opposite end: the Lower, the Better!

Various themes can be changed using the Change Theme button. The music can be turned off by pressing the Music button.

Some examples of the game screens:





Game Over

On reaching the opposite end, the game ends, and the time taken is displayed:



Fastest Solves

On clicking the Fastest Solves button on the Main Menu, you will see the Least Time taken to solve the various levels of The Horse Castle. An example screen:



Preferences

This window enables you to mute the music part of the game. You can do this by clicking on the red music button. If you want the music back on, click the button again.





Quit

On clicking this button, the game ends and the program terminates.

Various Implementations in the Code

For the castle navigation, I used the Recursive Backtracking algorithm. This algorithm is a randomized version of the depth-first search algorithm. The algorithm starts at a random room, chooses a random neighboring room that has not been visited, creates a path between the two rooms, and moves to the next room. The algorithm continues until it has visited every room in the castle. I have modified this algorithm slightly to make the wall size and the path size the same, which makes the castle look more appealing.

For the pathfinding, I used the A* algorithm. The A* algorithm is a pathfinding algorithm that uses a heuristic to determine the next node to visit in a graph. The algorithm uses a priority queue to determine the next node to visit based on the cost of the path to that node and the heuristic value of the node. The algorithm continues until it reaches the goal node or there are no more nodes to visit.

I have used the heapq module to implement the priority queue for the A* algorithm.

For the pygame functions, I referred to the official documentation of pygame and pygame-ce, mostly the latter for the updated functions and methods.

Customizations in the Game

A list of all the special customizations implemented in the game:

Animation is when the player moves.

Dynamic Background of the Main Menu.

Music and Sound.

Themes for the Game.

High Scores.

Preferences.

Back Button for easy navigation.

Customized Fonts.

Responsive Buttons.

References

Pygame Official Documentation

Pygame CE Official Documentation

Maze Generation Algorithms by professor-l

A* Algorithm

