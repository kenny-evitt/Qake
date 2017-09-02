# kenny-evitt/Qake

## The Original Qake

Play the original game here: http://qake.se/demo

Also on Chrome Experiments: https://www.chromeexperiments.com/experiment/qake

## Description

Qake is a voxel-engine written in Javascript with ThreeJS as graphic library.

kenny-evitt/Qake is a fork of Qake.

## Testing

From the root directory of the repo:

 1. Unpack the tarball with the nodejs server:

```shell
    tar xvfz qake_server.tar.gz
```

 2. Install Node.js and run `cd server; nodejs server.js`.

 3. Point your browser to *http://localhost:8081*.

## Screenshot (Original Game)

![alt tag](https://raw.github.com/lallassu/Qake/master/screenshot.png)

## The Code

### The Server

*server/server.js* is the server. It uses the Node.js 'http' module to serve any files in the repo (or whichever directory it's deployed).

### The Client

#### *index.html*

*index.html* is the game web page served by the server and includes the JavaScript client code.

The JavaScript game logic is almost completely encapsulated in the `Game` class in *js/main.js*.

The code in this file handles logic for three buttons at the top of the game.

#### *js/main.js*

*js/main.js* contains the `Game` class. Starting a game is just:

```js
        game = new Game();
        game.Init();
```

[from *index.html*]

#### The Game Loop

The function `update` function of the `Game` class is the game loop. It draws the 'player', 'physics' [?], and the 'world'.

The loop only runs at most, roughly, 60 times per second.

#### The Player

*js/player.js* contains the `Player` class.

##### Collision Detection

The function `CanMove` handles collision detection. Commenting out the checking code (i.e. always returning `true`) allows the player to walk their character thru objects and move their character beyond the 'base' in the game; the player character (PC) doesn't fall past the boundary either.

The PC *can* walk thru the 'flowers'/'mushrooms' however, even with collision detection running.

The PC can also move past the 'world boundary' by 'walking' or 'jumping' sideways.

The PC can jump when the player presses <kbd>Space</kbd> and the PC can 'fly' by holding <kbd>Space</kbd>.

The PC can not only move, but will also get 'stuck' if they jump/fly too far up (probably above the world boundary height).

##### Input

The function `KeyDown` implements keybindings.