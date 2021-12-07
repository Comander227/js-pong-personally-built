 


> Open this page at [https://comander227.github.io/js-pong-personally-built/](https://comander227.github.io/js-pong-personally-built/)

## Use as Extension

This repository can be added as an **extension** in MakeCode.

* open [https://arcade.makecode.com/](https://arcade.makecode.com/)
* click on **New Project**
* click on **Extensions** under the gearwheel menu
* search for **https://github.com/comander227/js-pong-personally-built** and import

## Edit this project ![Build status badge](https://github.com/comander227/js-pong-personally-built/workflows/MakeCode/badge.svg)

To edit this repository in MakeCode.

* open [https://arcade.makecode.com/](https://arcade.makecode.com/)
* click on **Import** then click on **Import URL**
* paste **https://github.com/comander227/js-pong-personally-built** and click import

## Blocks preview

This image shows the blocks code from the last commit in master.
This image may take a few minutes to refresh.

![A rendered view of the blocks](https://github.com/comander227/js-pong-personally-built/raw/master/.github/makecode/blocks.png)

#### Metadata (used for search, rendering)

* for PXT/arcade
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>








### @activities 1
 
# Pong
## Part 1: Setting Up Key Variables
### Part 1: Setting Up Key Variables
We will use the ``||Variables:variable||`` category to create our players and our background image.
### Step 1: Setting up the players Variables
Create a ``||variables: players||`` from the variables section by clicking on the ``||Variables: Make a Variable ||`` button. 
Name the variable ``||variables: players||``.
Set the value of ``||variables: players||`` to 1.
```blocks
let players = 1
```
### Step 2: Setting up the background variable
We need to create an image to use as our background.
Use the ``||Variables: Make a Variable ||`` button to create a variable named Picture for our background.
 
 
```blocks
let players = 1
let Picture = 0
```
### Step 3: Setting up the background image
Open the advanced section of the toolbox.
Click on the image category.
Grab a ``||image: create image width () height()||``.
Replace the white circle in the ``||variables: Set Picture||`` block.
```blocks
let players = 1
let Picture = image.create(0, 0)
```
 
### Step 4: Set the size of the image
Open the ``||scene:scene||`` category.
Add a ``||scene:screenWidth||`` to the image's width and a ``||scene:screenHeight||`` to the image height.
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight(),)
```
## Part 2: Setting up the net
### Part 2: Setting up the net
Here is where we will edit our background picture to include a net.
We will use a ``||loops:for loop||`` to create a uniform net. 
 
### Step 1: Using a For Loop
Add a ``||loops:for||`` to the ``||loops: on start||`` container.
Add the ``||scene: screenHeight||`` to the max index value.
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight(),)
for (let index = 0; index <= scene.screenHeight(); index++) { 
}
```
### Step 2: Using an if statement to set up the net.
Grab an ``||logic:if then loop||`` and add it to the ``||loops:for||`` loop.
Add a ``||logic: comparison||`` diamond to the ``||logic:if then loop||``.
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight(),)
for (let index = 0; index <= scene.screenHeight(); index++) { 
if (0 < 0) {
 
}}
```
### Step 3: Adding the math
Add a ``||math: remainder of||`` to the ``||logic: comparison||`` diamond.
Add a ``||math:division||`` circle and then the local ``||variables:index||`` to the ``||math: remainder of||``
Set the values so it reads ``||logic:if||`` the remainder of the ``||variables:index||`` divided by 6 is less than 4.
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight(),)
for (let index = 0; index <= scene.screenHeight(); index++) { 
if (index % 6 < 4) {
  }}
```
### Step 4: Creating our net
Add a ``||image:setPicture at x () y () color||`` block to the ``||logic:if then loop||``.
Add a ``||variables: Picture||`` circle from the ``||variables:variable||`` category to the ``||image:setPicture at x () y () color||`` block.
Add a ``||math: division||`` block to the x coordinate space.
Add the ``||scene: screenHeight||`` circle to the ``||math: division||``. Set the divisor to 2.
Remember to select a color for your net by clicking on the circle at the end of the block.
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight(),)
for (let index = 0; index <= scene.screenHeight(); index++) { 
if (index % 6 < 4) {
      Picture.setPixel(scene.screenWidth() / 2, index, 1)
  }}
```
### Step 5: Setting the background
Add a ``||scene: set background image||`` block to the ``||loops: on start||`` container.
Grab the ``||variables: Picture||`` circle and place that in the image space.
 
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight(), )
for (let index = 0; index <= scene.screenHeight(); index++) { 
if (index % 6 < 4) {
      Picture.setPixel(scene.screenWidth() / 2, index, 1)
  }}
scene.setBackgroundImage(Picture)
```
 
## Part 3: Setting Up our Player Paddles
### Part 3: Setting up our Player Paddles
In this section we will set up our player paddles.
### Step 1: Creating our Player sprite
Add a ``||sprites:set MySprite ||`` under the ``||scene: set background image||`` block in the ``||loops: on start||`` container.
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight(), )
for (let index = 0; index <= scene.screenHeight(); index++) { 
if (index % 6 < 4) {
      Picture.setPixel(scene.screenWidth() / 2, index, 1)
  }}
scene.setBackgroundImage(Picture)
let MySprite = sprites.create(img``,SpriteKind.Player)
```
### Step 2: Setting the Player1 Paddle
Rename ``||variables:MySprite||`` to ``||variables:Player1||``.
Select the Player 1 asset using the sprite editor.   
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight())
for (let index = 0; index <= scene.screenHeight(); index++) { 
if (index % 6 < 4) {
      Picture.setPixel(scene.screenWidth() / 2, index, 1)
  }}
scene.setBackgroundImage(Picture)
let Player1 = sprites.create(assets.image`Player 1`,SpriteKind.Player)
```
 
### Step 2.5: Moving Player 1.
Add a ``||controller:move MySprite with buttons||`` block from the ``||controller:controller||`` category. 
Change ``||variables:MySprite||`` to ``||variables:Player1||``.
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight())
for (let index = 0; index <= scene.screenHeight(); index++) { 
if (index % 6 < 4) {
      Picture.setPixel(scene.screenWidth() / 2, index, 1)
  }}
scene.setBackgroundImage(Picture)
let Player1 = sprites.create(assets.image`Player 1`,SpriteKind.Player)
controller.moveSprite(Player1)
```
### Step 2.6: Moving in One Direction
Click on the + button on the ``||controller:move Player1 with buttons||`` block.
Change the vx value from 100 to 0.
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight())
for (let index = 0; index <= scene.screenHeight(); index++) { 
if (index % 6 < 4) {
      Picture.setPixel(scene.screenWidth() / 2, index, 1)
  }}
scene.setBackgroundImage(Picture)
let Player1 = sprites.create(assets.image`Player 1`,SpriteKind.Player)
controller.moveSprite(Player1, 0, 100)
```
### Step 3: Setting the Player1 Paddle's Position
Add a ``||sprites: Set mySprite x() y()||`` block from the ``||sprites:sprites||`` category.
Change ``||variables:MySprite||`` to ``||variables:Player1||``.
Set the x value to 8 and the y value to 60.
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight())
for (let index = 0; index <= scene.screenHeight(); index++) { 
if (index % 6 < 4) {
      Picture.setPixel(scene.screenWidth() / 2, index, 1)
  }}
scene.setBackgroundImage(Picture)
let Player1 = sprites.create(assets.image`Player 1`,SpriteKind.Player)
controller.moveSprite(Player1, 0, 100)
Player1.setPosition(8,60)
```
### Step 4: Setting Up the Player1 Paddle to Stay on Screen
Add a ``||sprites: set mySprite stay on screen||`` block from the ``||sprites:sprites||`` category.
Change ``||variables:MySprite||`` to ``||variables:Player1||``.
Set the value to on.
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight())
for (let index = 0; index <= scene.screenHeight(); index++) { 
if (index % 6 < 4) {
      Picture.setPixel(scene.screenWidth() / 2, index, 1)
  }}
scene.setBackgroundImage(Picture)
let Player1 = sprites.create(assets.image`Player 1`,SpriteKind.Player)
controller.moveSprite(Player1, 0, 100)
Player1.setPosition(8,60)
Player1.setStayInScreen(true)
```
### Step 5: Setting Up the Player2 Paddle
We will use the same blocks that we used for Player1's Paddle but renaming the sprite to Player 2.
Start with adding the ``||sprites: set MySprite||`` to the ``||loops:on start||`` container.
Rename ``||variables:MySprite||`` to ``||variables:Player2||``.
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight())
for (let index = 0; index <= scene.screenHeight(); index++) { 
if (index % 6 < 4) {
      Picture.setPixel(scene.screenWidth() / 2, index, 1)
  }}
