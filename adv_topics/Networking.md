# Networking advanced topic presentation outline

## Presentation 1

* Networking and Games [Jumps off of end of Networking 0]  (estimated time: 10 min)

	* Focus on broad game issues

	* Lag compensation

		* Causes of Lag and Common Solutions

	* Client-side prediction and interpolation

		* Rollback vs Delay-Based

* TCP structure and implementation in Rust  (estimated time: 20 min)

	* Basic building blocks

		* Sockets, TcpListeners, TcpStreams

	* client - client vs client - server

		* pros cons

* Applications to our game [client - client]  (estimated time: 15 min)

	* Explain differences between real time and turn based

		* Don’t need to respond/update every millisecond, only on turn actions

	* Explain our current implementation plan

		* Client to client over LAN

		* Why we chose it over other options

	* How to deal with player disconnecting\reconnecting

	* Latency/timeout

## Presentation 2 - Real-Time / Low-Latency Multiplayer Networking

* Packets (about 5- 10 min)
	* Rust only sends byte buffers
		* How to pack X into byte buffer
		* How to unpack X from byte buffer
	* Converting Primitives to bytes / byte buffers
	* Converting Structs/Enums/Collections/etc. to primitives for byte buffers
* Real-Time / Low-Latency Multiplayer Networking (About 5 - 10 min)
	* What does real-time mean for the main gaming genres?
		* What is ping?
		* “40 to 60 ms is considered real-time”
		* “Over 170 games will reject if ping > 100ms” - https://britishesports.org/news/ping-latency-and-lag-what-you-need-to-know/ (In context of esports competitions)
	* Packet Size - Latency increases with packet in linear fashion until MTU limit is hit then packet needs to be fragmented, increasing latency.
	* Time it takes to pack and unpack a given packet
	* Difference between WAN and LAN
* Multithreading (About 5 min)
	* Show off Multithreaded web-server from Rust book Project from chapter 20
* Ways to prevent cheating and malicious connections (About 10 min)
	* How is cheating detected/prevented/deterred
	* Malicious connections detection/prevention/deter?
* Our own implementation -- Honor Code P2P (About 15 min)
	* UDP -- Peer to Peer
	* How to connect
		* Static SocketAddresss
		* non-static SocketAddresses
		* LAN vs. WAN
	* What our packets pack
		* We always need agreement - dynamic objects have one-and-only-one owner
		* Send and receive minimum necessary (without overengineering)
		* What is sent
			* Local player position and animation frame
			* Local portal(s) position
			* Block pickups
		* What is received -- basically same as sent
			* Remote player position
			* Remote player portal updates
			* If applicable, remote player block holding updates
	* Why one player only controls one portal / one set of portal
		* Otherwise many bug opportunities

## Presentation 3

* Authentication processes
  * Importance of authentication
    * Possibility of 'cheating' players
    * Possibility for miscellaneous/corrupted connections to affect an unrelated game
  * Overview of potential implementations
* Event flow & polling
  * Refresh of event driven programming => already had a lecture on the idea but a refresh is good for expanding on how it’s needed in the project
    * Action => reaction style that is most notably seen on websites and other interactive media
    * Usually, objects will wait/listen for some kind of input/interaction
    * e.x. => JS on websites `onclick=`, buttons/input/links, player interactions in video games (controls)
    * This makes it so that programs can run more efficiently, only working on things as they are requested to do so
  * For the sake of networking
    * Actions of one player can be “converted” into events to be received by the second player
    * instead of sending every event as they happen though, keep a list of the actions taken and send them at specific intervals
      * as a player moves, attacks, etc. this is kept track of and eventually sent to the second user’s end where everything is updated to comply with the actions the first player has taken
      * visual example of an average player turn and how that would be sent over to the server/other player
* Our Implementation
  * Networking structure
    * One shared server that communicates with all client connections
    * “Host” client as the owner of the room
    * “Peer” client joins a created room
  * Room creation process
    * Room code generation
    * Random token generation
    * Request from ‘host’ client: () -> room code + token
    * Request from ‘peer’ client: (room code) -> token
    * Any future requests: (room code + token) -> response
  * Polling details
    * Techniques to avoid frame loss (postponing polls, max conn. length, fixed data size)
    * Updating the game state on each client

