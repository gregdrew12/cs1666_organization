# Team Castle Quest

## Canonical game repo URL:

https://github.com/KalebRaymond/CS1666-Tactical-RPG

## Team Members
* Advanced Topic Subteam 1: AI

	* Kaleb Raymond
        * Pitt ID: kwr7
        * Github Username: KalebRaymond
    * Alexander Kwiatkowski
        * Pitt ID: ajk175
        * Github Username: AlexKwi
    * Colin Woelfel
        * Pitt ID: cjw102
        * Github Username: cjw102
    * Jared Carl
        * Pitt ID: jmc316
        * Github Username: jmc316


* Advanced Topic Subteam 2: Networking

	* Bianca Finamore    
        * Pitt ID: amf192
        * Github Username: BiancaFinamore
    * Jake Baumbaugh
        * Pitt ID: jtb122
        * Github Username: JakeBaumbaugh
    * Shane Josapak
        * Pitt ID: shj63
        * Github Username: shjosa
    * James Fenn
        * Pitt ID: jaf208
        * Github Username: fennifith

## Game Description

Castle Quest is a tactical RPG in the same style as games like Fire Emblem and Advance Wars. The game will feature a single player mode, where the player will face against an enemy AI, and a multiplayer mode, which will be identical to the single player but with the enemy AI replaced by another player.

At the start of the game, both teams start in opposite corners of the map. Both teams start with a castle and a few units spawned around their castle. Units come in three classes: melee, archer, and mage. Each class has unique stats, including move distance, attack range, attack damage, etc. Teams take turns moving their units, trying to reach the other team's castle and defeating enemy units while also protecting their own castle and units. The game continues until one of the teams captures the other's castle (by placing a unit over top the castle for 3 consecutive turns) or defeats all of the other's units.

* Grid-based Tactical RPG across one large map
    * Top-down view, at least 48x48 tiles
* Third, AI-controlled team (barbarians) located throughout map in small groups
    * Either the player or the enemy can defeat them for a chance of gaining additional party members
    * Barbarians are limited to melee & archer classes
* Each team (player 1, player 2/enemy AI, and barbarians) takes turns with the ability to move and attack opposing units within attack range
* Game continues until either player or enemy defeats the other
    * Defeating all of the other team’s units (Total Party Kill)
    * Capturing the other team’s castle (Placing a unit on their castle for three consecutive turns)
    * Barbarians do not contribute to win/lose conditions


## Advanced Topic Description

### AI

* Simple implementation for barbarians (melee and ranged with no magic)
	* Pursues and attacks any non-barbarian unit that comes into aggro range
	* Otherwise remains idle
* More complicated enemy AI for singleplayer (melee, archer, and magic)
	* Enemy AI must decide between pursuing the player or attacking barbarians to gain additional units
	* Enemy must pursue the player's castle while also strategically keeping some units close to the enemy castle to defend it.
	* Possible implementations include Minmax with Alpha/Beta Pruning, or a Finite State Machine
	* Enemy AI will take many factors of the game state into account into order to score each potential move
		* Health of each unit
    		* Attack range of each unit
    		* Damage output of each unit
    		* How close each unit is to a barbarian
    		* How close each unit is to a player unit
    		* The player unit's health, damage output, class, etc.
    		* How much their castle is currently threatened
    		* How much the player's castle in currently threatened


### Networking

* A server application running on a hosted server application will be running to provide multiplayer support.
* Upon selecting the multiplayer game mode from the menu, players can either create a room to generate a join code, or enter a code given to them by another player.
    * When creating a room, the server will provide a join code to the player to share with their opponent.
* When two players have connected to a server, they will be entered into a game on opposite sides of the map, where they will try to defeat the other player.
    * The second human player replaces the enemy AI of the singleplayer mode.


## Midterm Goals

* Single player: starting the game spawns players, enemies, and barbarian units on 48x48 map
* Basic movement implemented for player and barbarians
    * Player: Clicking on a unit and then clicking on any tile teleports the unit to that tile. After moving, a context menu appears that allows you to end the unit's turn.
    * Barbarian AI: If at least one player unit is within a certain range, barbarian units will move towards the closest player unit. Otherwise, the barbarian unit will not move.
    * Enemy AI team will simply skip turn
* Implement basic turn order functionality
    * Turn order goes player -> enemy AI -> barbarians, continues indefinitely 
    * “End turn” button for player skips remaining units & continues the game
* Multiplayer room creation and joining
    * Successfully joining the room alerts both players


## Final Goals

* 20% - Completed AI for enemy team & barbarians
    * Barbarians roam within a small radius until a player or enemy enters within their aggro range, upon which the barbarian will pursue the player/enemy and attack them
    * Enemy AI will be more advanced. 
    	* Enemy should choose whether to prioritize attacking barbarians that are out of the way versus going directly for the player.
    	* Enemy should reserve some units to defend their castle rather than go after the player's castle
* 20% - Functioning multiplayer
    * Joinable rooms with keys
    * Communicate turn order & character actions
    * The winning team receives a win message, while the loser receives a lose message
* 5% - Implement archer and mage classes for player and enemy teams. Implement archer for barbarian team
* 5% - Complete map design with all objectives (player/enemy castles, obstructions, predetermined barbarian spawnpoints)
* 5% - Additional unit spawning
    * After killing a barbarian, there is a random chance that the player will receive an additional unit spawned at their castle
    * Player can choose which class that unit will be
* 15% - Implement combat system & user interaction
    * Hovering over player's unit displays a cursor around the unit
    * Clicking on a player's unit will make a context menu appear with options to make the unit move or attack
    * Clicking on the "move" option will highlight the tiles that the unit can move to
    	* Clicking on a highlighted tile will move the unit to that tile
    * Clicking on the "attack" option will highlight the tile in the unit's attack range
    	* Clicking on a highlighted tile that contains a non-player unit will make the player unit attack that unit
    * After a player unit has moved and attacked, it will be grayed out, and will be unable to perform any more actions until the player's next turn
* 5% - Implement win & lose conditions
    * Entire team is defeated or player keeps one unit in opposing team’s castle for three consecutive turns


## Stretch Goals

* Additional Classes
    * Two new classes that offer different strategic advantages over other classes, allowing for more varied approaches to combat.

* Additional Objectives
    * Barbarian encampments as well as a central barbarian fort (instead of having lone barbarians randomly placed throughout the map) to allow for more chances to recruit new units
    * Utilizes the same capture mechanic as the player castles
    * When captured would provide some benefit to the player
