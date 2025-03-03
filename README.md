# Snake-game
Introduction :
The Snake Game is one of the most well-known arcade games, having its roots in the late 1970s and 1980s. It gained immense popularity with its release on early mobile phones, particularly the Nokia models, where it became a staple game for millions of users worldwide. The premise of the Snake Game is simple yet highly engaging: the player controls a snake that moves around the screen, consuming food items that appear randomly. Each time the snake consumes a piece of food, it grows longer, and the player’s score increases. The game continues until the snake either collides with the screen’s boundaries or with itself, at which point the game is over.

The Snake Game has been a classic example of how minimalistic gameplay, simple controls, and an intuitive interface can lead to addictive gameplay. It not only provides a fun way to pass time but also enhances the player’s reflexes and strategic thinking. As the snake grows longer, maneuvering it without crashing becomes more challenging, requiring quick decision-making and hand-eye coordination.

This project involves implementing the Snake Game using C++, a powerful and widely-used programming language known for its performance and control over system resources. The game is created using the graphics.h library, which provides a simple way to create graphical interfaces, making it suitable for beginners who are learning C++ and want to venture into game development. In this version of the Snake Game, the snake and the food are visually represented as blocks—a white block for the snake and a red block for the food. Players control the snake’s movement using the keyboard: ‘W’ for up, ‘A’ for left, ‘S’ for down, and ‘D’ for right.

The game integrates basic collision detection to check whether the snake has hit the walls or collided with itself. Additionally, the game dynamically updates the score based on the number of fruits eaten by the snake, providing a clear indication of the player’s progress. This project serves as an excellent introduction to game development fundamentals, such as handling user input, managing game state, and rendering graphics on the screen.

By creating this game, you will gain experience in using basic C++ concepts like loops, conditionals, and functions while also learning about graphics programming, memory management, and real-time processing. Additionally, you will become familiar with common game development concepts such as collision detection, dynamic object management, and scorekeeping, all of which are crucial for building more complex games in the future. This project is an ideal starting point for aspiring game developers looking to develop their skills and build a portfolio.

Modules or Packages required:
graphics.h:
Responsible for graphical output. It allows us to draw various geometric shapes and text on a window, which is essential for rendering game elements and the interface.

conio.h:
Provides useful keyboard input functions, such as kbhit() and getch(), which are used to detect key presses in real-time to control the snake.

stdlib.h:
 Standard library for various general-purpose functions like dynamic memory allocation and random number generation.

stdio.h:
Standard I/O functions for handling input and output operations.

time.h:
Used for time manipulation and generating random numbers, which is crucial for placing the fruits at random positions.


How to run the code :-
Install a compatible C++ compiler and the graphics library.

Download or clone the project repository from GitHub.

Open a terminal or command prompt and navigate to the project directory.

Compile the code using a C++ compiler. For example:

g++ -o snake_game snake_game.cpp -lgraph

Run the executable file to start the game:

 
./snake_game


Explanation of Code :
The code is structured into several main functions:

start(): Initializes the game window and sets up the initial game state, including drawing the boundary and placing the first fruit.

update(): Called in every frame to update the game’s state, move the snake, check for collisions, and refresh the graphics.

move(): Handles the snake’s movements based on user input, modifying the direction. It also prevents the snake from turning back directly on itself.

graphic(): Redraws the game window with the snake, fruit, and score to refresh the game display.

fruit(): Manages the generation and placement of the fruit. It also checks if the snake has eaten the fruit and updates its length and score accordingly.

Below is the key part of the move() function that handles the snake’s movement:

void move() {
    if (kbhit()) {
        direc = getch();
    }

    // Prevent the snake from moving directly back onto itself
    if ((direc == 'w' && last == 's') || (direc == 's' && last == 'w') ||
        (direc == 'a' && last == 'd') || (direc == 'd' && last == 'a')) {
        direc = last;
    }

    last = direc;

    // Update snake position based on the direction
    if (direc == 's') {
        y1 += 10;
    } else if (direc == 'a') {
        x1 -= 10;
    } else if (direc == 'w') {
        y1 -= 10;
    } else if (direc == 'd') {
        x1 += 10;
    }
}

This function reads keyboard input to change the direction of snakes and prevents the snake from moving in reverse directly. 
