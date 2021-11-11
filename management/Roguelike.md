# CS1666 Roguelike Management weeks

1. 9/15 - 9/21
	* Manager: Adam Wachowicz
	* Goals:
		1. Get project description and goals approved
1. 9/29 - 10/5
	* Manager: Josh Friedman
	* Goals:
		1. Create team credits sequence for the game
1. 10/6 - 10/19
	* Manager: Marshall Lentz
	* Goals:
		1. Implement player movement
			* Allow the player to move around the game world
			* Make the camera follow the player
			* Implement basic player attack
		2. Implement simple enemy movement
			* Have the enemies move around randomly when idle
			* Have one kind of enemy chase the player and attack when close
		3. Procedural generation: implement the starting room
			* Create one room for the player to start in
			* Keep the players within the bounds of the room by implementing wall collisions
		4. Physics engine: begin experimenting with knockback
			* When the player attacks an enemy, have the enemy be knocked back a certain distance
1. 10/20 - 10/26
	* Manager: Zirui Huang
	* Goals:
		1. Frame independent movement
		     * Movement 
		     * Melee attack cooldown and damage
		     * Ranged attack cooldown, damage, and speed
		2. HUD 
		     * Basic health bar (implement immunity after taking chunk damage)
   		     * A space for money
   		     * A space for mana (maybe implement mana since it should just be a number and an if statement?)
   		     * Equipped weapons and abilities
		3. Attacks
		     * Ranged enemy
		     * Ranged player attack
		4. Procedural Generation Team:
		    * Outline for presentation
		    * Begin generation algorithm
		
1. 10/27 - 11/2
	* Manager: Victor Mui
	* Goals:
		1. Finalize first playable level
		    * Add procedural generation for new rooms
		    * Add hallways for new rooms
		2. Add Crates
		    * Crates can be moved
		3. Add number counter for coins on HUD
		4. Add different type of projectiles
		    * Fireball
		    * Slimeball (maybe bouncy / ricochet)
1. 11/3 - 11/9
	* Manager: Daniel Stirling
	* Goals:
		1. Merge procedural generation system with working room from previous weeks
		    * Create a start and end position and ensure no enemies spawn in these rooms. 
		    * Add random enemy/object spawning to individual rooms 
		2. Fix collision
		    * Crates can be moved
		    * Ensure player doesn’t get stuck on walls, objects, and corners 
		    * Fix corridor hit boxes to allow player to traverse more easily
		    * Make sure projectiles and enemies cannot go through obstacles
1. 11/10 - 11/16
	* Manager: Davon Allensworth
	* Goals:
		1. Implement scene shifting
		    * Player can move from one level to another via stairs.
		2. Implement raycasting method of detecting rigid body collisions
		    * Collisions are detected via casting rays in direction of object velocity
        3. Begin implementation of "absorption" mechanic
            * Upon pressing E key, the player can absorb an enemy's ability.
        4. Add a new enemy type
            * Including new ability player can absorb.
        
1. 11/17 - 11/30
	* Manager: NAME
	* Goals:
		1. GOALHERE
		...
1. 12/1 - 12/7
	* Manager: Yihua Pu
	* Goals:
		1. GOALHERE
		...

