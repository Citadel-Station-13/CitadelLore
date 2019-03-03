---
title: Basics of Coding in BYOND
permalink: wiki/Basics_of_Coding_in_BYOND/
layout: wiki
tags:
 - Game Resources
---

**NOTE!!** This guide uses terms very loosely. Experienced coders,
please don't get at me over what an object is and what a method and so
forth. This guide is intended **solely for the new coder.** If you're
experienced with programming in general, you might want to check out
[SS13 for Experienced
Programmers](/wiki/SS13_for_Experienced_Programmers "wikilink").

DreamMaker
----------

The program you will need for both coding and mapping is made out of six
major components. The file tree, the object tree, the text editor, the
icons editor, the map editor and the error report panel.

### File tree

The file tree can be accessed by choosing the 'File' tab in the
left-hand vertical panel. It shows the files which make up the code as
they are sorted by folders. Double clicking any file will open it in
it's respective editor. If you add a new file to the list (in windows
explorer) hit the refresh button to refresh the list. The ticks next to
files indicate if they're used in the compiling of the code. A common
mistake is to forget to include a new file.

### Objects tree

What an object is is explained [further
down](#What_is_an_object? "wikilink") in this guide, but for now we can
say it contains a list of things, which you can place on the map. They
are arranged in a hierarchy. This is also explained and described
further down in the guide. The update button at the bottom will update
the tree with new sprites and objects, if they have been added in any of
the ticked .dm files.

### Text editor

This editor is accessed whenever you open a file with the extension
".dm". It is intended for the writing and editing of the game code.

### Icons editor

Intended for the editing of icon states and icons, it is accessed when
you open a ".dmi" file. It displays a list of all the sprites (often
called icon states) which are in the file. Rightclicking anywhere will
yield the options to create a new movie or pixmap. A pixmap is a static
image, while a movie is either an icon state which can point in several
different directions (often called dirs) or is animated. The movie can
have either 1 (south), 4 (NSEW) or 8 directions (full compass). Also
note that a .dmi file may only have icons of a certain size. In the case
of the singularity, which grows as it gains power, several .dmi files
are needed.

### Map editor

Usually opened at startup or when opening a ".dmm" map file, the map
editor displays the map. By default it displays all 4 major groups:
area, mob, object and turf. To choose the specifics of what to display,
hit the layers tab in the top-most toolbar and select 'Only show
selectable layers' and then choose which layers you want to be shown in
the same (layers) tab. (Most commonly used to hide the areas overlay).
Note that the map will not display if there are any errors in the .dm
code. Correct any errors and then recompile it.

### Error report panel

A text-based panel at the bottom of DreamMaker, the error report panel
is intended to provide compiling error reports.

### Compile and run

To compile updated code without running it, select the 'build' tab in
the uppermost toolbar and shoose 'compile'. To compile and run hit the
'run' button in the same tab.

Code components
---------------

### Variables

[reference](http://www.byond.com/members/?command=reference&path=var)

Variables are intended to store data. Variables are created like this:
(creates variable with no defined value) var/i

To define a value in declaration do this:

` var/i = 5`

or

` var/i = "Hello World"`

Once a variable has been defined, you cannot define another one with the
same name:

` var/i`  
` i = 2`  
` i = 6`  
` i = 12`

#### List

[reference](http://www.byond.com/members/?command=reference&path=list)

A list can be defined as either of the three, but special variables
associated with lists (such as len for length) will only be available if
you use the first declaration.

` var/list/a`  
` var/a[9]`  
` var/a = list()`

#### Other types

If you wish to store a coin in somewhere in the variables of an object
and use the coin's defined procs or variables, you'll have to define the
variable in which you store the coin as a coin. The second example also
creates a variable called D and fills it with a new coin.

` var/obj/item/weapon/coin/C`  
` var/obj/item/weapon/coin/D = new/var/obj/item/weapon/coin(src)`

#### Included variables

Variables which are built into byond itself and are not defined anywhere
in code:  
[Atom
vars](http://www.byond.com/members/?command=reference&path=atom%2Fvar)  
[Client
vars](http://www.byond.com/members/?command=reference&path=client%2Fvar)  
[Datum
vars](http://www.byond.com/members/?command=reference&path=datum%2Fvar)  
[Mob
vars](http://www.byond.com/members/?command=reference&path=mob%2Fvar)

##### Direction (dir) var

[reference](http://www.byond.com/members/?command=reference&path=atom%2Fvar%2Fdir)

**North:** 1  
**South:** 2  
**East:** 4  
**West:** 8  
**Northeast:** 5 (1 + 4)  
**Southeast:** 6 (2 + 4)  
**Northwest:** 9 (1 + 8)  
**Southwest:** 10 (2 + 8)  
They are numbered like this because dir uses the 'bitflag' methodology.
It is defined in binary, so...

**0001** is north  
**0010** is south  
**0100** is east  
**1000** is west

Combining these numbers yields north-east (0101), north-west (1001),
south-east (0110) and south-west (1010). Tho other combinations
(east-west(1100), north-south (0011), north-east-west (1101) and such)
are possible for special uses. Smoothwall code is an example.

##### Atom vars

These apply to all /obj, /turf, /area, /mob -type objects.

'''[Contents](http://www.byond.com/members/?command=reference&path=atom%2Fvar%2Fcontents):
**List of objects which are inserted into another object. (plasma tanks
in radiation arrays, ore in the smelter, etc.)  
**[Density](http://www.byond.com/members/?command=reference&path=atom%2Fvar%2Fdensity):
**0/1 - 0 means your mob can pass through (or over), 1 means you
cannot  
**[Desc](http://www.byond.com/members/?command=reference&path=atom%2Fvar%2Fdesc):
**string - Description, displayed upon examine  
**[Dir](http://www.byond.com/members/?command=reference&path=atom%2Fvar%2Fdir):
**1-10 - the direction the object is facing  
**[Icon](http://www.byond.com/members/?command=reference&path=atom%2Fvar%2Ficon):
**The .dmi file which contains the sprite for the icon  
**[Icon\_state](http://www.byond.com/members/?command=reference&path=atom%2Fvar%2Ficon_state):
**The name of the sprite in the file from Icon  
**[Overlays](http://www.byond.com/members/?command=reference&path=atom%2Fvar%2Foverlays):
**A list of images which are overlayed on the item.  
**[Layer](http://www.byond.com/members/?command=reference&path=atom%2Fvar%2Flayer):
**If two objects are on the same tile and one has a higher layer number
than the other, the one with the higher will be shown as above the one
with the lower  
**[Loc](http://www.byond.com/members/?command=reference&path=atom%2Fvar%2Floc):
**The X,Y,Z positioning of an item  
**[Luminosity](http://www.byond.com/members/?command=reference&path=atom%2Fvar%2Fluminosity):
**How much does it glow?  
**[Name](http://www.byond.com/members/?command=reference&path=atom%2Fvar%2Fname):
**The name, displayed when you hover your mouse over the item  
**[Opacity](http://www.byond.com/members/?command=reference&path=atom%2Fvar%2Fopacity):
**Can you see through it?  
**[Pixel\_x](http://www.byond.com/members/?command=reference&path=atom%2Fvar%2Fpixel_x),
[pixel\_y](http://www.byond.com/members/?command=reference&path=atom%2Fvar%2Fpixel_y):
**Set if the item on the map is nudged a few pixels to either side. Used
with APC's, Request Consoles, Fire alarms, etc.  
**[Type](http://www.byond.com/members/?command=reference&path=datum%2Fvar%2Ftype):
'''Type is the path of the object. A coin would have it's type variable
set to: /obj/item/weapon/coin

### Included instructions

Reference guides for included instructions (proc-s) can be found at the
following links:  
[Area
procs](http://www.byond.com/members/?command=reference&path=area%2Fproc)  
[Mob
procs](http://www.byond.com/members/?command=reference&path=mob%2Fproc)  
[Obj
procs](http://www.byond.com/members/?command=reference&path=obj%2Fproc)  
[Turf
procs](http://www.byond.com/members/?command=reference&path=obj%2Fproc)

### Conditionals

Conditionals are statements which determine how the code will be
executed, depending on a condition. The most common conditional is the
IF statement

==== = vs. == ====

` var/a`  
` a = 14`  
` if (a == 14)`  
`   world << "A has the value [a]"`  
` else`  
`   world << "A is not 14"`

As in the example above, the single = means you assign the value on the
right to the variable on the left. In the example above, the variable a
was assigned the value 14 (a = 14)

The double == is used to compare two values. It's most commonly used in
the if statement. In the example above you can see we compared the
variable a to 14 (a == 14). This determines how the if will react.

#### If statement

[reference](http://www.byond.com/members/?command=reference&path=proc%2Fif)

The example shows a simple if statement. If statements work by first
checking if the statement in the brackets, in the case above a == 14, is
true or not. If it's true, it will proceed to execute the code, which is
further indented from the if (in the case above: world &lt;&lt; "A has
the value \[a\]"). In the other case, if the statement is not true, it
will jump to the else statement and execute the code, which is indented
from that. It will only jump to the else statement if one is present. In
the example, if a was not 14, it would execute world &lt;&lt; "A is not
14"

Comparison operators include:  
**==** Equals  
**!=** Not Equals  
**&lt;** Less than  
**&gt;** More than  
**&lt;=** Less or equal  
**&gt;=** More or equal

#### Switch-case statement

[reference](http://www.byond.com/members/?command=reference&path=proc%2Fswitch)

### Loops

#### While

[reference](http://www.byond.com/members/?command=reference&path=proc%2Fwhile)

#### For

[reference](http://www.byond.com/members/?command=reference&path=proc%2Ffor%2Floop)

#### For (foreach)

[reference](http://www.byond.com/members/?command=reference&path=proc%2Ffor%2Flist)

### Procs

[reference](http://www.byond.com/members/?command=reference&path=proc)

What is an object?
------------------

SS13 is coded in Byond, which is an object oriented programming
language. Please note that by object here i do not mean an item or
machine in-game. For this intro alone i will speak of objects as I'll
define them here.

An object can be any defined path in the game. Examples include:

` /obj/item/weapon/sword`  
` /turf/simulated/floor`  
` /area/`  
` /atom/`

An object is made out of both [variables](#Variables "wikilink") and
[procs](#Procs "wikilink")

Here's an example of an object:

` /turf/simulated/gold_spot`  
`   var/spawned_gold = 0`  
`   name = "Gold Area"`  
`   desc = "This plot may have spawned gold!"`  
` `  
` /turf/simulated/gold_spot/proc/spawn_gold()`  
`   if(prob(50))`  
`     new/obj/item/stack/sheet/gold(src)`  
`     spawned_gold = 1`  
` `  
` /turf/simulated/gold_spot/New()`  
`   ..()`  
`   spawn_gold()`

### Hierarchy and Inheritance

Objects inherit all it's parent's variables and procs. This means that
an object defined as /obj/item/weapon/storage/box has all the variables
of /obj/item/weapon/storage, /obj/item/weapon, /obj/item, /obj and also
/atom, but we'll get to that one later. Some procs are already defined
for all objects, you can see these
[here](http://www.byond.com/members/?command=reference&path=atom%2Fproc).
In the above example, New() was an instance of a proc which was
inherited from the parent object. This is why New() does not have the
proc/ prefix, because it is already defined in the parent object. You
should however know that New() was redefined here, so it no longer acts
the same way as in the parent objects.

An example of an inherited variable are the name and desc (description)
variables. Both were redefined tho. spawned\_gold, however, is a new
variable. One which the parent proc does not have.

If we define the following two objects...

` /turf/simulated/gold_spot/plot1`  
` /turf/simulated/gold_spot/plot2`

...we just defined two child objects of /turf/simulated/gold\_spot and
they inherited all the procs and vars that /turf/simulated/gold\_spot
has including all those which /turf/simulated/gold\_spot inherited from
their parent (/turf/simulated).

### ..()

` ..()`

is something you will often see in the code. In other languages this is
usually called super(), it calls the parent object's proc with the same
name. Unlike some languages it is not automatically executed even if not
added, nor is it required to be at the proc's start. These are usually
added in New(), Del() and Attackby() procs to get to the original
definition in the common parent. These common definitions usually ensure
things are properly handled.

Area, Mob, Obj and Turf organization
------------------------------------

` /datum`  
`   /atom`  
`     /area --All objects in here are areas, which are used in mapping to define the extent of an APC's power coverage, lighting, atmos, etc.`  
`     /mob`  
`       /dead --ghosts`  
`       /living`  
`         /carbon --humans and monkeys`  
`         /silicon --AI and cyborgs`  
`     /obj`  
`       /effect --Landmarks, trigger objects, effects and decals`  
`       /item`  
`         /clothing --most of the clothing you can wear, belts and backpacks are in obj/item/weapon/storage`  
`         /devices --electronic devices`  
`         /stack --the things which you can stack, such as rods, floor tiles and materials`  
`         /weapons --most items which you can pick up`  
`       /machinery --machines which use power, process every tick and are generally unmovable`  
`       /structure --objects which don't require processing every tick or power, examples include windows, grilles, bookcases etc.`  
`     /turf`  
`       /simulated`  
`         /floor --floors with air`  
`           /airless --floors without air (ALWAYS use these for areas exposed to space)`  
`           /plating --plating`  
`             /airless --airless plating`  
`         /wall --walls`  
`           /r-wall --reinforced walls`  
`       /space --it's space`  
`       /unsimulated --everything used on centcom and places where air movement is not simulated.`

[Category:Guides](/wiki/Category:Guides "wikilink")
