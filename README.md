## This version of the user-doc doesn't contain images. I recommend using the version [here](https://docs.google.com/document/d/1maeaT1uglIzQWMiOX5FMbPA_QSzQ_XWwTwdjK9n_jf4/edit?usp=sharing).

# How to Use Scratch to Make a Version of Pong
## Difficulty: Fairly Easy

Table of Contents
- Prerequisites
- Setting up your project
- Adding sprites
- Gameplay
- Outro


# Prerequisites
To follow this tutorial, you at least need to be logged into Scratch. No other experience is needed. This tutorial is made for beginners to Scratch and is easy to follow along with. 

By the end of this tutorial, you’ll have learned how to create a project, create basic controls, make sprites move and bounce, use variables and create a basic main menu (if you choose to follow that part of the tutorial).

This tutorial is made with computer in mind, and controls for touchscreen won’t be covered in this tutorial. The tutorial works on every device with a (modern) browser, including iPad.

With that in mind, let’s get started.

# Setting Up Your Project
First, you’ll need to create a project. To do this, press the create button in the top bar.

Once you’ve created your project, you’ll be brought to the coding screen. This is where you’ll create your game, which in this case, is Pong.
You’ll start with a default character, known as a sprite, but we can remove this. Remove the cat by clicking the delete button.


And you’re ready to start creating!

# Adding Sprites
Adding sprites is easy. You have a few options to create sprites, which are all made available to you by hovering your mouse over the sprite adding button.



For this tutorial, I’ll be choosing a few premade sprites. Click the magnifying glass.


You’ll see the sprite selection screen. I’ll be choosing a ball and 2 lines.


After you’ve added the sprites into the project, it should look something like this: 


As you can see, the sprites are just randomly placed, and those lines are too long for what we are using them for, in which case are paddles for pong. To edit the selected sprite, click the ‘Costumes’ button.

Then, we can edit the sprite, in which case is the line. I made it shorter and thicker to make it more like a paddle.

Instead of making the edit to both of the lines, we can copy the edit and paste it on our other line sprite.


Next, we need to rotate the lines. Click the sprite to rotate and use the Direction box to rotate it. You can use the directional wheel, but the keyboard is more accurate for scenarios where you know the exact direction angle.

Then, click and drag the lines to their spots on the side of the screen.

Once you’ve done that, it’s time to start working on gameplay.

# Gameplay
## Moving The Paddles
Seeing as this version of Pong is multiplayer, we’ll need to create a control method for each paddle. For this tutorial, I’ll be using W and S for the left paddle, and Up Arrow and Down Arrow for the right paddle.

First, we need to make some broadcasts. A broadcast is an invisible message the average player can’t see, but other sprites can.

To move the left paddle, we need to create an action every time the W or S key is pressed. To do this, we need to go to the ‘Code’ section of our project and select the left line.


We need to make a forever action that starts when the green flag is clicked. To do this, go to the ‘Events’ section of the code blocks and drag in the ‘When [green flag] is clicked’ starting action.
Then, in the ‘Control’ section, find the ‘forever’ block and drag it under the green flag action we just added. The ‘forever’ block repeats the actions inside it infinitely while the program is running.
Next, we need to bring in 2 ‘if’ actions and drag them inside the ‘forever’ action. The ‘if’ action looks for a condition and performs an action when that condition is met. NOTE: The ‘if’ action is not to be confused with the ‘if else’ action, which does something else if the condition is not met.

We need to make this trigger activate when the W or S key is pressed. Go to the ‘Sensing’ section of the code blocks and bring a key press action into each blank spot of the ‘if’ actions. Change the default keys to W and S accordingly.
Now, go to the ‘Motion’ section of the code blocks and find the ‘change y by [number]’ action. Drag it inside the ‘if’ action. Remember to change the number to -10 on the down key.

At this point, you can click the green flag and test out what you’ve got so far. You should be able to use W and S to move the paddle on the left of the screen.
For the other paddle, we can just repeat what we did with the left paddle, but replacing W and S with Up Arrow and Down Arrow. 
NOTE: When you click the right paddle, it may seem like your code has been deleted. It hasn’t been. Code is different to every sprite, and the right paddle code is different to the left paddle code.

The paddles are complete! Now, we can move on to making the ball move. 

## The Ball
For the ball, we need to make it so that it:
Bounces off the paddles
Spawns back in the middle when it hits the edge and faces a random direction
First, let’s make it bounce off the paddles. Select the sprite you’re using for the ball and drag in a ‘when [green flag] clicked’ starting action.

Once you’ve done that, drag in a ‘go to’ action from the ‘Motion’ section. With this, we can make the ball go to the middle every time the game is started. Set the parameters to 0 and 0.

After that, drag in a ‘point in direction’ action. Then go to the ‘Operators’ section and replace the single number with a ‘pick random’ action.

Set the random number parameters to 45 and 135. Your code should look like this so far:

Add a ‘forever’ action and put the following actions inside it:
- if on edge, bounce
- move 5 steps
- if touching [name of left paddle]
  - turn [random number between 75 to 135] degrees
- if touching [name of right paddle]
  - turn [random number between 75 to 135] degrees
NOTE: Make sure the arrow on the turn actions are pointing clockwise.
Your code should look like this:

Now, we need to make it so that when the ball hits the edge, it goes back to 0, 0. We need some new sprites for this. Grab 2 lines from the sprite selector and position them to the side edges of the screen. You may need to move the paddles.

Then, make another green flag action with a forever loop. Then, add the following actions:
- if touching [left line name] then
  - go to x: 0 y: 0
- if touching [right line name] then
  - go to x: 0 y: 0


And that’s it! Start your project and try it out. It should look something like this:

You can stop here, but I recommend adding scoring. It doesn’t take much extra effort and makes the game more competitive and fun when playing with friends.

## Scoring
Scoring is pretty easy to add. We just need to make a variable for player 1 and 2 score, and make them go up by one when the ball hits the respective edge.

First, create a new variable. You can do this by going to the ‘Variables’ section and clicking ‘Make a Variable’.

Then, name the variable. I’ll name mine “Player 1 Score” for Player 1 and “Player 2 Score” for Player 2.

Once both of your variables are created, we need to make them go up by one when the ball hits the respective edge. For player 1, the ball would hit the right edge to score. 

Remember the mechanism we created to put the ball in the middle when it hits an edge? We can just use that for the scoring! Go back to the ball sprite and add a ‘set variable’ action under the ‘go to’ action.

Now do the same for the other line for player 2.

The last thing we need to do is reset the variables when the green flag is clicked. Create another green flag action and have it set both scores to 0.


# Outro
And we’re done! Your game should look something like this:

You can find the project I used for example in this user-doc at https://scratch.mit.edu/projects/417467504/. I used lsullivan3’s project ‘Easy Pong ( no score )’ to get some mechanics for this game. That project can be found at https://scratch.mit.edu/projects/417017510/. 


