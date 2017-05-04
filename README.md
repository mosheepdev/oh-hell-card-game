# Oh Hell! card game
A very modest application to play the Oh Hell! card game with your friends.

## The rules, roughly

The Oh Hell! card game (it has many different names) is a trick based card game. At each deal, you have to bet the number of tricks you will do.
The trump changes every deal, and is decided randomly.
The first deal, each player receives 1 card in hand. The second deal, 2. That goes up to the point you decide, then it goes back to 1.
There is a special rule for 1 card in hand. When it happens, you don't see your card, but the cards of the other players.

When a deal starts, each player bets on the number of tricks they will win. The constraint being that the total sum of the tricks bet by the players can't be the number of cards in hand.

### Points

Add the end of each deal, players win or lose points according to whether they manage to fulful their contract.
- if a player does as forecast, they get 10 points plus the number of tricks won
- if a player does not, they loses the absolute value of the difference between their bet, and the actual number of tricks they managed to take.


## How to make it work

This project uses [Electron](http://electron.atom.io/) as engine. You need to have Electron installed on your machine.
[Scala.js](https://www.scala-js.org/) creates javascript files for you to use with Electron.
Once compiled, you will have to copy-paste de files in the right folders.
- the gamemenus related files must go into electron/gamemenus/js-files
- the server related files must go into electron/server/js-files
- the main related files must go into electorn/mainprocess
- the gameplaying related files must go into electron/gameplaying/js-files

### Steps to follow (at least for Windows):
- download [Electron](http://electron.atom.io/)
- download the [scalajs-ui](https://github.com/sherpal/scalajs-ui) library
- `publishLocal` it using [sbt](http://www.scala-sbt.org/)
- download this project
- compile it using `fastOptJS` or `fullOptJS` using [sbt](http://www.scala-sbt.org/)
- copy-paste the files to the right folders
- open the Electron app and drag the electron folder in it.
Remark: if you want to use the `fullOptJS` files, you will have to change all the `require` calls in the html files.

## How to play

One of the player has to create a server from the app, by going into "Create Server" and entering the port the server will be listening. Then that player can host a game by going into "Host Game", chose a name for theirselfs, a name for the game (that basically behaves like a password, although no encryption is used), the address of the computer of the server (if the player created the server on their computer, it is localhost) and the port.
To join a game, the same information must be provided.

Note that the server can be on a computer different from the one of each player.

Remark: if you want to play with people that are not on the same wifi network as you are, you will probably have to do some extra work. Indeed, you have to set up a special NAT rule on your router, to redirect incoming packets coming through the game port.

## GUI

The GUI is currently utterly ugly, and this comes from my lack of artistic fiber. Feel free to customize the menus and the game GUI itself.

## Upcoming features and fixes
- save game name and player name when he or she join/host a game
- in the menu, having more feedback from the server (creation/dead...)
- when clicking on launch game, ask confirmation by showing all game detail
- fix the errors in server when a game ends
- allow to kick someone from the game
- add a "card viewer", to help people for which the cards would be too small.

