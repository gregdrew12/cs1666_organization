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

* General Physics Engine Thinga (10 mins)
	* Quick recap Physics 1 presentation, building on aspects especially relevant to our game
	* Intro to Rotational Motion Physics
* Applying Forces (25 mins)
	*  General overview of our approach to applying forces
	*  Deatiled analysis of the forces most prominent in our game & how they are applied:
		*  Gravity
		*  Rotation, Rotational Inertia, Torque
		*  Collision Forces, Multibody Collsions & "Particle" Tracking
		*  Friction 
		*  Buoyancy
* Constraints & Assumptions in our Implementation (10 mins)
	* Emphasize where & why we are making assumptions when simulating physical phenomena
		* Forces we are neglecting
		* Treatment of objects & mass
		* Hitboxes
		* Player's x bounded screen location

## Presentation 3: Roguelike

* Introduction (5 min)
	* Quick summary of Newtonian physics
	* Emphasis on linear momentum
* Top Down physics (10 min)
    * Uniqueness of our game (top-down)
	* No gravity
	* Ballistics projectiles and ricochet
	* Raycast collision detection based on vectors
* Collision Detection (10 min)
	* Check all rigidbodies for collisions
	* Benefits of raycasting
* Collision resolution (10 min)
	* Impulses and Linear algebra
	* Common bugs caused by processing
* Closing Statements (5 min)
	* Show the current state of the physics system
	* Talk about possible improvements
