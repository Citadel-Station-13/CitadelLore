---
title: Guide to Mapping
permalink: wiki/Guide_to_Mapping/
layout: wiki
tags:
 - Guides
---

Other related guides: [Understanding SS13
code](/wiki/Understanding_SS13_code "wikilink") and [SS13 for experienced
programmers](/wiki/SS13_for_experienced_programmers "wikilink")

Pre-commit checks
-----------------

\- Are all the floors with or without air, as they should be? (regular
or airless)  
- Does the area have an APC?  
- Does the area have an Air Alarm?  
- Does the area have a Request Console?  
- Does the area have lights?  
- Does the area have a light switch?  
- Does the area have enough intercoms?  
- Does the area have enough security cameras? (Use the verbs under
Mapping for help)  
- Is the area connected to the scrubbers air loop?  
- Is the area connected to the vent air loop? (vent pumps)  
- Is everything wired properly?  
- Does the area have a fire alarm and firedoors?  
- Do all pod doors work properly?  
- Are accesses set properly on doors, pod buttons, etc.  
- Are all items placed properly? (not below vents, scrubbers, tables)  
- Does the disposal system work properly from all the disposal units in
this room and all the units, the pipes of which pass through this
room?  
- Check for any misplaced or stacked piece of pipe (air and disposal)  
- Check for any misplaced or stacked piece of wire  
- Identify how hard it is to break into the area and where the weak
points are  
- Check if the area has too much empty space. If so, make it smaller and
replace the rest with maintenance tunnels.  

General Station-wide Mapping Guidelines
---------------------------------------

### Atmospherics

-   Each area should have EXACTLY one air alarm (Exceptions are only
    possible if a room has scrubbers or vent pumps on different
    frequencies)
-   Each ROOM (Walled off space) should have at least one vent pump and
    scrubber, which is properly connected to it's respective loop
-   The air supply loop's pipes should be colored blue
-   The scrubbers loop's pipes should be colored red

### Power

-   Each area (which requires power) should have exactly one APC

Atmospherics
------------

### Pipes and manifolds

Atmospherics releases it's cocktail of gases into the air supply loop
(blue pipes). The station is also equipped with a scrubber loop, which
filters unwanted gases and sends them back to atmospherics via the
scrubber loop (red pipes).

If you're expanding the air supply loop (blue pipes) use the objects in
/obj/machinery/atmospherics/pipe/simple/supply/visible or ../hidden
depending on if you want it to show above floors or below them. For
manifolds use the objects in
/obj/machinery/atmospherics/pipe/manifold/supply/visible and ../hidden.

If you are expanding the scrubber loop (red pipes) use the objects in
/obj/machinery/atmospherics/pipe/simple/scrubbers/visible or ../hidden
depending on if you want it to show above floors or below them. For
manifolds use the objects in
/obj/machinery/atmospherics/pipe/manifold/scrubbers/visible and
../hidden.

If you are however building a pipe network which has nothing to do with
the air supply or scrubbers loop, you should use the objects in
/obj/machinery/atmospherics/pipe/simple/general/visible or ../hidden.
For manifolds use the objects in
/obj/machinery/atmospherics/pipe/manifold/general/visible and ../hidden.
To manually set these ones up you will need to set the following
parameters (Assuming you are properly using the visible/hidden
categories)

` color = ""  // select from "" for gray or "red", "blue", "cyan", "green" or "yellow"`  
` icon_state = "intact" //The color of pipes is set to what the color variable says at round `  
` start irrespective of this, however to make mapping easier, please set the icon_state variable `  
` to the correct one here too. Please refer to the table below for icon_states for different colors. `

