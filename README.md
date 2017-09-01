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