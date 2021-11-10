# CS1666 CardRPG Management weeks

1. 9/15 - 9/21
	* Manager: Jacob Bonhomme
	* Goals:
		1. Get project description and goals approved
1. 9/29 - 10/5
	* Manager: Max Niederer
	* Goals:
		1. Create team credits sequence for the game
1. 10/6 - 10/19
	* Manager: Merrick Johnston
	* Goals:
		 1. create the entire combat system
		 	 1. setup backend data structures such as;
				 1. player: overaching structs for tracking the combat per player
				 1. deck: queues built into players holding keys to a hash table that fills in random order from the players 
					available cards
				 1. hand: a vector to hold copies of cards vurrently in hand
				 1. Cards:a hashtable holding all cards for quick access and removing the need to copy each card into queue outside
					the combat to pull from
			 1. begin setting up other systems
				 1. start implimenting the overworld movement (specifically movement around the wilds area)
				 1. get basic starting screen set up (get a play and quit button)
				 1. make card assets
	
1. 10/20 - 10/26
	* Manager: Gabe Balannik
	* Goals:
		1. Create the framework for loading assets
			1. load card textures into player deck
			2. load list of cards and their effects from file
			3. load spritesheets into overworld and render
		2. Scene transitions
			1. be able to transition between overworld and battle
			2. add function to menu screen with play, quit, credits buttons
			3. fixed timestep for animations
1. 10/27 - 11/2
	* Manager: Louisa Li
	* Goals:
		1. Playable combat system/engine
			- Each player will have a deck size of 20
			- Starting hand size of 5, max hand size of 7
			- Drawing/Synergistic attack mechanics
			- Mana/Energy management
			- Win/Lose conditions
				- Namely HP or running out of cards
			- Assortment of cards
				- 4 standard attack cards
				- 2 status attack cards
				- 3 defend cards
				- 2 heal cards
				- 2 distinct status cards
			- Scripted Enemy
				- There will be a scripted boss fight. This fight will simply show how the battle system works.


1. 11/3 - 11/9
	* Manager: David Bieler
	* Goals:
		1. GOALHERE
		...
1. 11/10 - 11/16
	* Manager: Derek Halbedl
	* Goals:
		1. Implement enemy variety
			- Create multiple themed card decks in the back end for enemies to use in battle
			- Develop a way to attach decks to specific enemies (whether randomly and/or ensuring unique decks belong to one enemy)
		2. Add turn counters to status effects showing the remaining turns
		3. Transition back to the overworld after a battle is won/lost
			- Play will resume from the previous overworld position.
			- Enemy will no longer be there to avoid instantly triggering another battle
		4. Complete backend decision tree data structures and begin implementation of CPU opponent minimax algorithm
		5. Client to Client communication via a Server
			- Be able to demonstrate clients sending to and receiving data from the server in some capacity
		
1. 11/17 - 11/30
	* Manager: NONE
	* Goals:
		1. GOALHERE
		...
1. 12/1 - 12/7
	* Manager: Emilio Filippi
	* Goals:
		1. GOALHERE
		...

