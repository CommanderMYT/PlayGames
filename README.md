# PlayGames
Classic Games Hub
A single-page web application featuring 25 classic games, built with HTML, JavaScript, p5.js, and styled with Tailwind CSS. The site displays a 5x5 grid of game tiles, allowing users to select and play games in a canvas. Currently, 9 games are fully implemented, with placeholders for the remaining 16, ready for further development.
Features

25 Classic Games: Includes Tetris, Snake, Pong, Breakout, Tic-Tac-Toe, Pac-Man, Space Invaders, Asteroids, Galaga, and 16 placeholder games (Frogger, Centipede, Minesweeper, Connect Four, Battleship, Othello, Checkers, Chess, Solitaire, FreeCell, Arkanoid, Dig Dug, Q*bert, Tetris Attack, Bubble Bobble, Donkey Kong).
Responsive Design: Works on desktop and mobile devices using Tailwind CSS.
Interactive Interface: Click a game tile to play, with instructions displayed below the canvas.
Lightweight: Uses CDNs for p5.js and Tailwind CSS, making it ideal for static hosting on GitHub Pages.
Modular Code: Each game is a p5.js sketch, easy to extend or modify.

Implemented Games

Tetris: Move falling blocks with LEFT/RIGHT, rotate with UP, drop faster with DOWN, instant drop with SPACE. Clear lines to score.
Snake: Use ARROW keys to move, eat red apples to grow, avoid walls and self.
Pong: Move left paddle with UP/DOWN, play vs. AI, first to 5 wins.
Breakout: Move paddle with LEFT/RIGHT, bounce ball to break bricks.
Tic-Tac-Toe: Click cells to place X, play vs. random AI (O), get three in a row.
Pac-Man: Use ARROW keys to move, eat dots, avoid ghosts in a small maze.
Space Invaders: Move with LEFT/RIGHT, shoot with SPACE, destroy aliens.
Asteroids: Rotate with LEFT/RIGHT, thrust with UP, shoot with SPACE, avoid asteroids.
Galaga: Move with LEFT/RIGHT, shoot with SPACE, destroy enemy waves.

Placeholder Games
The following games are included as placeholders with a basic sketch displaying "Game not yet implemented":

Frogger, Centipede, Minesweeper, Connect Four, Battleship, Othello, Checkers, Chess, Solitaire, FreeCell, Arkanoid, Dig Dug, Q*bert, Tetris Attack, Bubble Bobble, Donkey Kong.
Each has a template sketch (sketchTemplate) ready for implementation.

Setup and Hosting
Prerequisites

A GitHub account.
Git installed (optional, for command-line deployment).
The index.html file from this repository.

Hosting on GitHub Pages

Create a Repository:

Go to github.com and create a new repository named <your-username>.github.io for a user site (e.g., johndoe.github.io) or any name (e.g., classic-games-hub) for a project site.
Set it to Public and initialize with a README.


Upload Files:

Command Line:cd path/to/classic-games-hub
git init
git add index.html
git commit -m "Initial commit with Classic Games Hub"
git remote add origin https://github.com/<your-username>/<repository-name>.git
git push -u origin main


GitHub Website:
Go to your repository, click Add file > Upload files, and upload index.html.
Commit with a message like "Add index.html".




Enable GitHub Pages:

In the repository, go to Settings > Pages.
Set Source to Deploy from a branch, select main (or master), and choose / (root).
Save. The site will be live at https://<your-username>.github.io or https://<your-username>.github.io/<repository-name>.


Test the Site:

Visit the URL (e.g., https://johndoe.github.io/classic-games-hub).
Click game tiles to play and verify functionality.
Ensure JavaScript and WebGL are enabled in your browser for p5.js.



Extending Placeholder Games
To implement the remaining 16 games:

Create a New Sketch:

Copy the sketchTemplate function in index.html and rename it (e.g., sketchFrogger).
Define game state (e.g., player position, enemies, score).
Implement p.setup for canvas setup and initial state.
Implement p.draw for rendering and updating game state.
Add input handling (e.g., p.keyPressed or p.mousePressed).


Update Game List:

In the games array, set implemented: true for the game.
Update the sketches object in loadGame to map the game ID to the new sketch.


Example Pseudocode for Frogger:
const sketchFrogger = (p) => {
  let player = { x: 200, y: 380 };
  let cars = [{ x: 0, y: 300, dx: 2 }, ...];
  p.setup = () => { p.createCanvas(400, 400); };
  p.draw = () => {
    p.background(0);
    cars.forEach(car => { car.x += car.dx; /* Wrap around */ });
    if (/* player hits car */) { /* Game over */ }
    if (player.y < 50) { /* Win condition */ }
    p.fill(0, 255, 0); p.rect(player.x, player.y, 20, 20);
    cars.forEach(car => { p.fill(255, 0, 0); p.rect(car.x, car.y, 30, 20); });
  };
  p.keyPressed = () => {
    if (p.keyCode === p.UP_ARROW) player.y -= 40;
    // Handle other directions
  };
};


Resources:

Use the p5.js reference for graphics and input.
Study existing games (e.g., Pac-Man, Breakout) for patterns.
Check open-source game tutorials on GitHub for inspiration.



Contributing

Fork the repository and submit pull requests to add new game implementations or improve existing ones.
Focus on lightweight code to stay within GitHub Pages’ 1GB limit.
Test games for browser compatibility (Chrome, Firefox recommended).

Troubleshooting

Site Not Loading: Ensure index.html is in the repository root and GitHub Pages is enabled.
Games Not Working: Verify JavaScript is enabled and check the browser console for errors (e.g., CDN failures).
Performance Issues: Optimize game logic to reduce lag, especially for complex games like Chess or Solitaire.

License
This project is open-source under the MIT License. Feel free to use, modify, and distribute.