scene.setBackgroundImage(Picture)
let Player1 = sprites.create(assets.image`Player 1`,SpriteKind.Player)
controller.moveSprite(Player1, 0, 100)
Player1.setPosition(8,60)
Player1.setStayInScreen(true)
let Player2 = sprites.create(img``,SpriteKind.Player)
```
### Step 6: Setting the Player2 Paddle Image.
Assign the Player2 sprite with the Player 2 asset by clicking on the grey box.
In the editor open the asset tab.
Choose the paddle labeled Player 2.
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight())
for (let index = 0; index <= scene.screenHeight(); index++) { 
if (index % 6 < 4) {
      Picture.setPixel(scene.screenWidth() / 2, index, 1)
  }}
scene.setBackgroundImage(Picture)
let Player1 = sprites.create(assets.image`Player 1`,SpriteKind.Player)
controller.moveSprite(Player1, 0, 100)
Player1.setPosition(8,60)
Player1.setStayInScreen(true)
let Player2 = sprites.create(assets.image`Player 2`,SpriteKind.Player)
```
 
### Step 7: Setting Up Player 2's Position
Add the ``||sprites:set MySprite x() y()||`` block from the ``||sprites:sprites||`` category.
Change ``||basic:MySprite||`` to ``||variables:Player2||``.
Set the x value to 152 and the y value to 60.
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight())
for (let index = 0; index <= scene.screenHeight(); index++) { 
if (index % 6 < 4) {
      Picture.setPixel(scene.screenWidth() / 2, index, 1)
  }}
scene.setBackgroundImage(Picture)
let Player1 = sprites.create(assets.image`Player 1`,SpriteKind.Player)
controller.moveSprite(Player1, 0, 100)
Player1.setPosition(8,60)
Player1.setStayInScreen(true)
let Player2 = sprites.create(assets.image`Player 2`,SpriteKind.Player)
Player2.setPosition(152,60)
```
### Step 8: Setting the Player 2 Paddle to Stay on Screen.
Add a ``||sprites:set MySprite Stay on Screen||`` block to the ``||loops:on start||`` container.
Change ``||variables:MySprite||`` to ``||variables:Player2||``.
Set the value to on.
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight())
for (let index = 0; index <= scene.screenHeight(); index++) { 
if (index % 6 < 4) {
      Picture.setPixel(scene.screenWidth() / 2, index, 1)
  }}
scene.setBackgroundImage(Picture)
let Player1 = sprites.create(assets.image`Player 1`,SpriteKind.Player)
controller.moveSprite(Player1, 0, 100)
Player1.setPosition(8,60)
Player1.setStayInScreen(true)
let Player2 = sprites.create(assets.image`Player 2`,SpriteKind.Player)
Player2.setPosition(152,60)
Player2.setStayInScreen(true)
```
## Part 4: Setting up the Ball
### Part 4: Setting up the Ball
Now we are going to set up our game ball.
 
### Step 1: Setting up a Projectile
Add a ``||sprites: set Projectile From Sprite||`` block to the ``||loops:on start||``.
Change ``||variables:MySprite||`` to ``||variables:Player1||`` as we want the ball to spawn from Player1.
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight())
for (let index = 0; index <= scene.screenHeight(); index++) { 
if (index % 6 < 4) {
      Picture.setPixel(scene.screenWidth() / 2, index, 1)
  }}
scene.setBackgroundImage(Picture)
let Player1 = sprites.create(assets.image`Player 1`,SpriteKind.Player)
controller.moveSprite(Player1, 0, 100)
Player1.setPosition(8,60)
Player1.setStayInScreen(true)
let Player2 = sprites.create(assets.image`Player 2`,SpriteKind.Player)
Player2.setPosition(152,60)
Player2.setStayInScreen(true)
let projectile = sprites.createProjectileFromSprite(img``,Player1,0,0)
```
### Step 2: Assign the Projectile to the Ball asset.
Click on the ``||variables:projectile||``'s grey box to open the sprite editor.
Open the asset tab.
Choose the asset labeled Ball.
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight())
for (let index = 0; index <= scene.screenHeight(); index++) { 
if (index % 6 < 4) {
      Picture.setPixel(scene.screenWidth() / 2, index, 1)
  }}
scene.setBackgroundImage(Picture)
let Player1 = sprites.create(assets.image`Player 1`,SpriteKind.Player)
controller.moveSprite(Player1, 0, 100)
Player1.setPosition(8,60)
Player1.setStayInScreen(true)
let Player2 = sprites.create(assets.image`Player 2`,SpriteKind.Player)
Player2.setPosition(152,60)
Player2.setStayInScreen(true)
let projectile = sprites.createProjectileFromSprite(assets.image`Ball`,Player1,0,0)
```
 
### Step 3: Assigning Random vx and vy values.
Add a ``||math:pick random (min) to (max)||`` circle from the ``||math:math||`` category to the vx and vy value of the ``||sprites:set Projectile from||`` block.
Set the vx values to a minimum of 50 and maximum of 75.
Set the vy values to a minimum of 25 and maximum of 50.
 
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight())
for (let index = 0; index <= scene.screenHeight(); index++) { 
if (index % 6 < 4) {
      Picture.setPixel(scene.screenWidth() / 2, index, 1)
  }}
scene.setBackgroundImage(Picture)
let Player1 = sprites.create(assets.image`Player 1`,SpriteKind.Player)
controller.moveSprite(Player1, 0, 100)
Player1.setPosition(8,60)
Player1.setStayInScreen(true)
let Player2 = sprites.create(assets.image`Player 2`,SpriteKind.Player)
Player2.setPosition(152,60)
Player2.setStayInScreen(true)
let projectile = sprites.createProjectileFromSprite(assets.image`Ball`,Player1,randint(50,75),randint(25,50))
```
 
### Step 4: Moving the Ball
Add a ``||sprites:change MySprite x by ()||`` block to the ``||loops:on start||`` container.
Change ``||variables:MySprite||`` to ``||variables:projectile||``.
Change the value from 0 to 3.
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight())
for (let index = 0; index <= scene.screenHeight(); index++) { 
if (index % 6 < 4) {
      Picture.setPixel(scene.screenWidth() / 2, index, 1)
  }}
scene.setBackgroundImage(Picture)
let Player1 = sprites.create(assets.image`Player 1`,SpriteKind.Player)
controller.moveSprite(Player1, 0, 100)
Player1.setPosition(8,60)
Player1.setStayInScreen(true)
let Player2 = sprites.create(assets.image`Player 2`,SpriteKind.Player)
Player2.setPosition(152,60)
Player2.setStayInScreen(true)
let projectile = sprites.createProjectileFromSprite(assets.image`Ball`,Player1,randint(50,75),randint(25,50))
projectile.x +=3
```
### Step 5: Setting the Ball to Bounce
Add a ``||sprites:set MySprite Bounce on Walls||`` block from the ``||sprites:sprites||`` category.
Change ``||variables:MySprite||`` to ``||variables:projectile||``.
Set the value to true.
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight())
for (let index = 0; index <= scene.screenHeight(); index++) { 
if (index % 6 < 4) {
      Picture.setPixel(scene.screenWidth() / 2, index, 1)
  }}