| Color  | Visibility | icon\_state (pipe) | icon\_state (manifold) |
|--------|------------|--------------------|------------------------|
| Gray   | Visible    | intact             | manifold               |
| Gray   | Hidden     | intact-f           | manifold-f             |
| Red    | Visible    | intact-r           | manifold-r             |
| Red    | Hidden     | intact-r-f         | manifold-r-f           |
| Blue   | Visible    | intact-b           | manifold-b             |
| Blue   | Hidden     | intact-b-f         | manifold-b-f           |
| Cyan   | Visible    | intact-c           | manifold-c             |
| Cyan   | Hidden     | intact-c-f         | manifold-c-f           |
| Green  | Visible    | intact-g           | manifold-g             |
| Green  | Hidden     | intact-g-f         | manifold-g-f           |
| Yellow | Visible    | intact-y           | manifold-y-f           |
| Yellow | Hidden     | intact-y-f         | manifold-y-f           |

### Air Alarm

Every single area (with scrubbers and/or vent pumps) should have exactly
one air alarm. More than one should be placed if vent pumps or scrubbers
use different radio frequencies than the default one (1439).

### Scrubbers (Station air supply)

Every room (ie. walled off space) except for maintenance hallways should
have at least one scrubber.

The vars you need to set for this one specifically are:

` on = 1`  
` scrubbing = 1`  
` scrub_co2 = 1`  
` scrub_toxins = 0`  
` scrub_n2o = 0`  
` volume_rate = 120`  
` panic = 0`  
` frequency = 1439`

And make sure the **id\_tag** is the default one (null)

Also ensure the scrubber is connected to the scrubber loop!!

### Vent Pumps (Station air supply)

Every room (ie. walled off space) except for maintenance hallways should
have at least one vent pump.

The vars you need to set for this one specifically are:

` on = 1`  
` pump_direction = 1`  
` pressure_checks = 1`  
` frequency = 1439`

And make sure the **id\_tag** is the default one (null)

Also ensure the vent pump is connected to the air supply loop!!

### Disposals

Disposals is something that you will probably wind up having to play
with atleast once.

Disposals operates in a loop, starting and ending at the Cargo Office.
From here it rotates around the station and eventually returns. There
are branches off this main loop. "Trash" branches which join the main
branch with a junction. And "Mail" branches which use a sortjunction.
T**he important thing to remember when adding new branches is you do not
mix mail branches with trash branches.**

#### Trash Branches

<img src="Trash_pipes.png" title="fig:Example of Junctions." alt="Example of Junctions." width="150" />
<img src="Junction.png" title="fig:Junction.png" alt="Junction.png" width="150" />
Trash branches can have sub branches to other disposal cans as long as
their junctions all "point" towards the main loop, and when it gets to
the main loop has a junction that points in the direction the main loop
is going (usually clockwise) in the direction of the main loop.

The junction is **/obj/structure/disposalpipe/junction**.

When placing the junction don't worry about how it's rotated, we'll get
to that. Worry about which pipe the arrow is pointed and we'll rotate it
once it's placed. Place it and then we need to realize which cardinal
direction the arrow should point. Edit the variables of the junction and
look for
"[dir](/wiki/Understanding_SS13_Code#Direction_.28dir.29_var "wikilink")". Use
that link to set the value the "exit" end should point towards. So if we
want the arrow to point north we would set it to 1, south 2, and so on.

That's it. If you are editing a link in the main loop make sure it's
going with the flow, don't have two junctions that point back at each
other it will cause an infinite loop and that's bad.

#### Mail branches

