# Physics advanced topic presentation outline

## Presentation 1: platformer

* Overview of what physics is in games, what is a physics engine, how physics is implemented in games typically : 35 minutes
	* Classical mechanics/Newtonian physics: Newton’s laws for gravity, etc			(10 minutes)
	* Rigid-body dynamics: kinematics, Newton's laws of motion, collisions			(10 minutes)
	* Soft-body dynamics: fluid dynamics, Navier–Stokes equations, Particle systems		(10 minutes)
	* How we expect to implement basic physics into our game				(5 minutes)
* How we expect our portal mechanics to work : 10 minutes
	* Projectiles
	* Overview, location moving
	* “Speedy thing goes in, speedy thing comes out”
	* How objects moving through portals are to be handled
	* In-depth diagrams of collision and mechanics

## Presentation 2

* General Physics Engine Overview (5 mins)
	* Quick recap Physics 1 presentation, highlighting aspects especially relevant to our game
* Detecting Collisions (15 mins)
	* Our Implementation for Rigid Body Collision Detection
		* Ground/Player Collisions
		* Obstacle/Player, Obstacle/Obstacle, Terrrain/Obstacle Collisions
* Applying Forces (15 mins)
	*  General overview of our approach to applying forces
	*  Analysis of the forces most prominent in our game & how they are applied:
		*  Gravity
		*  Rotation, Rotational Inertia, Torque
		*  Collision Forces, Multibody Collsions & "Particle" Tracking
		*  Friction 
		*  Buoyancy
* Constraints & Assumptions in our Implementation (10 mins)
	* Emphasize where & why we are making assumptions when simulating physical phenomena
		* Forces we are neglecting
		* Treating objects & Mass
		* Hitboxes
		* Player's x bounded screen location

## Presentation 3

* Topic 1
	* Details
	* Details
	* Details
* Topic 2
	* Details
	* Details
	* Details