scene.setBackgroundImage(Picture)
let Player1 = sprites.create(assets.image`Player 1`,SpriteKind.Player)
controller.moveSprite(Player1, 0, 100)
Player1.setPosition(8,60)
Player1.setStayInScreen(true)
let Player2 = sprites.create(assets.image`Player 2`,SpriteKind.Player)
Player2.setPosition(152,60)
Player2.setStayInScreen(true)
let projectile = sprites.createProjectileFromSprite(assets.image`Ball`,Player1,randint(50,75),randint(25,50))
projectile.x +=3
projectile.setBounceOnWall(true)
```
## Part 5: Setting up the Scoring System
### Part 5: Setting up the Scoring System
Now that we have set up our paddles and ball we can move on to set up our scoring system.
 
### Step 1: Adding an On Game Update Container
Add a ``||game:on game update||`` container from the ``||game:game||`` category.
```blocks
game.onUpdate(function(){})
```
### Step 2: Setting up our if then containers
Add an ``||logic:if then loop||`` from the ``||logic:logic||`` category.
Add a ``||logic: comparison||`` diamond from the ``||logic:logic||`` category to your ``||logic:if then loop||``.
```blocks
game.onUpdate(function(){
if (0 < 0) {
 
}})
```
### Step 3: Add the needed Sprite values
Add a ``||sprites:MySprite x||`` circle from the ``||sprites:sprites||`` group to each comparison value.
```blocks
game.onUpdate(function(){
let mySprite: Sprite = null
   if (mySprite.x > mySprite.x) {
    
   }
})
```
### Step 4: Adjusting our Sprites and values
Change the comparison diamond so it reads ``||variables:projectile||`` ``||sprites:x||`` is less than (>) ``||variables:Player2||`` ``||sprites:right||``.
```blocks
let projectile: Sprite = null
let Player2: Sprite = null
game.onUpdate(function(){
   if (projectile.x > Player2.right) {
    
   }
})
```
### Step 5: Scoring Points
Add the ``||info: Change Player 2 Score By 1||`` block from the ``||info:info||`` category.
Change ``||info:Player 2||`` to ``||info:Player 1||``.
```blocks
let projectile: Sprite = null
let Player2: Sprite = null
game.onUpdate(function(){
   if (projectile.x > Player2.right) {
   info.player1.changeScoreBy(1)  
   }
})
```
### Step 6: Adding Sound Effects.
Open the ``||music:music||`` category and add a  ``||music:play sound||`` block under your ``||info: Change Player 1 Score By 1||`` block.
Change ``||music:ba ding||`` to ``||music:jumpUp||``.
```blocks
let projectile: Sprite = null
let Player2: Sprite = null
game.onUpdate(function(){
   if (projectile.x > Player2.right) {
   info.player1.changeScoreBy(1)  
   music.jumpUp.play()
   }
})
```
### Step 6: Resetting the Ball's Position.
Add a ``||sprites: set mySprite position to x() y()||`` block under the ``||music:play sound jump up||`` block. 
Change ``||variables:mySprite||`` to ``||variables:projectile||``.
```blocks
let projectile: Sprite = null
let Player2: Sprite = null
game.onUpdate(function(){
   if (projectile.x > Player2.right) {
   info.player1.changeScoreBy(1)  
   music.jumpUp.play()
   projectile.setPosition(0,0)
   }
})
```
### Step 6.5: Resetting the Ball's Position to Player 1.
Add a ``||math:addition||`` cirlce to the x value for your ``||variables:projectile||``'s new position. 
Add a ``||sprites:mySprite x||`` circle to the beginning of your ``||math:addition cirlce||`` and one to the ``||sprites:y value||``. 
Change both ``||variables:mySprite||`` to ``||variables:Player1||``.
Change the second ``||variables:Player1||`` from ``||sprites:x||`` to ``||sprites:y||``. 
Use the ``||math:addition||``to add ``||math: 3||`` to the ``||variables:projectile||`` ``||sprites:x value||``.
```blocks
let projectile: Sprite = null
let Player2: Sprite = null
let Player1: Sprite = null
game.onUpdate(function(){
   if (projectile.x > Player2.right) {
   info.player1.changeScoreBy(1)  
   music.jumpUp.play()
   projectile.setPosition(Player1.x +3,Player1.y)
   }
})
```
### Step 7: Resetting the Ball's Velocity.
Add a ``||sprites:set mySprite velocity to vx() vy()||`` block under your ``||sprites:set projectile position||`` block. 
Change ``||variables:mySprite||`` to ``||variables:projectile||``.
```blocks
let projectile: Sprite = null
let Player2: Sprite = null
let Player1: Sprite = null
game.onUpdate(function(){
   if (projectile.x > Player2.right) {
   info.player1.changeScoreBy(1)  
   music.jumpUp.play()
   projectile.setPosition(Player1.x +3,Player1.y)
   projectile.setVelocity(0,0)
   }
})
```

### Step 7.5:Setting the Ball's Velocity Values. 
Add a ``||math:pick random||`` cirlce to the ``||sprites:vx||`` and the``||sprites:vy||`` values.
Set the ``||sprites:vx value||`` to ``||math: 50 min and 75 max||``.
Set the ``||sprites:vy value||`` to ``||math: 25 min and 50 max||``.
```blocks
let projectile: Sprite = null
let Player2: Sprite = null
let Player1: Sprite = null
game.onUpdate(function(){
   if (projectile.x > Player2.right) {
   info.player1.changeScoreBy(1)  
   music.jumpUp.play()
   projectile.setPosition(Player1.x +3,Player1.y)
   projectile.setVelocity(randint(50,75),randint(25,50))
   }
})
```
### Step 8: Setting up Player2's Scoring System. 
Click the + button on the ``||logic:if then||`` container twice.
This will create an ``||logic:else if||`` loop and an ``||logic:else||`` loop. 
Click the - button to remove the ``||logic:else||`` loop. 
```blocks
let projectile: Sprite = null
let Player2: Sprite = null
let Player1: Sprite = null
game.onUpdate(function(){
   if (projectile.x > Player2.right) {
   info.player1.changeScoreBy(1)  
   music.jumpUp.play()
   projectile.setPosition(Player1.x +3,Player1.y)
   projectile.setVelocity(randint(50,75),randint(25,50))
   } else if (false){
   }
})
```
### Step 9: Setting up the Scoring Condition.
Copy the ``||logic:comparison||`` diamond from the top of the ``||logic:if then loop||`` by right clicking on the diamond and then duplicating it.
Drag it to the new ``||logic:else if loop||``. 
Change the values so it reads ``||variables:projectile||`` ``||sprites:x||`` ``||logic:<||`` ``||variables:Player1||`` ``||sprites:left||``.
```blocks
let projectile: Sprite = null
let Player2: Sprite = null
let Player1: Sprite = null
game.onUpdate(function(){
   if (projectile.x > Player2.right) {
   info.player1.changeScoreBy(1)  
   music.jumpUp.play()
   projectile.setPosition(Player1.x +3,Player1.y)
   projectile.setVelocity(randint(50,75),randint(25,50))
   } else if (projectile.x < Player1.left){
   }
})
``` 

### Step 10: Updating Player2's Score.
Add a ``||info:change player 2 score by 1||`` block from the ``||info:info||`` category to your ``||logic:else if loop||``.
```blocks
let projectile: Sprite = null
let Player2: Sprite = null
let Player1: Sprite = null
game.onUpdate(function(){
   if (projectile.x > Player2.right) {
   info.player1.changeScoreBy(1)  
   music.jumpUp.play()
   projectile.setPosition(Player1.x +3,Player1.y)
   projectile.setVelocity(randint(50,75),randint(25,50))
   } else if (projectile.x < Player1.left){
   info.player2.changeScoreBy(1)

   }
})
``` 
### Step 11: Adding a Sound Effect.
Add a ``||music:play sound||`` block under the ``||info:change player 2 score by 1||`` block. 
Change ``||music:ba ding||`` to ``||music:jump up||``. 
```blocks
let projectile: Sprite = null
let Player2: Sprite = null
let Player1: Sprite = null
game.onUpdate(function(){
   if (projectile.x > Player2.right) {
   info.player1.changeScoreBy(1)  
   music.jumpUp.play()
   projectile.setPosition(Player1.x +3,Player1.y)
   projectile.setVelocity(randint(50,75),randint(25,50))
   } else if (projectile.x < Player1.left){
   info.player2.changeScoreBy(1)
   music.jumpUp.play()
   }
})
```

### Step 12: Reseting the Ball's Position.
Add a ``||sprites: set mySprite position to x() y()||`` block under the ``||music:play sound jump up||`` block. 
Change ``||variables:mySprite||`` to ``||variables:projectile||``.
```blocks
let projectile: Sprite = null
let Player2: Sprite = null
let Player1: Sprite = null
game.onUpdate(function(){
   if (projectile.x > Player2.right) {
   info.player1.changeScoreBy(1)  
   music.jumpUp.play()
   projectile.setPosition(Player1.x +3,Player1.y)
   projectile.setVelocity(randint(50,75),randint(25,50))
   } else if (projectile.x < Player1.left){
   info.player2.changeScoreBy(1)
   music.jumpUp.play()
   projectile.setPosition(0,0)
   }
})
```
### Step 12.5: Resetting the Ball's Position to Player 2.
Add a ``||math:subtraction||`` cirlce to the x value for your ``||variables:projectile||``'s new position. 
Add a ``||sprites:mySprite x||`` circle to the beginning of your ``||math:subtraction cirlce||`` and one to the ``||sprites:y value||``. 
Change both ``||variables:mySprite||`` to ``||variables:Player2||``.
Change the second ``||variables:Player2||`` from ``||sprites:x||`` to ``||sprites:y||``. 
Use the ``||math:subtraction||``to subtract ``||math: 3||`` to the ``||variables:projectile||`` ``||sprites:x value||``.
```blocks
let projectile: Sprite = null
let Player2: Sprite = null
let Player1: Sprite = null
game.onUpdate(function(){
   if (projectile.x > Player2.right) {
   info.player1.changeScoreBy(1)  
   music.jumpUp.play()
   projectile.setPosition(Player1.x +3,Player1.y)
   projectile.setVelocity(randint(50,75),randint(25,50))
   } else if (projectile.x < Player1.left){
   info.player2.changeScoreBy(1)
   music.jumpUp.play()
   projectile.setPosition(Player2.x -3,Player2.y)
   }
})
```

### Step 13: Resetting the Ball's Velocity.
Add a ``||sprites:set mySprite velocity to vx() vy()||`` block under your ``||sprites:set projectile position||`` block. 
Change ``||variables:mySprite||`` to ``||variables:projectile||``.
```blocks
let projectile: Sprite = null
let Player2: Sprite = null
let Player1: Sprite = null
game.onUpdate(function(){
   if (projectile.x > Player2.right) {
   info.player1.changeScoreBy(1)  
   music.jumpUp.play()
   projectile.setPosition(Player1.x +3,Player1.y)
   projectile.setVelocity(randint(50,75),randint(25,50))
   } else if (projectile.x < Player1.left){
   info.player2.changeScoreBy(1)
   music.jumpUp.play()
   projectile.setPosition(Player2.x -3,Player2.y)
   projectile.setVelocity(0,0)
   }
})
```
### Step 13.5:Setting the Ball's Velocity Values. 
Add a ``||math:pick random||`` cirlce to the ``||sprites:vx||`` and the``||sprites:vy||`` values.
Set the ``||sprites:vx value||`` to ``||math: -75 min and -50 max||``.
Set the ``||sprites:vy value||`` to ``||math: -50 min and -25 max||``.
```blocks
let projectile: Sprite = null
let Player2: Sprite = null
let Player1: Sprite = null
game.onUpdate(function(){
   if (projectile.x > Player2.right) {
   info.player1.changeScoreBy(1)  
   music.jumpUp.play()
   projectile.setPosition(Player1.x +3,Player1.y)
   projectile.setVelocity(randint(50,75),randint(25,50))
   } else if (projectile.x < Player1.left){
   info.player2.changeScoreBy(1)
   music.jumpUp.play()
   projectile.setPosition(Player2.x -3,Player2.y)
   projectile.setVelocity(randint(-75,-50),randint(-50,-25))
   }
})
```

### Step 14: Setting up the Players Starting Score. 
Add two ``||info:set player 2 score to 0||`` to your ``||loops: on start||`` container. 
Change one of the ``||info:set player 2 score to 0||`` to ``||info:set player 1 score to 0||``.
```blocks
let players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight())
for (let index = 0; index <= scene.screenHeight(); index++) { 
if (index % 6 < 4) {
      Picture.setPixel(scene.screenWidth() / 2, index, 1)
  }}