<img src="Sortjunction.png" title="fig:Sortjunction.png" alt="Sortjunction.png" width="150" />
Mail branches use a sorting junction
(**/obj/structure/disposalpipe/sortjunction**) to go from the main loop
to the destination, it should not branch off further or have trash boxes
branched into it as well, it will cause problems. sorting junctions are
placed in the same way regular junctions are. sort junctions should only
be on the main loop, do not use them elsewhere. What sort junctions do
is look for a tag from a package, if it matches the ID of the office it
is checking for it redirects the package to it's "Sort Direction" Sort
junctions either sort to the left or the right, their *dir* variable
will decide which direction the "Default" is (not sort direction, our
picture example's dir value is to the east so it's 4). Luckily there are
plenty of icons for this item so you can choose which one works and can
probably find the correct directions. If not you can either edit
*iconstate* "pipe-j1s" vs "pipe-j2s" (changes which side the sort side
is on of the pipe and set *dir* until you get it the way you want it.
Once you have it placed you need to look up the number you will be
placing in it's *sortType* variable, this can be determined by a list in
**code/setup.dm** and counting through the list for your destination if
you need to make new destinations you need to edit that list.

**var/list/TAGGERLOCATIONS**

At the time of this writeup that list is:

1.  Disposals
2.  Cargo Bay
3.  QM Office
4.  Engineering
5.  CE Office
6.  Atmospherics
7.  Security
8.  HoS Office
9.  Medbay
10. CMO Office
11. Chemistry
12. Research
13. RD Office
14. Robotics
15. HoP Office
16. Library
17. Chapel
18. Theater (UNUSED)
19. Bar
20. Kitchen
21. Hydroponics
22. Janitor
23. Genetics

#### Last steps

Click out your pipes and when you get to where the disposal unit goes
place it with /obj/machinery/disposal and a pipe leading up to it on the
same tile that is /obj/structure/disposalpipe/trunk

and you are done!

Power
-----

### APC

Each new room needs at least one, this will provide all the power for
the room (magically). Any room that is very equipment heavy may need
another APC to split the load and prevent early black outs.

### Wiring

Make sure the wires lead from the main power grid, and to the APC(s) of
your area. If any equipment in your new area requires a wire under it,
line it up, connected to the main power grid, and under the machinery.
Wires are also helpful when making electrical grills (just dot wire
under a grill), make sure the wires touch the main power grid (or they
won't shock people).

Equipment
---------

### Lights

Lights take up a lot of power, don't use too many! Make sure to put in
just enough so the room is fully lit, but not so many that the equipment
will go out in ten minutes of the round starting.

### Light switch

For mood lighting, or to show the room is currently not in use by the
primary occupant. These disable the lighting equipment (and power drain
associated) in the area, but not desk lamps. Place these on walls,
usually by a door.

### Request Console

If a certain room has no need for materials, or produces no materials,
do not give it a Request Console. If it does (for either case or both)
make sure it has at least one, that is in a place where some one will
see it.

### Intercoms

At least every room should have one of these. They should be set to
145.9, and be speaker ON Microphone OFF. This is so radio signals can
reach people even without head sets on. Larger room will require more
than one at a time.

### Security Cameras

Most areas should have these, enough to see the general area from a
Human point of view, but, not bunched together for the AI's sake. Larger
rooms may require more than one.

Room Structure
--------------

### Access

Here are the various door access.

access\_security = 1

access\_brig = 2

access\_armory = 3

access\_forensics\_lockers= 4

access\_medical = 5

access\_morgue = 6

access\_tox = 7

access\_tox\_storage = 8

access\_genetics = 9

access\_engine = 10

access\_engine\_equip= 11

access\_maint\_tunnels = 12

access\_external\_airlocks = 13

access\_emergency\_storage = 14

access\_change\_ids = 15

access\_ai\_upload = 16

access\_teleporter = 17

access\_eva = 18

access\_heads = 19

access\_captain = 20

access\_all\_personal\_lockers = 21

access\_chapel\_office = 22

access\_tech\_storage = 23

access\_atmospherics = 24

access\_bar = 25

access\_janitor = 26

access\_crematorium = 27

access\_kitchen = 28

access\_robotics = 29

access\_rd = 30

access\_cargo = 31

access\_construction = 32

access\_chemistry = 33

access\_cargo\_bot = 34

access\_hydroponics = 35

access\_manufacturing = 36

access\_library = 37

access\_lawyer = 38

access\_virology = 39

access\_cmo = 40

access\_qm = 41

access\_court = 42

access\_clown = 43

access\_mime = 44

access\_surgery = 45

access\_theatre = 46

access\_research = 47

access\_mining = 48

access\_mining\_office = 49 - not in use

access\_mailsorting = 50

access\_mint = 51

access\_mint\_vault = 52

access\_heads\_vault = 53

access\_mining\_station = 54

access\_xenobiology = 55

access\_ce = 56

access\_hop = 57

access\_hos = 58

access\_RC\_announce = 59 - Request console announcements

access\_keycard\_auth = 60 - Used for events which require at least two
people to confirm them

access\_tcomsat = 61 - has access to the entire telecomms satellite /
machinery

### CentCom Access

Mostly for admin use.

access\_cent\_general = 101 - General facilities.

access\_cent\_thunder = 102 - Thunderdome.

access\_cent\_specops = 103 - Special Ops.

access\_cent\_medical = 104 - Medical/Research

access\_cent\_living = 105 - Living quarters.

access\_cent\_storage = 106 - Generic storage areas.

access\_cent\_teleporter = 107 - Teleporter.

access\_cent\_creed = 108 - Creed's office.

access\_cent\_captain = 109 - Captain's office/ID comp/AI.

### Misc Access

access\_syndicate = 150 - General Syndicate Access

access\_crate\_cash = 200 - Money Crates?

### Airless Floors

Ideal for rooms or chambers that mix gas, and for tiles exposed to
space. Not ideal for areas that humans will cross in frequency.

Use these on external tiles (to prevent lag when the game starts) and
chambers that will require gas mixing (toxins mix chamber/ furnace).
Double check these to make sure you don't suffocate mobs in the new
rooms.

### Fire Alarms and Fire Doors

Make sure to put these INSIDE of the boundary of the area, so there is a
lock down. Any spot that gets hot as a normal function should not have a
fire Alarm right next to the heat source (toxin mix chamber). Make sure
there is a fully sealed area (with the exception of maintenance doors
for people to escape fires) that can't be open by normal civilians.

### Weak Points

Judge how high security the room will be, if it is high security,
reinforced walls and electrified grill windows may be in order. Areas
that do not need a lot of security can use basic walls, and windows to
your liking (though normal glass windows break very very easy). Each
room should have one place that's weaker than the rest (like a back
door, side entrance, or a window), just because the main entrance might
be out of commission (and realistically, for traitors to break into).

### Item and Machinery Distribution

Be smart about what will go in an area, keep a fine balance between the
size of the room and amount of equipment. Large rooms may require
multiple APCs to prevent power outages early in game. Second, make sure
to place equipment that make sense for the area (security computer in a
security area/ Medical vendor in a medical area).

Balance
-------

### Item contents

The harder the room is to enter, the more goodies or sensitive equipment
there is inside. Make sure to keep this in mind (and don't make an empty
room that's covered in blast doors, electrified grills, reinforced
walls, and captain level doors).

### Room security

A room is only as secure as its necessity. Public rooms should not have
many security functions (other than a fire alarm), but private work
space must be more secure (based on job). The bartenders do not need
reinforced walls around their storage, but engineers do.

The highest security rooms should utilize the highest security measures.
The lowest security rooms should utilize the cheapest security measures.

Step\_x, step\_y and the broken movement syndrome
-------------------------------------------------

So you compiled the map and suddenly whenever you move you no longer get
the animation of moving but just 'appear' on the next tile?

So a while back step\_x and step\_y were introduced to allow pixel based
movement. SS13 does not utilize this. Step\_x and step\_y are variables
that each atom has. The way they work is that as soon as you set any
object on the map to use one of these variables, the game interprets
that you overrode all default movement code and wrote your own - but you
didn't (The code that makes the animation from tile to tile).

To fix this problem you need to close dream maker (save the project
first, obviously). Open your map (.dmm) file in a text editor, such as
notepad or notepad++. Search (ctrl+f) through the file for step\_x and
step\_y and remove any reference to it. Once no more step\_x or step\_y
-es are found in the file, save it and open it in dream maker once
again. Compile the code and movement should work fine once more. Go to
[the development IRC](/wiki/Community "wikilink") if you need more help.

[Category:Game Resources](/wiki/Category:Game_Resources "wikilink")
