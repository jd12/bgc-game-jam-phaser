# Game Jam Phaser

## Overview 

You will build a game where the goal is to collect the pigcats. The pigcats will switch between dangerous and safe. If you collect all the pigcats, you win. If you're health goes down to zero, you lose. You will also build in start, win, and lose screens. 

## Part I - Setup

Go to plnkr.co and click "Launch Editor"

![Initial Project](images/plunker_initial.png)

Edit your `index.html` to look like below

![Initial Index](images/index_html.png)

Delete `script.js` and create a new file named `game.js`. Your window should look like this. 

![Empty Game JS](images/empty_game_js.png)

### Create Initial Variables

Variables are useful for storing data that may change during the game (e.g. your player’s hitPoints).

To create a variable, you have to tell JavaScript:

- The name you’re going to refer to it by
- The value (information) that the variable contains

You only have to declare the variable once. Then you can use it wherever you need.

Let's create a few variables. 

![Initial Variables](images/initial_variables.png)

Global means the variables can be used anywhere in our `game.js` file.

Copy and paste the below variables below your intial ones. 

```js
// Links to images
var skyImage = 'https://i.imgur.com/ZCWqpAc.png';
var playerSprites = 'http://i.imgur.com/ODpjVpQ.png';
var pigcatSprites = 'https://i.imgur.com/ut53em3.png';
```

Your `game.js` file should look like this: 

![Image Links](images/image_links.png)

### Preload Function

So in code, we have things called functions. Functions allow us to group our code together and makes our code manageable. Phaser has special functions that it looks for in creating our game. One of them is `preload`, which it uses to set up our game. Create preload function like the one below in your `game.js` below your global variables.

![Preload Initial](images/preload_initial.png)

### Create functions

Phaser uses the `create()` function to create all the objects in our game.
Add this function below the `preload()` function.

![Create Initial](images/create_initial.png)

Everytime we want to add an object to the game, we’ll add a new line  to this function.

Your `game.js` file should look like this now:

![Game JS](images/game_js_create.png)

### Set up game object

We need to do one final step to finish loading the game. We need to set up a game object to tell Phaser how to load our game. Add this to the top of your code under `// GLOBAL VARIABLES`:

![Game Object](images/game_object.png)

### Initial Sky Image

Go ahead and click the `Run` button. You should get something like this:

![Initial Sky](images/initial_sky.png)

## Part II - Game Start

Let's add a `startGame` function below the create function

![Start Game](images/start_game.png)

Now let's update our `create` function to call our `startGame` function

![Create Start Game](images/create_start_game.png)

We'll utilize this functionality to start our game when we click the screen.

## Part III - Animations and Sprites

Let's add our player to the game. Update your `preload` and `create` functions like so: 

![Heroine](images/heroine.png)

When you run your code, you should get something like this:

![Heroine](images/heroine_on_screen.png)

Great job! Now let's animate our player. 

Update your create function to add images from our spritesheet to make it appear our player is walking.

![Walking Animations](images/walking_animations.png)

### Player Movement

We want our player to move when we press the arrow keys. In our `create` function we need to set up our game to listen for keyboard presses.

![Create Keyboard](images/create_keyboard.png)

Phaser has another special function called `update`. It calls `update` once every millisecond. We can utilize this function to have our player respond to key presses. Create an `update` function at the bottom of your `game.js` file. 

![Update Initial](images/update_initial.png)

It's ok if the left and right in your `keyboard.left` and `keyboard.right` doesn't turn green.

Now we need to update our game object to utilize our update object.

![Update Game Object](images/update_game_object.png)

Run your code and you should be able to turn your character left and right 

![Heroine Left](images/heroine_left.png)

### Challenge 

Can you update the code to add keypresses for up and down? 

Afterwards, you should be able to turn your player in all 4 directions.

### Moving your Player

Now let's make the player actually move across the screen when we press the arrow keys. Update your `update` function to:

![Moving Update](images/moving_update.png)

You should now be able to move left and right. Update your code so that you can move up and down (Remember that moving up and down means changing the y position of your player instead of the x).

## Adding Enemies

Let's add enemies to our game. 

First, we need to update our `preload()` function 

![Enemy Preload](images/enemy_preload.png)

Then we'll update our create function so that we set up our enemies in the game. 

![Enemy Create](images/enemies_create.png)

Then we'll create a function that lets us create enemies randomly. You can copy and paste the below code at the bottom of your `game.js` file.

```js
function createEnemies() {
	var enemy = enemies.create(
(Math.random() * game.world.width), ((Math.random() * game.world.height) - 32), 'baddie');
}
```

You should be able to Run your game and when you click on the screen, you should see a pigcat pop up. 

![Enemy Create](images/enemy_onscreen.png)