scene.setBackgroundImage(Picture)
let Player1 = sprites.create(assets.image`Player 1`,SpriteKind.Player)
controller.moveSprite(Player1, 0, 100)
Player1.setPosition(8,60)
Player1.setStayInScreen(true)
let Player2 = sprites.create(assets.image`Player 2`,SpriteKind.Player)
Player2.setPosition(152,60)
Player2.setStayInScreen(true)
let projectile = sprites.createProjectileFromSprite(assets.image`Ball`,Player1,randint(50,75),randint(25,50))
projectile.x +=3
projectile.setBounceOnWall(true)
info.player1.setScore(0)
info.player2.setScore(0)
```

## Part 6: Making an Impact.
### Part 6: Making an Impact.
Now we will use an ``||sprites:On Overlap||`` container to make our ball bounce off the paddles. 

### Step 1: Adding the new container.
Add an new ``||sprites: on Overlap||`` container to the workspace.
Change the ``||variables:otherSprite||`` ``||sprites:kind||`` from ``||sprites:player||`` to ``||sprites:projectile||``. 
```blocks
sprites.onOverlap(SpriteKind.Player,SpriteKind.Projectile, function(sprite,otherSprite){

})
```
### Step 2: Updating the Ball's Velocity.
Add two ``||sprites:set mySprite x to ()||`` to the ``||sprites:on Overlap||`` container.
Add ``||math:multiplication||`` circles to each value.  
```blocks
sprites.onOverlap(SpriteKind.Player,SpriteKind.Projectile, function(sprite,otherSprite){
  let mySprite: Sprite = null
    mySprite.x = 0 * 0
    mySprite.x = 0 * 0
})
```
### Step 3: Altering the value.
Add two ``||sprites: mySprite x||`` circles to your ``||math:multiplication||`` values. 
Drag the local ``||variables:otherSprite||`` over the all of the ``||variables:mySprite||`` variables

```blocks
sprites.onOverlap(SpriteKind.Player,SpriteKind.Projectile, function(sprite,otherSprite){

    otherSprite.x = 0 * otherSprite.x
    otherSprite.x = 0 * otherSprite.x
})
```

### Step 3.5 Continuing to alter the values
Change the first ``||sprites:set otherSprite X||`` to ``||sprites:set otherSprite vx||``. 
Set the ``||math:multiplication||`` cirlce to read ``||math: -1.1 x||`` ``||variables:otherSprite||`` ``||sprites:vx||``.
```blocks
sprites.onOverlap(SpriteKind.Player,SpriteKind.Projectile, function(sprite,otherSprite){

    otherSprite.vx = -1.1 * otherSprite.vx
    otherSprite.x = 0 * otherSprite.x
})
```

### Step 3.6 Continuing to alter the values
Change the second ``||sprites:set otherSprite X||`` to ``||sprites:set otherSprite vy||``. 
Set the ``||math:multiplication||`` cirlce to read ``||math: 1.1 x||`` ``||variables:otherSprite||`` ``||sprites:vy||``.
```blocks
sprites.onOverlap(SpriteKind.Player,SpriteKind.Projectile, function(sprite,otherSprite){

    otherSprite.vx = -1.1 * otherSprite.vx
    otherSprite.vy = 1.1 * otherSprite.vy
})
```

### Step 4: Adding A Sound Effect. 
Add ``||music:play tone at Middle C for 1/2 beat||`` to the ``||sprites:on overlap||`` container. 
Change ``||music: Middle C||`` to ``||music:Middle B||``. If you can't find Middle B, enter the value 494. 
```blocks
sprites.onOverlap(SpriteKind.Player,SpriteKind.Projectile, function(sprite,otherSprite){

    otherSprite.vx = -1.1 * otherSprite.vx
    otherSprite.vy = 1.1 * otherSprite.vy
    music.playTone(494,music.beat(BeatFraction.Half))
})
```


## Part 7 Setting Up Solo Mode
### Part 7 Setting Up Solo Mode

### Step 1: New Container
Grab a new ``||game:on game update||`` container.
```blocks
game.onUpdate(function(){
   
})
```
### Step 2: Adding Logic
Add an ``||logic:if then loop||`` to your ``||game: on game update||`` container. 
Add an ``||logic: and||`` diamond to the ``||logic:if then loop||``.
```blocks
game.onUpdate(function(){
  if (true && true){
  } 
})
```
### Step 3: Setting up the core if then loop. 
Add two comparison diamonds to the ``||logic: and||`` diamond. 
Add a ``||math:division||`` circle to the first ``||logic:comparison||`` diamond.
Add a ``||sprites:mySprite x()||`` cirlce to the ``||logic:comparison||`` diamond. 
Add a ``||scene:screenWidth||`` circle to the other side of the ``||logic:comparison||`` diamond. 
Set the first diamond so it reads ``||variables:projectile||`` ``||sprites:y||`` ``||logic:>||`` ``||scene:screenWidth||`` ``||math:/2||`` 
```blocks
let projectile: Sprite = null
game.onUpdate(function(){
  if (projectile.y > scene.screenWidth() /2 && true){
  } 
})
```

### Step 4: How Many Players Do We Have?
We need to check how many players we have. Add the ``||variables:players||`` from the ``||variables:variables||`` category to the second comparison diamond. 
Set it so it reads ``||variables:players||`` ``||logic:=||`` 1.
```blocks
let projectile: Sprite = null
game.onUpdate(function(){
  if (projectile.y > scene.screenWidth() /2 && players == 1){
  } 
})
```

### Step 5: Adding More Logic to our Computer Opponent.
Add an ``||logic: if then else loop||`` to the ``||logic: if then loop||`` you already have. 
```blocks
let projectile: Sprite = null
game.onUpdate(function(){
  if (projectile.y > scene.screenWidth() /2 && players == 1){
    if (true){
    }else {
    }
  } 
})
```
### Step 6: Comparing the computer's position to the ball's position.
Add a ``||logic:comparison||`` diamond to the ``||logic:if then loop||`` you just added. 
Add a ``||sprites:mySprite x||`` circle to both parts of the ``||logic:comparson||`` diamond.
Set the ``||variables:variables||`` so the ``||logic:comparison||`` diamon reads ``||variables:projectile||`` ``||sprites:y||`` ``||logic: >||`` ``||variables:Player2||`` ``||sprites:y||``.
```blocks
let Player2: Sprite = null
let projectile: Sprite = null
game.onUpdate(function(){
  if (projectile.y > scene.screenWidth() /2 && players == 1){
    if (projectile.y > Player2.y){
    }else {
    }
  } 
})
```
### Step 7: Moving the Computer's Paddle.
Add a ``||sprites:change mySprite x by ()||`` block to the ``||logic:if the loop||`` and the ``||logic:else loop||``. 
Set the first block to read ``||sprites: change||`` ``||variables:Player2||`` ``||sprites:y by 2||``.
Set the second block to read  ``||sprites: change||`` ``||variables:Player2||`` ``||sprites:y by -2||``.
```blocks
let Player2: Sprite = null
let projectile: Sprite = null
game.onUpdate(function(){
  if (projectile.y > scene.screenWidth() /2 && players == 1){
    if (projectile.y > Player2.y){
    Player2.y += 2
    }else {
    Player2.y += -2
    }
  } 
})
```

## Part 8: Controlling Player 2
### Part 8: Controlling Player 2
Now we are going to establish the controls for Player 2. 

### Step 1: Adding a New Controller Container
Drag a ``||controller: on player 2 A button pressed||`` to the workspace.
Change ``||controller: A||`` to ``||controller: up||``.
```blocks
controller.player2.onButtonEvent(ControllerButton.Up,ControllerButtonEvent.Pressed, function(){
})
```

### Step 2: Altering the number of players.
Add a ``||variables:set players to 0||`` block to the ``||controller: on player 2 up button pressed||`` container.
Change the value from ``||variables:0||`` to ``||variables:2||``.
```blocks
controller.player2.onButtonEvent(ControllerButton.Up,ControllerButtonEvent.Pressed, function(){
let players = 2
})
``` 


### Step 3: Adding Controller Blocks.
Add a ``||controller: player 2 move mySprite with buttons||`` to the ``||controller: on player 2 up button pressed||`` container. 
Change ``||variables:mySprite||`` to ``||variables:Player2||``.
Click on the ``||controller: +||`` button.
Change the ``||controller: vx||`` value to 0.
```blocks
controller.player2.onButtonEvent(ControllerButton.Up,ControllerButtonEvent.Pressed, function(){
let players = 2
controller.player2.moveSprite(Player2,0,100)
})
``` 

### Step 4: Duplicating the Controller Container.
Right click on the ``||controller: on player 2 up button pressed||`` container.
Click on Duplicate. 
Change ``||controller: up||`` to ``||controller:down||``.
```blocks
controller.player2.onButtonEvent(ControllerButton.Up,ControllerButtonEvent.Pressed, function(){
let players = 2
controller.player2.moveSprite(Player2,0,100)
})

