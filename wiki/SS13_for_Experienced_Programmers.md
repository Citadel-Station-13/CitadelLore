---
title: SS13 for Experienced Programmers
permalink: wiki/SS13_for_Experienced_Programmers/
layout: wiki
tags:
 - Guides
---

Other related guides: [Basics of Coding in
BYOND](/wiki/Basics_of_Coding_in_BYOND "wikilink") and the [Guide to
Mapping](/wiki/Guide_to_Mapping "wikilink")

So you know how to write programs in other languages and would like a
quick guide on how to understand and code for SS13? Good, this is the
guide for you. It likely doesn't contain everything that you need to
know but it's a start.

Syntax
------

-   Semicolons at the end are not mandatory,
-   Loop, proc, object, variable etc. spans are determined by
    indentations (similar to Python, see examples below)

` /obj`  
`   var`  
`     i1`  
`     i2`  
`     i3`

is the same as (Strongly recommended you use this layout to make
searching for variable and proc definitions easier.)

` /obj`  
`   var/i1`  
`   var/i2`  
`   var/i3`

which is inturn the same as

` /obj/var/i1`  
` /obj/var/i2`  
` /obj/var/i3`

-   This guide uses the word 'object' for any defined type (see
    [Variable types](#Variable_types "wikilink")) and the word 'obj' for
    derivatives of atom/obj, which are all objects which can be placed
    on the map.
-   This guide uses the word 'AI controlled' for behavior to do with an
    [AI](/wiki/AI "wikilink") player controlling an item. The term 'Game
    controlled' is used when refering to behavior which the script
    itself determins (Usually called AI controlled creatures or NPCs)
-   All things are inherited from parent objects. If a variable is
    defined in /obj/item, it doesn't need to be (actually can't be)
    redefined in /obj/item/weapon.

### [Variables](http://www.byond.com/members/?command=reference&path=var)

Variables are very general, Byond makes no difference in the declaration
of strings, integers, etc. (Similar to PHP)

#### [Predefined variables](http://www.byond.com/members/?command=reference&path=var)

There is a lot of predefined variables for objects in BYOND, but the
most important are:

-   **[src](http://www.byond.com/members/?command=reference&path=proc%2Fvar%2Fsrc)** -
    a variable equal to the object containing the proc or verb. It is
    defined to have the same type as that object. (Similar to "this" in
    Java or C++)
-   **[usr](http://www.byond.com/members/?command=reference&path=proc%2Fvar%2Fusr)** -
    a mob variable (var/mob/usr) containing the mob of the player who
    executed the current verb, or whose action ultimately called the
    current proc. **A good rule of thumb is to never put usr in a
    proc.** If src would not be the correct choice, it is better to send
    another argument to your proc with the information it needs.
-   **[args](http://www.byond.com/members/?command=reference&path=proc%2Fvar%2Fargs)** -
    a list of the arguments passed to the proc or verb.
-   **[vars](http://www.byond.com/members/?command=reference&path=datum%2Fvar%2Fvars)** -
    a list of object variables. If the variable name is used as an index
    into the list, the value of that variable is accessed.

For more SS13 specific variables see [SS13 common variable
meanings](#SS13_common_variable_meanings "wikilink")

#### Variable definition

##### Basic definitions

` var/j`  
` var/i = 4`  
` var/a, b, c`

##### Complex definitions

The general syntax is [var/type/variable\_name =
value](http://www.byond.com/members/?command=reference&path=var)

Examples:

` var/obj/item/I = new/obj/item`  
` `[`I.name`](http://www.byond.com/members/?command=reference&path=operator%2F%40dt%3B)` = "Some item"`

Datum definition and declaration of a variable of that datum type:

` datum/test_datum`  
`   var/test_variable = 0 //declaration of the test_variable var`  
`   `  
`   proc/set_as(var/i) //proc definition within the test_datum datum`  
`     test_variable = i //set the test_variable var to the value in the argument`  
` `  
` var/datum/test_datum/TD = new/datum/test_datum //TD will now be a reference to a datum of type test_datum`  
` TD.test_variable = 4  //Byond doesn't know of private variables, so you can set any variables like this`  
` `[`world`](http://www.byond.com/members/?command=reference&path=world)` `[`<<`](http://www.byond.com/members/?command=reference&path=operator%2F%26lt%3B%26lt%3B)` TD.test_variable //will output 4 to all connected users`  
` TD.set_as(10) //Will call the set_as proc in the datum with the argument 10`  
` TD.test_variable //will output 10 to all connected users`

#### Bitflags

Bitflags are variables which use bits instead of numbers to determine
conditions. The bit operators are
[&](http://www.byond.com/members/?command=reference&path=operator%2F%26)
and
[\|](http://www.byond.com/members/?command=reference&path=operator%2F%7C).
For now, you should know that bitflag operators use the binary value of
numbers to determine the result. So [13 &
3](http://www.byond.com/members/?command=reference&path=operator%2F%26)
will result in 1. ([1101 & 0011 =
0001](http://www.byond.com/members/?command=reference&path=operator%2F%26))
and [13 \| 3 =
15](http://www.byond.com/members/?command=reference&path=operator%2F%7C)
([1101 \| 0011 =
1111](http://www.byond.com/members/?command=reference&path=operator%2F%7C))
see [if](#If "wikilink") for uses

#### Variable types

[reference](http://www.byond.com/members/?command=reference&path=var)

-   [datum](http://www.byond.com/members/?command=reference&path=datum) -
    ordinary object type (class in java)
-   [atom](http://www.byond.com/members/?command=reference&path=atom) -
    atom derives into obj, turf, mob and area
-   [turf](http://www.byond.com/members/?command=reference&path=turf) -
    tiles which make up the floors, walls and space on SS13
-   [area](http://www.byond.com/members/?command=reference&path=area) -
    areas are grouped locations. They combine many turfs and it gives
    some common properties. Power, atmosphere, etc. are determined by
    areas
-   [mob](http://www.byond.com/members/?command=reference&path=mob) - an
    object with life, be it game controlled or player controlled.
-   [obj](http://www.byond.com/members/?command=reference&path=obj) -
    objects which can be placed on the map
-   [client](http://www.byond.com/members/?command=reference&path=client) -
    a new client object is created for each connected player
-   [list](http://www.byond.com/members/?command=reference&path=list) -
    a list of elements. The first element in a list called L is L\[1\]
-   [world](http://www.byond.com/members/?command=reference&path=world) -
    this is a variable where some global variables for the entire world
    can be set. World's contents var contains all atoms currently in the
    game world.

#### [Outputting messages](http://www.byond.com/members/?command=reference&path=operator%2F%26lt%3B%26lt%3B%2Foutput)

The most basic way of outputting messages is with the ['&lt;&lt;' output
operator](http://www.byond.com/members/?command=reference&path=operator%2F%26lt%3B%26lt%3B%2Foutput).

` `[`world`](http://www.byond.com/members/?command=reference&path=world)` `[`<<`](http://www.byond.com/members/?command=reference&path=operator%2F%26lt%3B%26lt%3B)` "Hello World!" //Outputs a message to all clients in the world`  
` `[`usr`](http://www.byond.com/members/?command=reference&path=proc%2Fvar%2Fusr)` `[`<<`](http://www.byond.com/members/?command=reference&path=operator%2F%26lt%3B%26lt%3B)` "Hello usr" //Outputs a message to only the user who is tied to the calling of the proc which contains this.`

##### Output with variables

` var/s1 = "Hello"`  
` var/s2 = "World"`  
` var/i = 2011`  
` `[`world`](http://www.byond.com/members/?command=reference&path=world)` `[`<<`](http://www.byond.com/members/?command=reference&path=operator%2F%26lt%3B%26lt%3B)` "[s1] [s2], this guide was written in [i]" //Returns "Hello World, this guide was written in 2011"`

#### Determining variable types in code

The
[istype()](http://www.byond.com/members/?command=reference&path=proc%2Fistype)
proc will come in handy

Example

` var/obj/item/weapon/W = new/obj/item/weapon/baton`  
` if(`[`istype`](http://www.byond.com/members/?command=reference&path=proc%2Fistype)`(W,/obj/item/weapon/baton))`  
`   `[`world`](http://www.byond.com/members/?command=reference&path=world)` << "It's a baton!"`

The second argument is optional, if it's omitted, the variable will be
checked against its declared type, like

` var/obj/item/weapon/W = new/obj/item/weapon/baton`  
` if(`[`istype`](http://www.byond.com/members/?command=reference&path=proc%2Fistype)`(W))`  
`   `[`world`](http://www.byond.com/members/?command=reference&path=world)` << "It's a weapon!"`

Standard code for getting specific arguments from variables which have a
type that is a subclass of the type the current proc treats them with
(see any attackby() proc for examples). Note that the example below is
of a proc which is globaly defined, not tied to the object. It doesn't
make much sense to do it like this but it works for the purposes of the
example. /obj objects don't have the 'amount' variable, it's defined in
/obj/item/stack (as ilustrated by the oversimplified definition of
classes below. Also note where var/ is used and where it isn't).

` /obj`  
`   var/name = "Object"`  
` `  
` /obj/item`  
`   name = "Item"`  
` `  
` /obj/item/stack`  
`   name = "Stack"`  
`   var/amount = 50`  
` `  
` proc/get_amount(var/obj/O)`  
`   if(`[`istype`](http://www.byond.com/members/?command=reference&path=proc%2Fistype)`(O,/obj/item/stack))`  
`     var/obj/item/stack/S = O`  
`     return `[`S.amount`](http://www.byond.com/members/?command=reference&path=operator%2F%40dt%3B)

There is another way of doing this. I'll show you that it exists but it
is NOT TO BE USED.

` proc/get_aount(var/obj/S)`  
`   if(`[`istype`](http://www.byond.com/members/?command=reference&path=proc%2Fistype)`(O,/obj/item/stack))`  
`     return `[`O:amount`](http://www.byond.com/members/?command=reference&path=operator%2F%3A)

The [colon
operator](http://www.byond.com/members/?command=reference&path=operator%2F%3A)
(:) in the example above tells the byond compiler: "I know what I'm
doing, so ignore the fact the object doesn't have this variable, I'll
make sure it works myself." The problem is that people will revise your
code and use it in ways you never planed for. This means something might
eventually make the O:amount throw exceptions in the form of runtime
errors. Some variables might eventually need to be removed or replaced
and this is impossible when they are used with object:variable as the
compiler will not throw an error when the variable is removed. The error
will only become apparent after the game is ran on the live server which
might cause it to crash. So just don't use this method, ever.

There are some shortcuts to
[istype()](http://www.byond.com/members/?command=reference&path=proc%2Fistype)
proc:  
[isarea(variable)](http://www.byond.com/members/?command=reference&path=proc%2Fisarea)
= istype(variable, /area)  
[isicon(variable)](http://www.byond.com/members/?command=reference&path=proc%2Fisicon)
= istype(variable, /icon)  
[ismob(variable)](http://www.byond.com/members/?command=reference&path=proc%2Fismob)
= istype(variable, /mob)  
[isobj(variable)](http://www.byond.com/members/?command=reference&path=proc%2Fisobj)
= istype(variable, /obj)  
[isturf(variable)](http://www.byond.com/members/?command=reference&path=proc%2Fisturf)
= istype(variable, /turf)  
[isloc(variable)](http://www.byond.com/members/?command=reference&path=proc%2Fisloc)
= ismob(variable) \|\| isobj(variable) \|\| isturf(variable) \|\|
isarea(variable)

#### Switching between variable types in code

Byond defined:  
[ascii2text](http://www.byond.com/members/?command=reference&path=proc%2Fascii2text)  
[file2text](http://www.byond.com/members/?command=reference&path=proc%2Ffile2text)  
[list2params](http://www.byond.com/members/?command=reference&path=proc%2Flist2params)  
[num2text](http://www.byond.com/members/?command=reference&path=proc%2Fnum2text)  
[params2list](http://www.byond.com/members/?command=reference&path=proc%2Fparams2list)  
[text2ascii](http://www.byond.com/members/?command=reference&path=proc%2Ftext2ascii)  
[text2file](http://www.byond.com/members/?command=reference&path=proc%2Ftext2file)  
[text2num](http://www.byond.com/members/?command=reference&path=proc%2Ftext2num)  
[text2path](http://www.byond.com/members/?command=reference&path=proc%2Ftext2path)  
[time2text](http://www.byond.com/members/?command=reference&path=proc%2Ftime2text)  
SS13 Defined:  
text2dir(direction)  
dir2text(direction)  
dd\_file2list(file\_path, separator)  
dd\_text2list(text, separator, var/list/withinList)  
dd\_text2List(text, separator, var/list/withinList)  
dd\_list2text(var/list/the\_list, separator)  
angle2dir(var/degree)  
angle2text(var/degree)  
For more useful procs see  
[code/defines/procs/helpers.dm](http://code.google.com/p/tgstation13/source/browse/trunk/code/defines/procs/helpers.dm)  
[code/game/objects/items/helper\_procs.dm](http://code.google.com/p/tgstation13/source/browse/trunk/code/game/objects/items/helper_procs.dm)

### [If](http://www.byond.com/members/?command=reference&path=proc%2Fif)

Ifs default to checking for true if not otherwise stated. True is
defined for all variable types as empty, 0 or non-existant (null).

` if(condition)`  
`   action_true()`  
` else`  
`   action_false()`

#### Common variable behavior in if statements:

| Variable type         | False when | True when     |
|-----------------------|------------|---------------|
| String (text / ascii) | "" or null | Anything else |
| Int / Real            | 0 or null  | Anything else |
| datum, atom           | null       | Anything else |

#### [Logical operators](http://www.byond.com/members/?command=reference&path=operator)

Pretty standard:

` `[`!statement1`](http://www.byond.com/members/?command=reference&path=operator%2F%21)` //NOT statement1`  
` `[`(statement1)`` ``&&`` ``(statement2)`](http://www.byond.com/members/?command=reference&path=operator%2F%26%26)` //statement1 AND statement2`  
` `[`(statement1)`` ``||`` ``(statement2)`](http://www.byond.com/members/?command=reference&path=operator%2F%7C%7C)` //statement1 OR statement2`  
` `[`==`](http://www.byond.com/members/?command=reference&path=operator%2F%3D%3D)` //equals`  
` `[`!=`](http://www.byond.com/members/?command=reference&path=operator%2F%21%3D)` //not equal`  
` `[`<`](http://www.byond.com/members/?command=reference&path=operator%2F%26lt%3B)` (`[`<=`](http://www.byond.com/members/?command=reference&path=operator%2F%26lt%3B%3D)`) //less (or equal)`  
` `[`>`](http://www.byond.com/members/?command=reference&path=operator%2F%26gt%3B)` (`[`>=`](http://www.byond.com/members/?command=reference&path=operator%2F%26gt%3B%3D)`) //more (or equal)`  
` `[`&`](http://www.byond.com/members/?command=reference&path=operator%2F%26)` //bitflag AND operator. 13 & 3 = 1 (1101 & 0011 = 0001)`  
` `[`|`](http://www.byond.com/members/?command=reference&path=operator%2F%7C)` //bitflag OR operator. 13 | 3 = 15 (1101 | 0011 = 1111)`

Byond does not recognize the === (identical) operator. More operators
can be found in the left menu on the [reference
page](http://www.byond.com/members/?command=reference&path=operator)

### [While](http://www.byond.com/members/?command=reference&path=proc%2Fwhile)

Byond will cancel a loop if it reaches a certain number of iteration and
give a runtime error out of fear of infinite loops. Same applies for
recursions. Same as anywhere else

` while(condition)`  
`   action1()`

All loops understand the
[continue](http://www.byond.com/members/?command=reference&path=proc%2Fcontinue)
and
[break](http://www.byond.com/members/?command=reference&path=proc%2Fbreak)
commands

### For

All loops understand the
[continue](http://www.byond.com/members/?command=reference&path=proc%2Fcontinue)
and
[break](http://www.byond.com/members/?command=reference&path=proc%2Fbreak)
commands

For combines the for loop and foreach loop:

#### [For loop](http://www.byond.com/members/?command=reference&path=proc%2Ffor%2Floop)

` for(var/i = 1; i <= 10; i++)`  
`   `[`world`](http://www.byond.com/members/?command=reference&path=world)` << i //Will write (each in a new line) 1 2 3 4 5 6 7 8 9 10`

#### [For each](http://www.byond.com/members/?command=reference&path=proc%2Ffor%2Flist)

` for(var/obj/item/weapon/baton/B `[`in`](http://www.byond.com/members/?command=reference&path=operator%2Fin)` world)  //will iterate through world.contents (which contains all atoms in the world) and only pick those which are of the given type (/obj/item/weapon/baton)`  
`   B.name = "Smelly baton" //Will apply the new name to the baton in the current iteration loop`

### [Do - While](http://www.byond.com/members/?command=reference&path=proc%2Fdo)

The Do while operator is not commonly used in SS13 code, Byond does
support it tho.

` var/i = 3`  
` do`  
`   world << i--`  
` while(i)`

All loops understand the
[continue](http://www.byond.com/members/?command=reference&path=proc%2Fcontinue)
and
[break](http://www.byond.com/members/?command=reference&path=proc%2Fbreak)
commands

### [Defining objects](http://www.byond.com/members/?command=reference&path=datum)

Doesn't matter if you want a
[datum](http://www.byond.com/members/?command=reference&path=datum) or
[atom](http://www.byond.com/members/?command=reference&path=atom), the
definition of objects is the same and simple:

` /obj/item/weapon/item1 //will nmake a new object of type obj.`  
`   var/item_property = 5 //Will define a new variable type for all item1 objs`  
`   name = "Testing Item" //The name var is already defined in parent objects so it is not defined here, but only assigned a new valie.`  
` `  
` /obj/item/weapon/item1/`[`New()`](http://www.byond.com/members/?command=reference&path=datum%2Fproc%2FNew)` //Constructor proc`  
`   `[`..()`](#..() "wikilink")` //should always be present in New() procs, see `[`..()`](#..() "wikilink")` for more information`  
`   item_property = 3 //An action that is performed in the object constructor.`

### [Procs](http://www.byond.com/members/?command=reference&path=proc) (Methods, functions, procedures)

You're used to the standards of methods, functions and procedures,
right? Well procs ignore some aspects of these. They can best be
compared to Java methods, as they're tied to specific objects. They
cannot be defined as static, private, public, etc. tho. You can write
static methods, however the compiler will not restrict you from calling
them in a non-static way or environment. Same applies for non-static
methods.

` proc/proc_name(var/argument1, var/argument2)`  
`   `[`world`](http://www.byond.com/members/?command=reference&path=world)` << "[argument1] [argument2]"`

The above would declare a global proc. If you wish to tie it to a
certain level

#### ..()

This is the same as super() in Java. It calls the parent object type's
proc with the same name and same arguments.

Example:

` /obj/item`  
`   name = "Item"`  
` `  
` /obj/item/New() //New() is the proc that gets called whenever a new object of this type is created. A constructor if you will.`  
`   src.name = "It's an item!"`  
` `  
` /obj/item/stack`  
`   name = "Stack"`  
` `  
` /obj/item/stack/New() `  
`   src.name = "It's a stack!"`  
`   ..()`

If you have the code from the example above and create a new object of
type /obj/item/stack, it will first make the item in the game world with
the name "Stack", because it's defined to be that by default. Then the
New() proc will be called immedietally after. This will change the name
to "It's a Stack!" but the call of the parent type's New() proc with the
..() command will then set it to "It's an item!". So in the end, the new
object will be called "It's an item!". The ..() command is however very
important in many cases as some things are defined only in the common
parent's New() procs. In Del(), the proc which gets called prior to an
object's deletion, it requires the code to get to the root Del() proc to
even delete it. See examples of Del() in the code.

Important procs
---------------

### [New()](http://www.byond.com/members/?command=reference&path=atom%2Fproc%2FNew)

This proc is called whenever a new instance of the object is created. It
can have arguments if needed. It should call ..() where applicable so
that parent constructors can be applied.

If you wish to create a New() proc for
[atoms](#Variable_types "wikilink") with custom arguments, ensure the
first argument is for the object's location. Example:

` obj/item/weapon/my_item/New(var/location, var/i)`  
`   ..()`  
`   //Whatever else you need to do`

To make a general object use

` `[`new`](http://www.byond.com/members/?command=reference&path=proc%2Fnew)` /datum/test_datum`

To make an atom (which usually has a locaiton)

` `[`new`](http://www.byond.com/members/?command=reference&path=proc%2Fnew)` /obj/item/weapon(src.loc)`

For the custom example above, the code to create a new such object would
be: The 5 is just an example of a value which could be assigned to the
var/i in the constructor.

` `[`new`](http://www.byond.com/members/?command=reference&path=proc%2Fnew)` /obj/item/weapon/my_item(src.loc, 5)`

Where src is the proc owner, which contains the line above. src.loc is
the locaiton of the src object.

### [Del()](http://www.byond.com/members/?command=reference&path=datum%2Fproc%2FDel)

This proc gets called before an object's delection. It MUST call ..() at
the end as the actual deletion is done in the root Del() proc.

An object is deleted by using the del(O) proc with O being the object to
be deleted.

### attack\_hand(mob/M as mob)

Whenever a user (M) clicks on the object with an empty active hand

### attack\_paw(mob/M as mob)

Whenever a monkey (M) clicks the object with an empty active hand

If a custom attack\_paw(mob/user) proc is not written for an atom, it
defaults to calling attack\_hand(user)

### attack\_ai(mob/user)

Whenever an AI or cyborg clicks the object with an empty active hand

If a custom attack\_ai(mob/user) proc is not written for an atom, it
defaults to calling attack\_hand(user)

### attack(mob/M as mob, mob/user as mob)

When the object is used to attack mob M by mob user

### attackby(obj/item/W, mob/user)

When the object is being attacked by user with W (Example: If you click
on wires with wirecutters)

### ex\_act(severity)

How the item reacts to explosions. Severity can either be 1, 2 or 3 with
1 being the most destructive.

### blob\_act()

How the item reacts to a blob (magma) attack

### emp\_act(severity)

How the item reacts to an EMP. Severity can either be 1 or 2 with 1
being the more powerful EMP surge.

### [Topic(href, href\_list)](http://www.byond.com/members/?command=reference&path=datum%2Fproc%2FTopic)

This one's called when you click a link in a pop-up window. Like when
you increase the output of [SMES cells](/wiki/SMES_cells "wikilink"). The
href\_list variable is the important one as it's a parsed version of the
arguments you add into a link. To make a link in the pop-up window, add
the following line to the text you display (dat in the example):

` dat += `[`text`](http://www.byond.com/members/?command=reference&path=proc%2Ftext)`("<A href='?src=\ref[src];select=[i]'>[src.name]</a><br>")`

Check the code for more examples of this.

### process()

This gets called for all objects on every tick. If possible, avoid it as
it's processor heavy, but for some things it just can't be avoided.

SS13 common variable meanings
-----------------------------

### Datum

Datums have the smallest number of pre-defined variables. These are
present in all objects in the game:

` type //The type of an object. If your object is of type /obj/item/weapon/shovel writing the following: new src.type(src.loc) will make another shovel in the same tile.`  
` parent_type //Parent type of /obj/item/weapon/shovel is /obj/item/weapon... seems streight-foward enough.`  
` tag //The tag is used to help you identify things when using several instances. It has to be set manually for each instance tho. Lazy coders and mappers resulted in not many tags being used. Instances in the map editor are sorted by tag.`  
` vars //List of object vars the datum has defined`

### Atom

These variables are shared by all areas, mobs, objs and turfs.

` contents //List of contents. Closets store their contents in this var as do all storage items. All the items on a turf are in the turf's contents var.`  
` density //If density is at 0, you can walk over the object, if it's set to 1, you can't.`  
` desc //Description. When you right-click and examine an object, this will show under the name.`  
` dir //Object direction. Sprites have a direction variable which can have 8 'legal' states. `[`More`` ``info`](/wiki/Understanding_SS13_code#Direction_(dir)_var "wikilink")  
` gender //not used`  
` icon //The dmi file where the sprite is saved. Must be written in single quotations (Example: 'items.dmi')`  
` icon_state //The name of the sprite in the dmi file. If it's not a valid name or is left blank, the sprite without a name in the dmi file will be used. If such a sprite doesn't exist it will default to being blank.`  
` invisibility //Invisibility is used to determine what you can and what you can't see. Check the code or wait for someone who knows how exactly this works to write it here.`  
` infra_luminosity //Only mecha use this`  
` underlays //List of images (see image() proc) which are underlayed under the current sprite`  
` overlays //List of images (see image() proc) which are overlayed over the current sprite`  
` loc //Contains a reference to the turf file where the object currently is.`  
` layer //A numerical variable which determins how objects are layered. Tables with a layer of 2.8 are always under most items which have a layer of 3.0. Layers go up to 20, which is reserved for HUD items.`  
` luminosity //How much the item will glow. Note that the picking up and dropping of luminous items needs to be specially handled. See flashlight code for an example.`  
` mouse_over_pointer //not used`  
` mouse_drag_pointer //(almost) not used`  
` mouse_drop_pointer //not used`  
` mouse_drop_zone //not used`  
` mouse_opacity //Used in a few places. Check the description in the reference page`  
` name //The name of the object which is displayed when you right click the object and in the bottom left of the screen when you hover your mouse over it.`  
` opacity //Whether you can see through/past it (glass, floor) when set to 0 or whether you can't (walls, mecha) when set to 1.`  
` pixel_x //How many pixels in the x direction should the sprite be offset from the starting set. See the APC's New() proc for an example and how fire alarms are defined on the map. pixel_x = -5 will move it 5 pixels to the left and pixel_x = 5 will move it 5 pixels to the right`  
` pixel_y //Same as pixel_y but in the y direction. Positive values move it to the north, negative to the south.`  
` pixel_z //Used in isometric maps, so it's not used in SS13`  
` suffix //Rarely used. See the reference page for more information`  
` text //How to represent the object on text clients. Not used.`  
` type //The type of the object`  
` vars //See `[`Datum`](#Datum "wikilink")` above`  
` verbs //The verbs you can use with the item. Verbs are the options in the right click menu.`  
` x //X position, read only. Set the loc variable to move it or use the inbulit functions.`  
` y //Y position, read only. `  
` z //Z position (Which z-level it's on), read only.`

### Area

` var/requires_power = 1 //Areas which are to work without an APC (Such as centcom areas) should have this at 0. All other areas should have it at 1.`  
` var/music = null //Music to be played when you enter the area.`  
` `[`luminosity`](http://www.byond.com/members/?command=reference&path=atom%2Fvar%2Fluminosity)` = 0 //Areas which should be lit at all times (such as space and centcom) should have this at 1 as well as the sd_lighting var at 0`  
` var/sd_lighting = 0 //This var determines whether dynamic lighting is to be calculated for the area's tiles. Turn this to off only for areas which have the luminosity var set to 1`

Most other variables exist only for technical reasons and should not be
messed with unless done through existing procs, they are defined in:

` `[`code/defines/area/Space`` ``Station`` ``13`` ``areas.dm`](http://code.google.com/p/tgstation13/source/browse/trunk/code/defines/area/Space%20Station%2013%20areas.dm)

### Mob

There is a huge amount of variables for mobs. Take a look at the
following files:

` `[`code/defines/mob/mob.dm`](http://code.google.com/p/tgstation13/source/browse/trunk/code/defines/mob/mob.dm)  
` `[`code/defines/mob/dead/observer.dm`](http://code.google.com/p/tgstation13/source/browse/trunk/code/defines/mob/dead/observer.dm)  
` `[`code/defines/mob/living/living.dm`](http://code.google.com/p/tgstation13/source/browse/trunk/code/defines/mob/living/living.dm)  
` `[`code/defines/mob/living/carbon/carbon.dm`](http://code.google.com/p/tgstation13/source/browse/trunk/code/defines/mob/living/carbon/carbon.dm)  
` `[`code/defines/mob/living/carbon/human.dm`](http://code.google.com/p/tgstation13/source/browse/trunk/code/defines/mob/living/carbon/human.dm)  
` `[`code/defines/mob/living/carbon/monkey.dm`](http://code.google.com/p/tgstation13/source/browse/trunk/code/defines/mob/living/carbon/monkey.dm)  
` `[`code/defines/mob/living/silicon/silicon.dm`](http://code.google.com/p/tgstation13/source/browse/trunk/code/defines/mob/living/silicon/silicon.dm)  
` `[`code/defines/mob/living/silicon/ai.dm`](http://code.google.com/p/tgstation13/source/browse/trunk/code/defines/mob/living/silicon/ai.dm)  
` `[`code/defines/mob/living/silicon/robot.dm`](http://code.google.com/p/tgstation13/source/browse/trunk/code/defines/mob/living/silicon/robot.dm)

There are also additional files for aliens, larva, facehuggers and more
there, but the files above will have most of the variables you might
need.

### Obj

` var/m_amt = 0 // How much metal the item has. Used to determine how much metal you get when feeding it into an autolathe and how much it costs to produce it at the lathe`  
` var/g_amt = 0 // How much glass the item has. Used to determine how much glass you get when feeding it into an autolathe and how much it costs to produce it at the lathe`  
` var/w_amt = 0 // waster amounts. Not used`  
` var/origin_tech = null //Used by R&D to determine what research bonuses it grants. See examples in item definitions in code.`  
` var/reliability = 100 //Used by SOME devices to determine how reliable they are. The number represents the percentual chance for them to work properly.`  
` var/unacidable = 0 //universal "unacidabliness" var, objects with this set to 1 cannot be destroyed by acids.`  
` var/throwforce = 0 //The amount of damage applies to a target when they're hit by the item.`

More variables are defined in:

` `[`code/defines/obj.dm`](http://code.google.com/p/tgstation13/source/browse/trunk/code/defines/obj.dm)

#### Item

Items are objs which can be picked up. They're divided into several
categories according to their function.

/obj/item is defined in the following file:

` `[`code/defines/obj.dm`](http://code.google.com/p/tgstation13/source/browse/trunk/code/defines/obj.dm)

It adds the following variables (Look at the file for more, but these
are the more important ones):

` var/force = null //This determins how much damage the target takes when they're attacked by the item in hand. Small items usually have it at 0, medium ones between 5 and 10, rare and powerful items around 10-15 and two-handed items at 15 and more. Syndicate items have it even higher at 40 and more.`  
` var/item_state = null //This it the var that determines which sprite will be used for the item from icons/mob/items_lefthand.dmi and items_righthand.dmi.`  
` var/damtype = "brute" //Determines what damage type the item produces.`  
` var/health = null //Some items use this to determine when they'll break from use or damage. Not common tho.`  
` var/hitsound = null //Sound that's played when you hit something with the item. Not commonly used.`  
` var/w_class = 3.0 //Weight class.`  
`   // w_class = 1 means it's an item that can fit in a pocket (diskette, pen, cigarette packet)`  
`   // w_class = 2 means the item can't fit in pockets but can fit in a box (clipboard, analyzer, cleaner)`  
`   // w_class = 3 means the item can't fit in a box but can fit in backpacks (box, rods, metal)`  
`   // w_class = 4 means the item can't even fit in a backpack (packpack, pickaxe, fireaxe)`  
`   // w_class = 5 is used but not for weight classes.`  
` var/wielded = 0 //Used for double-handed items which can be carried in one hand but needs to be wielded by two hands before they can be used. This is determined by code when wielding and unwielding. All items should start with this at 0.`  
` var/twohanded = 0 ///Set this to 1 if your item is two-handed.`  
` flags = FPRINT | TABLEPASS //Flags`

#### Machinery

Defined in:

` `[`code/defines/obj/machinery.dm`](http://code.google.com/p/tgstation13/source/browse/trunk/code/defines/obj/machinery.dm)

Machinery are objs which cannot be picked up and generally require power
to operate. They have the following vars defined for all of them:

` var/use_power = 0 //Determines if and how much power the machine will use each tick.`  
`   //use_power = 0 - no power is used`  
`   //use_power = 1 - idle power is used`  
`   //use_power = 2 - active power is used`  
` var/idle_power_usage = 0 //How many watts of power the machine will use each tick when use_power is set to 1`  
` var/active_power_usage = 0 //How many watts of power the machine will use each tick when use_power is set to 2`  
` var/power_channel = EQUIP //Determines which APC power category the device falls under. EQUIP, ENVIRON or LIGHT`  
` var/list/component_parts = null //A list of parts needed to construct the machine from a machine frame.`

### Turf

` var/intact = 1 //This determines if the turf will hide pipes, cable and such. Set to 1 to hide and to 0 to not hide them. Only pipes and wire with level set to 1 will be hidden. Set their level var to 2 to keep them from being hidden.`  
` var/blocks_air = 0 //Determines if the turf prevents air from passing (walls) if set to 1.`

Other variables exist but they're tied to atmospherics code which is not
to be touched as whenever anything is changed in it it results in a
million things breaking.

` `[`code/defines/turf.dm`](http://code.google.com/p/tgstation13/source/browse/trunk/code/defines/turf.dm)

#### Simulated

Simulated floors are tiles which simulate air movement and temperature.
The station is made entirely from these while centcom is made from
unsimulated floors to prevent massive and unneeded lag.

` var/wet = 0 //If this it a positive number, it is wet and you'll slip on it if you run.`  
` var/thermite = 0 //Will be set to 1 when thermite is poured on it.`

##### Simulated floors

` var/icon_regular_floor = "floor" //Determines what icon the steel version of the floor should have. Determined at floor creation (New() proc). If the icon_state of the floor at that point is one from the global icons_to_ignore_at_floor_init var, then this variable is assigned the value "floor". The icons_to_ignore_at_floor_init list contains broken, plating, burnt and non-steel icon_states from icons/turf/floors.dmi`  
` heat_capacity = 10000 //When a fire (hotspot) on the tile exceeds this number, the floor has a chance of melting. The more the number is exceeded, the higher the chance of melting.`  
` var/broken = 0 //This mostly only determins if you'll get the tile back when you use the crowbar`  
` var/burnt = 0 //This mostly only determins if you'll get the tile back when you use the crowbar`  
` var/obj/item/stack/tile/floor_tile = new/obj/item/stack/tile/steel //What floor tile is on the tile`

Simulated floors are defined in:

` `[`code/game/turf.dm`](http://code.google.com/p/tgstation13/source/browse/trunk/code/game/turf.dm)

##### Simulated walls

Doesn't really contain any special new variables.

Defined in:

` `[`code/defines/turf.dm`](http://code.google.com/p/tgstation13/source/browse/trunk/code/defines/turf.dm)

[Category:Game Resources](/wiki/Category:Game_Resources "wikilink")
