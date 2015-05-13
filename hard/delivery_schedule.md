http://en.wikipedia.org/wiki/Vehicle_routing_problem
http://www.mafy.lut.fi/study/DiscreteOpt/CH6.pdf
http://wps.prenhall.com/wps/media/objects/9434/9660836/online_tutorials/heizer10e_tut5.pdf

# Title

Customer Unit Delivery Scheduling

# Difficulty

Hard

# Description

You run a business where you sell doohickies, and business is booming. You're customers are all local, but you're just getting off the ground and you don't have a large fleet of trucks, just one guy. Your truck has a finite capacity, and you have to keep costs down as you make deliveries - minimize milage, maximize deliveries, etc. That's where today's challenge program comes in. 

As you make delivery runs, your truck will run out of enough doohickies and so you have to return to the depot and refill it. 

# Input Description

You'll be given a line with an integer *N*, which tells you how many doohickies your truck can hold, and a two-tuple where the doohickie depot is. Then you'll be given a line with another single integer *M*, which tells you how many customers to read. Each customer line (of which there are *M*) will be a two-tuple telling you the point where the customer is and then how many units they want. 

# Output Description

Your program should emit the sequence of stops you need to make, including depot stops, that *minimizes* the miles driven. You must deliver enough units for every customer when you stop! No customer will ask for more than *N* doohickies (your truck's capacity), and you *should* expect to travel from one customer to the next without stopping at the depot if you can deliver enough units at once. 

# Challenge Input

	40 (20,20)
	9
	10 (20,8)
	15 (31,20)
	18 (13,21)
	17 (30,20)
	3 (20,10)
	5 (11,29)
	9 (28,12)
	4 (14,14)
	6 (32,8)