controller.player2.onButtonEvent(ControllerButton.Down,ControllerButtonEvent.Pressed, function(){
let players = 2
controller.player2.moveSprite(Player2,0,100)
})
```



## Finish
### Finish
Congrats on completing your own version of Pong. Feel free to play a few rounds and challange your friends. 
 
 
```blocks
controller.player2.onButtonEvent(ControllerButton.Down, ControllerButtonEvent.Pressed, function () {
   players = 2
   controller.player2.moveSprite(Player2, 0, 100)
})
controller.player2.onButtonEvent(ControllerButton.Up, ControllerButtonEvent.Pressed, function () {
   players = 2
   controller.player2.moveSprite(Player2, 0, 100)
})
sprites.onOverlap(SpriteKind.Player, SpriteKind.Projectile, function (sprite, otherSprite) {
   otherSprite.vx = -1.1 * otherSprite.vx
   otherSprite.vy = 1.1 * otherSprite.vy
   music.playTone(494, music.beat(BeatFraction.Half))
})
let Player2: Sprite = null
let players = 0
players = 1
let Picture = image.create(scene.screenWidth(), scene.screenHeight())
for (let index = 0; index <= scene.screenHeight(); index++) {
   if (index % 6 < 4) {
       Picture.setPixel(scene.screenWidth() / 2, index, 1)
   }
}
scene.setBackgroundImage(Picture)
let Player1 = sprites.create(assets.image`Player 1`, SpriteKind.Player)
Player1.setPosition(8, 60)
controller.moveSprite(Player1, 0, 100)
Player1.setStayInScreen(true)
Player2 = sprites.create(assets.image`Player 2`, SpriteKind.Player)
Player2.setPosition(152, 60)
Player2.setStayInScreen(true)
let projectile = sprites.createProjectileFromSprite(assets.image`Ball`, Player1, randint(50, 75), randint(25, 50))
projectile.x += 3
projectile.setBounceOnWall(true)
projectile.setFlag(SpriteFlag.ShowPhysics, false)
info.player1.setScore(0)
info.player2.setScore(0)
game.onUpdate(function () {
   if (projectile.x > scene.screenWidth() / 2 && players == 1) {
       if (projectile.y > Player2.y) {
           Player2.y += 2
       } else {
           Player2.y += -2
       }
   }
})
game.onUpdate(function () {
   if (projectile.x > Player2.right) {
       info.player1.changeScoreBy(1)
       music.jumpUp.play()
       projectile.setPosition(Player1.x + 3, Player1.y)
       projectile.setVelocity(randint(50, 75), randint(25, 50))
   } else if (projectile.x < Player1.left) {
       info.player2.changeScoreBy(1)
       music.jumpUp.play()
       projectile.setPosition(Player2.x - 3, Player2.y)
       projectile.setVelocity(randint(-75, -50), randint(25, 50))
   }
})
```
```assetjson
{
"README.md": " ",
"assets.json": "",
"images.g.jres": "{\n    \"image1\": {\n        \"data\": \"hwQEABAAAAAREREREREREREREREREREREREREREREREREREREREREQ==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"displayName\": \"Player 1\"\n    },\n    \"image2\": {\n        \"data\": \"hwQEABAAAAAREREREREREREREREREREREREREREREREREREREREREQ==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"displayName\": \"Player 2\"\n    },\n    \"image3\": {\n        \"data\": \"hwQEAAQAAAAREQAAEREAABERAAAREQAA\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"displayName\": \"Ball\"\n    },\n    \"*\": {\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"dataEncoding\": \"base64\",\n        \"namespace\": \"myImages\"\n    }\n}",
"images.g.ts": "// Auto-generated code. Do not edit.\nnamespace myImages {\n\n    helpers._registerFactory(\"image\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"image1\":\n            case \"Player 1\":return img`\n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n`;\n            case \"image2\":\n            case \"Player 2\":return img`\n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n`;\n            case \"image3\":\n            case \"Ball\":return img`\n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n1 1 1 1 \n`;\n        }\n        return null;\n    })\n\n    helpers._registerFactory(\"animation\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n\n        }\n        return null;\n    })\n\n}\n// Auto-generated code. Do not edit.\n",
"main.blocks": "<xml xmlns=\"https://developers.google.com/blockly/xml\"><variables><variable id=\"rz2=;8%bkqrt,ku)g}8M\">players</variable><variable id=\"#f.b?SPX2EsqPu1X23dc\">Player_2</variable><variable id=\"Ec|Im!!IX8Pe~*~zo^Yz\">projectile</variable><variable id=\"k7D8@~,f^PwaT*^)7?Z/\">Player_1</variable><variable id=\"|~*o`cGlL}Vg`sOzA~iz\">Picture</variable><variable id=\"d99wZJ-_8I(|Y|=w)gg;\">index</variable><variable type=\"KIND_SpriteKind\" id=\"qqVNHMhe/y7?3;Yc.M-g\">Player</variable><variable type=\"KIND_SpriteKind\" id=\"3M=CxbLYdCu}8gS@hg|C\">Projectile</variable><variable type=\"KIND_SpriteKind\" id=\"mZ@-)oD$D,$SWFG3:a32\">Food</variable><variable type=\"KIND_SpriteKind\" id=\"v|$._^oCK:dm*)Q]uVW=\">Enemy</variable></variables><block type=\"pxt-on-start\" x=\"20\" y=\"20\"><statement name=\"HANDLER\"><block type=\"variables_set\"><field name=\"VAR\" id=\"rz2=;8%bkqrt,ku)g}8M\">players</field><value name=\"VALUE\"><shadow type=\"math_number\"><field name=\"NUM\">1</field></shadow></value><next><block type=\"variables_set\"><field name=\"VAR\" id=\"|~*o`cGlL}Vg`sOzA~iz\">Picture</field><value name=\"VALUE\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"image_create\"><value name=\"width\"><block type=\"scenescreenwidth\"/></value><value name=\"height\"><block type=\"scenescreenheight\"/></value></block></value><next><block type=\"pxt_controls_for\"><value name=\"VAR\"><shadow type=\"variables_get_reporter\"><field name=\"VAR\" id=\"d99wZJ-_8I(|Y|=w)gg;\">index</field></shadow></value><value name=\"TO\"><shadow type=\"math_whole_number\"><field name=\"NUM\">0</field></shadow><block type=\"scenescreenheight\"/></value><statement name=\"DO\"><block type=\"controls_if\"><value name=\"IF0\"><shadow type=\"logic_boolean\"><field name=\"BOOL\">TRUE</field></shadow><block type=\"logic_compare\"><field name=\"OP\">LT</field><value name=\"A\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"math_modulo\"><value name=\"DIVIDEND\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"variables_get\"><field name=\"VAR\" id=\"d99wZJ-_8I(|Y|=w)gg;\">index</field></block></value><value name=\"DIVISOR\"><shadow type=\"math_number\"><field name=\"NUM\">6</field></shadow></value></block></value><value name=\"B\"><shadow type=\"math_number\"><field name=\"NUM\">4</field></shadow></value></block></value><statement name=\"DO0\"><block type=\"Image_setPixel\"><value name=\"picture\"><shadow type=\"variables_get\"><field name=\"VAR\" id=\"|~*o`cGlL}Vg`sOzA~iz\">Picture</field></shadow></value><value name=\"x\"><block type=\"math_arithmetic\"><field name=\"OP\">DIVIDE</field><value name=\"A\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"scenescreenwidth\"/></value><value name=\"B\"><shadow type=\"math_number\"><field name=\"NUM\">2</field></shadow></value></block></value><value name=\"y\"><block type=\"variables_get\"><field name=\"VAR\" id=\"d99wZJ-_8I(|Y|=w)gg;\">index</field></block></value><value name=\"c\"><shadow type=\"colorindexpicker\"><field name=\"index\">1</field></shadow></value></block></statement></block></statement><next><block type=\"gamesetbackgroundimage\"><value name=\"img\"><shadow type=\"background_image_picker\"/><block type=\"variables_get\"><field name=\"VAR\" id=\"|~*o`cGlL}Vg`sOzA~iz\">Picture</field></block></value><next><block type=\"variables_set\"><field name=\"VAR\" id=\"k7D8@~,f^PwaT*^)7?Z/\">Player_1</field><value name=\"VALUE\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"spritescreate\"><value name=\"img\"><shadow type=\"screen_image_picker\"><field name=\"img\">assets.image`Player 1`</field><data>{\"commentRefs\":[],\"fieldData\":{\"img\":\"myImages.image1\"}}</data></shadow></value><value name=\"kind\"><shadow type=\"spritekind\"><field name=\"MEMBER\">Player</field></shadow></value></block></value><next><block type=\"spritesetpos\"><value name=\"sprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"k7D8@~,f^PwaT*^)7?Z/\">Player_1</field></block></value><value name=\"x\"><shadow type=\"positionPicker\"><field name=\"index\">8</field></shadow></value><value name=\"y\"><shadow type=\"positionPicker\"><field name=\"index\">60</field></shadow></value><next><block type=\"game_control_sprite\"><mutation xmlns=\"http://www.w3.org/1999/xhtml\" _expanded=\"2\" _input_init=\"true\"></mutation><value name=\"sprite\"><shadow type=\"variables_get\"><field name=\"VAR\" id=\"k7D8@~,f^PwaT*^)7?Z/\">Player_1</field></shadow></value><value name=\"vx\"><shadow type=\"spriteSpeedPicker\"><field name=\"speed\">0</field></shadow></value><value name=\"vy\"><shadow type=\"spriteSpeedPicker\"><field name=\"speed\">100</field></shadow></value><next><block type=\"spritesetsetstayinscreen\"><value name=\"sprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"k7D8@~,f^PwaT*^)7?Z/\">Player_1</field></block></value><value name=\"on\"><shadow type=\"toggleOnOff\"><field name=\"on\">true</field></shadow></value><next><block type=\"variables_set\"><field name=\"VAR\" id=\"#f.b?SPX2EsqPu1X23dc\">Player_2</field><value name=\"VALUE\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"spritescreate\"><value name=\"img\"><shadow type=\"screen_image_picker\"><field name=\"img\">assets.image`Player 2`</field><data>{\"commentRefs\":[],\"fieldData\":{\"img\":\"myImages.image2\"}}</data></shadow></value><value name=\"kind\"><shadow type=\"spritekind\"><field name=\"MEMBER\">Player</field></shadow></value></block></value><next><block type=\"spritesetpos\"><value name=\"sprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"#f.b?SPX2EsqPu1X23dc\">Player_2</field></block></value><value name=\"x\"><shadow type=\"positionPicker\"><field name=\"index\">152</field></shadow></value><value name=\"y\"><shadow type=\"positionPicker\"><field name=\"index\">60</field></shadow></value><next><block type=\"spritesetsetstayinscreen\"><value name=\"sprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"#f.b?SPX2EsqPu1X23dc\">Player_2</field></block></value><value name=\"on\"><shadow type=\"toggleOnOff\"><field name=\"on\">true</field></shadow></value><next><block type=\"variables_set\"><field name=\"VAR\" id=\"Ec|Im!!IX8Pe~*~zo^Yz\">projectile</field><value name=\"VALUE\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"spritescreateprojectilefromsprite\"><value name=\"img\"><shadow type=\"screen_image_picker\"><field name=\"img\">assets.image`Ball`</field><data>{\"commentRefs\":[],\"fieldData\":{\"img\":\"myImages.image3\"}}</data></shadow></value><value name=\"sprite\"><shadow type=\"variables_get\"><field name=\"VAR\" id=\"k7D8@~,f^PwaT*^)7?Z/\">Player_1</field></shadow></value><value name=\"vx\"><shadow type=\"spriteSpeedPicker\"/><block type=\"device_random\"><value name=\"min\"><shadow type=\"math_number\"><field name=\"NUM\">50</field></shadow></value><value name=\"limit\"><shadow type=\"math_number\"><field name=\"NUM\">75</field></shadow></value></block></value><value name=\"vy\"><shadow type=\"spriteSpeedPicker\"/><block type=\"device_random\"><value name=\"min\"><shadow type=\"math_number\"><field name=\"NUM\">25</field></shadow></value><value name=\"limit\"><shadow type=\"math_number\"><field name=\"NUM\">50</field></shadow></value></block></value></block></value><next><block type=\"Sprite_blockCombine_change\"><field name=\"property\">Sprite.x@set</field><value name=\"mySprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"Ec|Im!!IX8Pe~*~zo^Yz\">projectile</field></block></value><value name=\"value\"><shadow type=\"math_number\"><field name=\"NUM\">3</field></shadow></value><next><block type=\"spritesetsetbounceonwall\"><value name=\"sprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"Ec|Im!!IX8Pe~*~zo^Yz\">projectile</field></block></value><value name=\"on\"><shadow type=\"toggleOnOff\"><field name=\"on\">true</field></shadow></value><next><block type=\"spritesetsetflag\"><field name=\"flag\">SpriteFlag.ShowPhysics</field><value name=\"sprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"Ec|Im!!IX8Pe~*~zo^Yz\">projectile</field></block></value><value name=\"on\"><shadow type=\"toggleOnOff\"><field name=\"on\">false</field></shadow></value><next><block type=\"pisetscore\"><field name=\"player\">info.player1</field><value name=\"value\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow></value><next><block type=\"pisetscore\"><field name=\"player\">info.player2</field><value name=\"value\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow></value></block></next></block></next></block></next></block></next></block></next></block></next></block></next></block></next></block></next></block></next></block></next></block></next></block></next></block></next></block></next></block></next></block></statement></block><block type=\"ctrlonbuttonevent\" x=\"1369\" y=\"20\"><field name=\"controller\">controller.player2</field><field name=\"button\">ControllerButton.Down</field><field name=\"event\">ControllerButtonEvent.Pressed</field><statement name=\"HANDLER\"><block type=\"variables_set\"><field name=\"VAR\" id=\"rz2=;8%bkqrt,ku)g}8M\">players</field><value name=\"VALUE\"><shadow type=\"math_number\"><field name=\"NUM\">2</field></shadow></value><next><block type=\"ctrlgame_control_sprite\"><mutation xmlns=\"http://www.w3.org/1999/xhtml\" _expanded=\"2\" _input_init=\"true\"></mutation><field name=\"controller\">controller.player2</field><value name=\"sprite\"><shadow type=\"variables_get\"><field name=\"VAR\" id=\"#f.b?SPX2EsqPu1X23dc\">Player_2</field></shadow></value><value name=\"vx\"><shadow type=\"spriteSpeedPicker\"><field name=\"speed\">0</field></shadow></value><value name=\"vy\"><shadow type=\"spriteSpeedPicker\"><field name=\"speed\">100</field></shadow></value></block></next></block></statement></block><block type=\"ctrlonbuttonevent\" x=\"2116\" y=\"20\"><field name=\"controller\">controller.player2</field><field name=\"button\">ControllerButton.Up</field><field name=\"event\">ControllerButtonEvent.Pressed</field><statement name=\"HANDLER\"><block type=\"variables_set\"><field name=\"VAR\" id=\"rz2=;8%bkqrt,ku)g}8M\">players</field><value name=\"VALUE\"><shadow type=\"math_number\"><field name=\"NUM\">2</field></shadow></value><next><block type=\"ctrlgame_control_sprite\"><mutation xmlns=\"http://www.w3.org/1999/xhtml\" _expanded=\"2\" _input_init=\"true\"></mutation><field name=\"controller\">controller.player2</field><value name=\"sprite\"><shadow type=\"variables_get\"><field name=\"VAR\" id=\"#f.b?SPX2EsqPu1X23dc\">Player_2</field></shadow></value><value name=\"vx\"><shadow type=\"spriteSpeedPicker\"><field name=\"speed\">0</field></shadow></value><value name=\"vy\"><shadow type=\"spriteSpeedPicker\"><field name=\"speed\">100</field></shadow></value></block></next></block></statement></block><block type=\"gameupdate\" x=\"2863\" y=\"20\"><statement name=\"HANDLER\"><block type=\"controls_if\"><value name=\"IF0\"><shadow type=\"logic_boolean\"><field name=\"BOOL\">TRUE</field></shadow><block type=\"logic_operation\"><field name=\"OP\">AND</field><value name=\"A\"><shadow type=\"logic_boolean\"><field name=\"BOOL\">TRUE</field></shadow><block type=\"logic_compare\"><field name=\"OP\">GT</field><value name=\"A\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"Sprite_blockCombine_get\"><field name=\"property\">Sprite.x</field><value name=\"mySprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"Ec|Im!!IX8Pe~*~zo^Yz\">projectile</field></block></value></block></value><value name=\"B\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"math_arithmetic\"><field name=\"OP\">DIVIDE</field><value name=\"A\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"scenescreenwidth\"/></value><value name=\"B\"><shadow type=\"math_number\"><field name=\"NUM\">2</field></shadow></value></block></value></block></value><value name=\"B\"><shadow type=\"logic_boolean\"><field name=\"BOOL\">TRUE</field></shadow><block type=\"logic_compare\"><field name=\"OP\">EQ</field><value name=\"A\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"variables_get\"><field name=\"VAR\" id=\"rz2=;8%bkqrt,ku)g}8M\">players</field></block></value><value name=\"B\"><shadow type=\"math_number\"><field name=\"NUM\">1</field></shadow></value></block></value></block></value><statement name=\"DO0\"><block type=\"controls_if\"><mutation else=\"1\"/><value name=\"IF0\"><shadow type=\"logic_boolean\"><field name=\"BOOL\">TRUE</field></shadow><block type=\"logic_compare\"><field name=\"OP\">GT</field><value name=\"A\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"Sprite_blockCombine_get\"><field name=\"property\">Sprite.y</field><value name=\"mySprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"Ec|Im!!IX8Pe~*~zo^Yz\">projectile</field></block></value></block></value><value name=\"B\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"Sprite_blockCombine_get\"><field name=\"property\">Sprite.y</field><value name=\"mySprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"#f.b?SPX2EsqPu1X23dc\">Player_2</field></block></value></block></value></block></value><statement name=\"DO0\"><block type=\"Sprite_blockCombine_change\"><field name=\"property\">Sprite.y@set</field><value name=\"mySprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"#f.b?SPX2EsqPu1X23dc\">Player_2</field></block></value><value name=\"value\"><shadow type=\"math_number\"><field name=\"NUM\">2</field></shadow></value></block></statement><statement name=\"ELSE\"><block type=\"Sprite_blockCombine_change\"><field name=\"property\">Sprite.y@set</field><value name=\"mySprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"#f.b?SPX2EsqPu1X23dc\">Player_2</field></block></value><value name=\"value\"><shadow type=\"math_number\"><field name=\"NUM\">-2</field></shadow></value></block></statement></block></statement></block></statement></block><block type=\"gameupdate\" x=\"20\" y=\"1207\"><statement name=\"HANDLER\"><block type=\"controls_if\"><mutation elseif=\"1\"/><value name=\"IF0\"><shadow type=\"logic_boolean\"><field name=\"BOOL\">TRUE</field></shadow><block type=\"logic_compare\"><field name=\"OP\">GT</field><value name=\"A\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"Sprite_blockCombine_get\"><field name=\"property\">Sprite.x</field><value name=\"mySprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"Ec|Im!!IX8Pe~*~zo^Yz\">projectile</field></block></value></block></value><value name=\"B\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"Sprite_blockCombine_get\"><field name=\"property\">Sprite.right</field><value name=\"mySprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"#f.b?SPX2EsqPu1X23dc\">Player_2</field></block></value></block></value></block></value><statement name=\"DO0\"><block type=\"pichangescore\"><field name=\"player\">info.player1</field><value name=\"value\"><shadow type=\"math_number\"><field name=\"NUM\">1</field></shadow></value><next><block type=\"mixer_play_sound\"><field name=\"sound\">music.jumpUp</field><next><block type=\"spritesetpos\"><value name=\"sprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"Ec|Im!!IX8Pe~*~zo^Yz\">projectile</field></block></value><value name=\"x\"><shadow type=\"positionPicker\"/><block type=\"math_arithmetic\"><field name=\"OP\">ADD</field><value name=\"A\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"Sprite_blockCombine_get\"><field name=\"property\">Sprite.x</field><value name=\"mySprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"k7D8@~,f^PwaT*^)7?Z/\">Player_1</field></block></value></block></value><value name=\"B\"><shadow type=\"math_number\"><field name=\"NUM\">3</field></shadow></value></block></value><value name=\"y\"><shadow type=\"positionPicker\"/><block type=\"Sprite_blockCombine_get\"><field name=\"property\">Sprite.y</field><value name=\"mySprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"k7D8@~,f^PwaT*^)7?Z/\">Player_1</field></block></value></block></value><next><block type=\"spritesetvel\"><value name=\"sprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"Ec|Im!!IX8Pe~*~zo^Yz\">projectile</field></block></value><value name=\"vx\"><shadow type=\"spriteSpeedPicker\"/><block type=\"device_random\"><value name=\"min\"><shadow type=\"math_number\"><field name=\"NUM\">50</field></shadow></value><value name=\"limit\"><shadow type=\"math_number\"><field name=\"NUM\">75</field></shadow></value></block></value><value name=\"vy\"><shadow type=\"spriteSpeedPicker\"/><block type=\"device_random\"><value name=\"min\"><shadow type=\"math_number\"><field name=\"NUM\">25</field></shadow></value><value name=\"limit\"><shadow type=\"math_number\"><field name=\"NUM\">50</field></shadow></value></block></value></block></next></block></next></block></next></block></statement><value name=\"IF1\"><shadow type=\"logic_boolean\"><field name=\"BOOL\">TRUE</field></shadow><block type=\"logic_compare\"><field name=\"OP\">LT</field><value name=\"A\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"Sprite_blockCombine_get\"><field name=\"property\">Sprite.x</field><value name=\"mySprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"Ec|Im!!IX8Pe~*~zo^Yz\">projectile</field></block></value></block></value><value name=\"B\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"Sprite_blockCombine_get\"><field name=\"property\">Sprite.left</field><value name=\"mySprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"k7D8@~,f^PwaT*^)7?Z/\">Player_1</field></block></value></block></value></block></value><statement name=\"DO1\"><block type=\"pichangescore\"><field name=\"player\">info.player2</field><value name=\"value\"><shadow type=\"math_number\"><field name=\"NUM\">1</field></shadow></value><next><block type=\"mixer_play_sound\"><field name=\"sound\">music.jumpUp</field><next><block type=\"spritesetpos\"><value name=\"sprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"Ec|Im!!IX8Pe~*~zo^Yz\">projectile</field></block></value><value name=\"x\"><shadow type=\"positionPicker\"/><block type=\"math_arithmetic\"><field name=\"OP\">MINUS</field><value name=\"A\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"Sprite_blockCombine_get\"><field name=\"property\">Sprite.x</field><value name=\"mySprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"#f.b?SPX2EsqPu1X23dc\">Player_2</field></block></value></block></value><value name=\"B\"><shadow type=\"math_number\"><field name=\"NUM\">3</field></shadow></value></block></value><value name=\"y\"><shadow type=\"positionPicker\"/><block type=\"Sprite_blockCombine_get\"><field name=\"property\">Sprite.y</field><value name=\"mySprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"#f.b?SPX2EsqPu1X23dc\">Player_2</field></block></value></block></value><next><block type=\"spritesetvel\"><value name=\"sprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"Ec|Im!!IX8Pe~*~zo^Yz\">projectile</field></block></value><value name=\"vx\"><shadow type=\"spriteSpeedPicker\"/><block type=\"device_random\"><value name=\"min\"><shadow type=\"math_number\"><field name=\"NUM\">-75</field></shadow></value><value name=\"limit\"><shadow type=\"math_number\"><field name=\"NUM\">-50</field></shadow></value></block></value><value name=\"vy\"><shadow type=\"spriteSpeedPicker\"/><block type=\"device_random\"><value name=\"min\"><shadow type=\"math_number\"><field name=\"NUM\">25</field></shadow></value><value name=\"limit\"><shadow type=\"math_number\"><field name=\"NUM\">50</field></shadow></value></block></value></block></next></block></next></block></next></block></statement></block></statement></block><block type=\"spritesoverlap\" x=\"1121\" y=\"1207\"><value name=\"HANDLER_DRAG_PARAM_sprite\"><shadow type=\"argument_reporter_custom\"><mutation typename=\"Sprite\"/><field name=\"VALUE\">sprite</field></shadow></value><value name=\"kind\"><shadow type=\"spritekind\"><field name=\"MEMBER\">Player</field></shadow></value><value name=\"HANDLER_DRAG_PARAM_otherSprite\"><shadow type=\"argument_reporter_custom\"><mutation typename=\"Sprite\"/><field name=\"VALUE\">otherSprite</field></shadow></value><value name=\"otherKind\"><shadow type=\"spritekind\"><field name=\"MEMBER\">Projectile</field></shadow></value><statement name=\"HANDLER\"><block type=\"Sprite_blockCombine_set\"><field name=\"property\">Sprite.vx@set</field><value name=\"mySprite\"><block type=\"argument_reporter_custom\"><mutation typename=\"Sprite\"/><field name=\"VALUE\">otherSprite</field></block></value><value name=\"value\"><block type=\"math_arithmetic\"><field name=\"OP\">MULTIPLY</field><value name=\"A\"><shadow type=\"math_number\"><field name=\"NUM\">-1.1</field></shadow></value><value name=\"B\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"Sprite_blockCombine_get\"><field name=\"property\">Sprite.vx</field><value name=\"mySprite\"><block type=\"argument_reporter_custom\"><mutation typename=\"Sprite\"/><field name=\"VALUE\">otherSprite</field></block></value></block></value></block></value><next><block type=\"Sprite_blockCombine_set\"><field name=\"property\">Sprite.vy@set</field><value name=\"mySprite\"><block type=\"argument_reporter_custom\"><mutation typename=\"Sprite\"/><field name=\"VALUE\">otherSprite</field></block></value><value name=\"value\"><block type=\"math_arithmetic\"><field name=\"OP\">MULTIPLY</field><value name=\"A\"><shadow type=\"math_number\"><field name=\"NUM\">1.1</field></shadow></value><value name=\"B\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"Sprite_blockCombine_get\"><field name=\"property\">Sprite.vy</field><value name=\"mySprite\"><block type=\"argument_reporter_custom\"><mutation typename=\"Sprite\"/><field name=\"VALUE\">otherSprite</field></block></value></block></value></block></value><next><block type=\"mixer_play_note\"><value name=\"note\"><shadow type=\"device_note\"><field name=\"note\">494</field></shadow></value><value name=\"duration\"><shadow type=\"device_beat\"><field name=\"fraction\">BeatFraction.Half</field></shadow></value></block></next></block></next></block></statement></block></xml>",
"main.ts": "controller.player2.onButtonEvent(ControllerButton.Down, ControllerButtonEvent.Pressed, function () {\n    players = 2\n    controller.player2.moveSprite(Player_2, 0, 100)\n})\ncontroller.player2.onButtonEvent(ControllerButton.Up, ControllerButtonEvent.Pressed, function () {\n    players = 2\n    controller.player2.moveSprite(Player_2, 0, 100)\n})\nsprites.onOverlap(SpriteKind.Player, SpriteKind.Projectile, function (sprite, otherSprite) {\n    otherSprite.vx = -1.1 * otherSprite.vx\n    otherSprite.vy = 1.1 * otherSprite.vy\n    music.playTone(494, music.beat(BeatFraction.Half))\n})\nlet Player_2: Sprite = null\nlet players = 0\nplayers = 1\nlet Picture = image.create(scene.screenWidth(), scene.screenHeight())\nfor (let index = 0; index <= scene.screenHeight(); index++) {\n    if (index % 6 < 4) {\n        Picture.setPixel(scene.screenWidth() / 2, index, 1)\n    }\n}\nscene.setBackgroundImage(Picture)\nlet Player_1 = sprites.create(assets.image`Player 1`, SpriteKind.Player)\nPlayer_1.setPosition(8, 60)\ncontroller.moveSprite(Player_1, 0, 100)\nPlayer_1.setStayInScreen(true)\nPlayer_2 = sprites.create(assets.image`Player 2`, SpriteKind.Player)\nPlayer_2.setPosition(152, 60)\nPlayer_2.setStayInScreen(true)\nlet projectile = sprites.createProjectileFromSprite(assets.image`Ball`, Player_1, randint(50, 75), randint(25, 50))\nprojectile.x += 3\nprojectile.setBounceOnWall(true)\nprojectile.setFlag(SpriteFlag.ShowPhysics, false)\ninfo.player1.setScore(0)\ninfo.player2.setScore(0)\ngame.onUpdate(function () {\n    if (projectile.x > scene.screenWidth() / 2 && players == 1) {\n        if (projectile.y > Player_2.y) {\n            Player_2.y += 2\n        } else {\n            Player_2.y += -2\n        }\n    }\n})\ngame.onUpdate(function () {\n    if (projectile.x > Player_2.right) {\n        info.player1.changeScoreBy(1)\n        music.jumpUp.play()\n        projectile.setPosition(Player_1.x + 3, Player_1.y)\n        projectile.setVelocity(randint(50, 75), randint(25, 50))\n    } else if (projectile.x < Player_1.left) {\n        info.player2.changeScoreBy(1)\n        music.jumpUp.play()\n        projectile.setPosition(Player_2.x - 3, Player_2.y)\n        projectile.setVelocity(randint(-75, -50), randint(25, 50))\n    }\n})\n",
"pxt.json": "{\n    \"name\": \"JS Pong Personally Built Empty Test\",\n    \"description\": \"\",\n    \"dependencies\": {\n        \"device\": \"*\"\n    },\n    \"files\": [\n        \"main.blocks\",\n        \"main.ts\",\n        \"README.md\",\n        \"assets.json\",\n        \"tilemap.g.jres\",\n        \"tilemap.g.ts\",\n        \"images.g.jres\",\n        \"images.g.ts\"\n    ],\n    \"targetVersions\": {\n        \"branch\": \"v1.7.22\",\n        \"tag\": \"v1.7.22\",\n        \"commits\": \"https://github.com/microsoft/pxt-arcade/commits/fa9cc16632907b4dd59f733b62e573beded922dc\",\n        \"target\": \"1.7.22\",\n        \"pxt\": \"7.3.23\"\n    },\n    \"preferredEditor\": \"tsprj\"\n}\n",
"tilemap.g.jres": "{\n    \"transparency16\": {\n        \"data\": \"hwQQABAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true\n    },\n    \"*\": {\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"dataEncoding\": \"base64\",\n        \"namespace\": \"myTiles\"\n    }\n}",
"tilemap.g.ts": "// Auto-generated code. Do not edit.\nnamespace myTiles {\n    //% fixedInstance jres blockIdentity=images._tile\n    export const transparency16 = image.ofBuffer(hex``);\n\n    helpers._registerFactory(\"tile\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"transparency16\":return transparency16;\n        }\n        return null;\n    })\n\n}\n// Auto-generated code. Do not edit.\n"
}
```
 
 
 
