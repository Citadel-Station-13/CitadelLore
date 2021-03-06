---
title: Supermatter Engine
permalink: wiki/Supermatter_Engine/
layout: wiki
tags:
 - Guides
---

The supermatter engine, located in the northwest part of Engineering, is
the main source of power for the Tether.

The supermatter engine can be extremely dangerous; when deliberately
tampered with or poorly set up, it can easily blow a substantial hole in
Engineering and leave the facility all but powerless in the aftermath.

Safety First
------------

There are a few important safety principles to remember when working
with the engine:

-   The supermatter is extremely dangerous. You can **pull** it, but any
    other attempt to touch or grab it, or bumping into it, or trying to
    use an item on it (you get the idea) will result in you instantly
    turning into a pile of ash.
    -   If it is absolutely essential to interact with the supermatter,
        you will want to ensure that you have received a backup implant
        from Medbay in case something goes wrong.
-   The radiation from the supermatter is also dangerous. Inactive
    crystals release low levels of radiation, but the engine room can be
    safely entered **as long as the core blast doors remain shut**. You
    should wear a radiation suit, with a hood, at all times when working
    in the active engine.
    -   Suits are available in the engine entrance airlock, the engine
        monitoring room, and the engine gas storage room.
    -   Engineering voidsuits will not protect you from radiation. They
        provide <i>some</i> protection, enough to keep you out of
        immediate danger if you need to work with the engine while it is
        not atmospherically stable, but you should always wear a
        radiation suit if possible.
        -   The Chief Engineer's hardsuit and EVA hardsuit are fully
            rad-shielded, in the event that prolonged exposure to both
            the supermatter and vacuum are mandatory.
-   The supermatter, even while inactive, will cause hallucinations and
    other mental effects if seen directly. Optical meson scanners
    ![](MGlasses.png "fig:MGlasses.png") must always be worn when
    working in the engine room.
    -   Meson scanners are available in the same lockers as the
        radiation suits, though you should probably be wearing your own
        pair from your locker anyway. They don't need to be turned on to
        protect your eyes, you just need to be wearing them.
-   The laser from the emitter is incredibly deadly. Don't walk in front
    of the emitter while it is on.
    -   The emitter beam is capable of damaging and destroying the core
        blast doors if they are kept closed. Always ensure that the
        blast doors are open when firing the emitter.

Principles of Operation
-----------------------

<i>If you are new to the engine and the only engineer on shift, skip
ahead to "Engine Setup" for a quick guide on how to get the engine
running, and come back to this later.</i>

![](VirSM.png "VirSM.png")

### Labelled Engine Room

![](VirSMnumbered.png "VirSMnumbered.png")

**Label meanings**

1. The omnifilters and the high-power pump that leads into the waste
loop. This is where you set where your coolant is filtered to. North
goes to waste, south is the pipeline awaiting filtering.

2. Coolant loop & high-power pump that pushes cooled coolant into the
generator loop.

3. Waste management. More on that down below. Used for containing
filtered non-coolant gas and preventing it from getting too hot.

4. Input and syphon for the gas loop. Middle two are inputs. Left one
pushes into the yellow pipes, which go into the supermatter chamber, are
siphoned out by the vent inside the chamber and are pushed into the
generator hot loop, before getting filtered and dumped back into the
chamber.

5. Emergency coolant valve. For when you need to immediately dump
something cold into the chamber. They are digital valves.

### Producing Power

The engine uses a Thermoelectric Generator - TEG for short. Its right
side is heated by the supermatter, while the left side is cooled using
the radiators. There are two TEGs, each has a nominal maximum output of
500 kW of electricity, though higher power outputs are entirely safe.

In its base state, the supermatter does not produce any heat, but when
it is activated by the ![](Emitter.png "fig:Emitter.png") emitter which
is in the engine room for this purpose, the core begins to heat up. For
this reason, in order to produce heat and therefore power, the
supermatter must be energized using the emitter; this is referred to as
"starting" the engine.

### Engine Byproducts

Activating the supermatter causes it to produce not only heat and
radiation, but also oxygen and phoron. The gas from the engine is
drained using a vent pump to the right of the supermatter. It passes
through red pipes where it enters the TEGs, is cooled down using the gas
from the cold loop to produce power, and moves to the yellow pipes. The
yellow pipes have two omni gas filters attached to them. These are used
to filter the selected engine coolant back into the hot loop, while
allowing all other gases to pass through to the waste cooling and
storage canister. The filtered and cooled coolant is then injected back
into the core chamber to repeat the process.

**Exposure to oxygen causes the supermatter to increase in reactivity,
which makes it produce greater quantities of oxygen. Positive feedback
loops are possible in certain circumstances.**

### Power Management

![](Enginesmes.png "Enginesmes.png")

Once power is generated by the TEGs, it flows through the yellow power
cables which run from the TEGs themselves to SMES room to the northeast.
Two SMES units draw power from this direct output circuit; the engine
room SMES to the left and the main power distribution SMES to the right.
The engine room SMES powers all of the equipment in the engine room via
the Engine Room APC; the main grid SMES provides power to the rest of
the facilty.

The engine room SMES draws around 60kW in normal conditions. The main
grid SMES output will depend on the facility's power draw.

### Engine Waste Handling

![](EngineWasteSetup.png "EngineWasteSetup.png")

The pipes along the north wall of the engine room cool and store the
unwanted byproducts filtered from the engine hot loop. The black pipes
to the right are the intercooler loop; they run out into space and the
gas within them is cooled by radiating heat out into space. The
byproducts never enter the intercooler loop; it must be filled with
coolant (usually phoron, but any gas will do fine.) to work.

The black pipes and canister on the left contain the engine waste.

The weird grey things between the two pipe networks are the heat
exchangers; they let the heated gas in the byproduct lines be cooled by
the colder gas in the intercooler loop.

### Engine Monitoring

![Red - Engine Cooling Control  
Orange - Power Monitering  
Yellow - Engineering Cameras  
Green - RCON Console  
Purple - Station Alert Console  
Pink - Buttons, Clockwise from top left: Reactor Blast Doors, Engine
Emitter, Monitoring Room Blast
Doors](EngineMonitoringSetup.png "Red - Engine Cooling Control Orange - Power Monitering Yellow - Engineering Cameras Green - RCON Console Purple - Station Alert Console Pink - Buttons, Clockwise from top left: Reactor Blast Doors, Engine Emitter, Monitoring Room Blast Doors")

The Engine Monitoring room, located immediately fore of the engine
itself, contains five computers as well as three buttons to control the
functioning of the engine.

From north to south, the computers are:

-   <b>Engine Cooling Control</b>: Shows the status of the engine,
    including temperature, pressure, and the composition of the gas
    mixture in the core. It also allows full control over the core vent
    pump and gas injector, should the hot loop circulation need to be
    modified.
-   <b>Power Monitoring</b>: Allows viewing of the powernet sensors on
    the current level, which includes the engine output, engine room,
    engineering, and master grids.
-   <b>Engineering Cameras</b>: Provides access to the cameras in the
    engineering department, which includes the engine room,
    atmospherics, solar array, and those of any engineering robots or
    maintenance drones.
-   <b>RCON</b>: Monitors and controls all of the SMES on the facility.
-   <b>Station Alert Computer</b>: Shows power, atmospheric, and fire
    alarms from anywhere across the facility.

The three buttons are:

-   <b>Reactor Blast Doors</b> (top left): Opens and closes the engine
    core blast doors.
-   <b>Engine Emitter</b> (top right): Toggles the emitter in the engine
    room on and off.
-   <b>Engine Monitoring Room Blast Doors</b> (bottom): Opens and closes
    the safety shutters separating Engine Monitoring from the engine
    room.

Procedures
----------

<i>This section describes all of the basic procedures which can be
carried out with the engine room equipment, including several procedures
which form part of the setup process, but is not a comprehensive guide
to engine setup. For that, see Engine Setup below.</i>

### Injecting Coolant

The line of canister ports just south of the engine core allow gas to be
freely added and removed from both the hot and cold loops. To add
coolant to the engine:

-   There are four phoron canisters in engineering gas storage room
    behind the blast doors to the south. Pull two to the input ports in
    the center.
-   Use a ![](Wrench.png "fig:Wrench.png") wrench on the canisters to
    attach them to the ports.
-   Access the pumps controls by clicking with an empty hand on the
    pump; click "MAX" to maximise the target pressure and click on the
    power toggle to turn it on.
-   When the coolant canister is empty, ![](Wrench.png "fig:Wrench.png")
    wrench it again to disconnect it, and either reuse it as a drain
    tank or drag it to Atmospherics so that it can be refilled.
-   Add an additional canister to the cold loop.

### Starting the Engine

<span style="color:#ff0000"><i>Do not start the engine unless all other
engine setup has been completed.</i>

Starting the engine entails activating the supermatter core using the
emitter in the engine room. In can be done from either inside the engine
room itself, or inside the Engine Monitoring Room.

-   Ensure that all engine setup has been completed.
-   Open the Reactor Blast Doors using the appropriate button.
-   Activate the ![](Emitter.png "fig:Emitter.png") emitter.
    -   From inside the engine room, click on the emitter itself with an
        empty hand. From the Engine Monitoring room, press the button.
-   Allow the emitter to fire the required number of shots.
    -   The emitter fires in bursts of four shots with a longer pause
        between bursts. You can turn it off at any time, even in the
        middle of a burst.
    -   16 shots will provide sufficient power to the facilty for the
        the length of a normal shift. Additional shots will provide more
        power, but risk causing radiation to penetrate beyond the engine
        room into the monitoring room and engine hallway.
    -   If you are "boosting" the engine mid-shift, you should never
        fire more than one shot at a time, then give it some time to see
        that temperature is stable.
-   Turn the emitter off in the same way you turned it on.
-   Close the Reactor Blast Doors.

### Removing Engine Coolant

In some situations, such as minor overheating of the engine, you may
wish to purge the engine of coolant before injecting more. The engine is
specifically designed to allow you to pump coolant into canisters in
order to do this.

-   Find an empty canister and relabel it as a hazard canister.
    -   (To do this, click on the canister with an empty hand to access
        its control panel, and then click the "Relabel" button. The
        button will be greyed out unless the canister is completely
        empty)
-   Use a ![](Wrench.png "fig:Wrench.png") wrench to attach the hazard
    canister to hot loop gas removal connector, on the far left of the
    coolant input/output array.
-   Turn the pump on and set the target pressure to maximum.
-   Wait for the engine to drain. This can take time, and may require
    changing a full hazard canister for an empty one, using a
    ![](Wrench.png "fig:Wrench.png") to disconnect the one and connect
    the other.
    -   In an emergency, it is seldom necessary to fully drain the
        engine before injecting new coolant. Alternating between both
        may be less risky.
-   Once the engine has drained, turn off the pump.
-   Disconnect the hazard canister containing the drained coolant, and
    return it to Atmospherics to be emptied.
-   <i>It is essential to add new coolant if the old coolant has been
    drained. Without coolant, the engine will rapidly overheat.</i>

### Venting the Core

When engine overheating is serious enough that there is no time to drain
the engine, the coolant inside the engine can instead be vented into
space. There is a shutter north of the core which vents directly into
space. There are two buttons which control this shutter. One is located
in the along the south wall of the engine room, another in the Chief
Engineer's Office near the entrance to the Engineering lobby.

Venting the core is as simple as pressing either of the two buttons to
open the shutters, and allowing the coolant to vent. This can take a
long time - up to a minute or two if the coolant is especially hot or
high-pressure - since much of the coolant will be in the pipes rather
than in the core when venting starts. Engine pressure can be monitored
from the Engine Cooling Control computer in Engine Monitoring.

Once the core has been fully vented, be sure to close the shutter before
refilling it with coolant.

### Ejecting the Supermatter

If it is utterly impossible to salvage the engine situation, it is
possible to eject the supermatter into space, avoiding severe damage to
the facilty.

-   Gain access to the Chief Engineer's Office, where the eject button
    is located.
    -   If there is no Chief Engineer on staff, you will need to ask the
        AI to open the door for you.
    -   If there is no AI either, you will need to either [hack the
        airlock](/wiki/Guide_to_Hacking "wikilink") or disassemble one of the
        windows to get in.
-   Ensure the the engine vent is open. There is a button to do so on
    the wall behind the Chief Engineer's desk, and another in the
    engine.
    -   If you accidentally close the shutters instead of opening them
        by pushing the button when someone in the engine room has
        already opened them (or someone else does so) the ejection will
        fail, and will not be repeatable.
-   The eject button is located in an alcove behind the Chief Engineer's
    desk, behind a glass panel. Break the glass using your crowbar, a
    toolbox, or any other heavy object. Doing so may take several hits.
-   <span style="color:#ff0000">Verbally confirm that the engine vent is
    open with either a crewmember in the Engine Room or the facilty's
    AI.
-   Press the eject button.

A new supermatter core can be ordered from the Cargo department to
replace the ejected one.

Engine Setup
------------

This section details the process of setting up the engine for the first
time at the start of the shift.

Many people have developed additions to this procedure which they carry
out as standard, but unless you're told otherwise the steps which are
listed here are more or less universal.

### Coolant Setup

Setting up the engine cooling system is essential to prevent the engine
from overheating.

1.  There are four phoron canisters
    ![](Plasma_canister.png "fig:Plasma_canister.png") in engine gas
    storage south of the engine core.
2.  Place a can directly over the hot loop input and cold loop input
    connectors ![](Connector_Port.png "fig:Connector_Port.png") and
    wrench them to secure them.
3.  Turn on the pumps ![](Pump.png "fig:Pump.png") leading from the port
    and maximize their output.
4.  Wait until the cans are fully drained (the pump will show that its
    power use is 0).
5.  Unwrench the canisters, and add an additional phoron canister to the
    cold loop connector.
6.  Configure the omni-filters
    ![](Omni_gas_filter.gif "fig:Omni_gas_filter.gif") in the center of
    the room. North should always be output, you can see which other
    directions are available by looking at the pipes around the filters.
    One of the two remaining directions needs to be the input, and the
    other needs to filter the kind of coolant you are using. Once they
    are set, turn them on.
    1.  There is currently a bug that causes the omni-filters to fail
        unexpectedly, causing all hot loop coolant to be flushed into
        the waste cooler. This will eventually cause the core to
        overheat and potentially delaminate. Until
        <https://github.com/VOREStation/VOREStation/issues/2021> is
        resolved, replace the omni filters by unwrenching them and
        acquiring a gas filter and mirrored gas filter from the pipe
        dispenser in backup atmospherics, just south of engine gas
        storage. The normal filters are activated automatically when
        secured, so quickly change their filtered gas to the intended
        coolant.
7.  Turn on the high-power pump
    ![](Volumetric_Pump.png "fig:Volumetric_Pump.png") near the window
    west of the connector ports to circulate the cold loop.
8.  Make sure to maximize the coolants pumps output, or risk damage by
    overheating.

### Engine Waste and Intercooler Loop

After that, go to the north wall of the engine room. You may notice an
empty yellow canister connected to a port marked with a yellow dotted
outline. Across from it in the northeast corner, there is a connector
port for adding gas to the cooler loop, and another just below it for
removing gas.

1.  Connect any type of gas canister to the top port.
    1.  It can be any type of gas. Using the fourth unused phoron
        canister is generally advised, however.
2.  Make sure the pump next to this port is turned on and set to max.

### Activating the Supermatter

Now that everything is set up, you can start the engine.

1.  Be sure to wear optical meson scanners
    ![](MGlasses.png "fig:MGlasses.png") and a complete radiation suit
    ![](Radiation_Suit.png "fig:Radiation_Suit.png")
    ![](Radiation_Hood.png "fig:Radiation_Hood.png") if performing this
    from the engine room, as it involves visual contact with the
    supermatter crystal.
2.  Click the 'Engine Monitoring Room Blast Doors' button on the
    southeast corner of the core chamber to close the shutters between
    the engine room and Engine Monitoring.
    1.  This step can be performed from the monitoring room, the button
        is on the bottom center of the table.
3.  Click the 'Reactor Blast Doors' button just below the first button
    to open the supermatter chamber blast doors.
    1.  This step can be performed from the monitoring room, the button
        is on the upper left of the table.
4.  Click on the emitter ![](Emitter.png "fig:Emitter.png") and let it
    fire . <b>Sixteen</b> shots is advisable if you used phoron coolant.
    Click on it again to stop it from firing. More shots can be fired
    with minimal risk of overheating, but excessive radiation leaking
    from the engine room becomes the main concern.
    1.  This step can be performed from the monitoring room. Use the
        engineering camera monitor to visually ensure that the reactor
        blast doors are open before firing. The button is on the upper
        right of the table.
5.  Close the reactor blast doors.

### Setting Up the SMES

There are two SMES units [\[File:SMES.png]([File:SMES.png "wikilink")
which need to be set up in the Engine SMES room found northeast of the
engine room.

1.  Set up the SMES units to input and output according to your engine
    output.
    1.  To do this, you need to know your power output, which is
        displayed on either of the SMES units as 'Input Load'.
        Alternatively, you can use a
        ![](multitool.png "fig:multitool.png") multitool on a wire in
        the engine room and it's reading will be your output.
    2.  The main distribution SMES take power with higher priority than
        the engine SMES - meaning that if you set input on it higher
        than the engine's power output, the engine room will eventually
        run out of power and cooling will stop working.
2.  From here, you may go to the different
    [Substations](/wiki/Substations "wikilink") around the facilty, and set up
    those smaller sub-grids (Not required but highly recommended).
3.  Alternatively, you could use one of the RCON consoles to remotely
    modify any of the SMES on facilty.

Optimization and Maintenance
----------------------------

### Supermatter Upkeep

The supermatter very, very gradually decreases in heat output after
being energized. Additional charging may be needed after several hours
if the power production is not enough to charge the
![](APC.png "fig:APC.png") APC units across the facilty.

1.  Check the nearby Power Monitoring computer to see the power output
    of the 'Engine Output' power network.
2.  If the ![](SMES.png "fig:SMES.png") SMES units have a solid red
    light on top, they are not charging. If this is so, you must either
    increase output or lower the input on other SMES that are drawing
    from the same network.

### Power Output

Once all APCs around the facilty have been fully charged, power
requirements are reduced. If you wish to reduce potential harm caused by
electrical shock, output levels can reduced as well.

1.  Check the 'Master' power network using a power monitering console to
    see the current power load.
2.  Adjust the ![](SMES.png "fig:SMES.png") SMES output charge
    accordingly, with some margin to allow for occasional power spikes
    as APCs recharge or power-hungry devices such as rechargers are
    used.

Engine Emergencies
------------------

If the core chamber gets too hot, the supermatter crystal will begin to
lose stability and delaminate. In such situations, the Engine Monitoring
Computer will make an announcement over the engineering radio channel to
that effect. If you hear this announcement, hotfoot it to the engine
room <i>immediately</i>. Unless there are many other engineers on shift
to do it, your first priority is to get the engine under control.

The first thing you should do is try to find the problem which caused
the engine temperature to spike. Power failures due to not setting the
![](SMES.png "fig:SMES.png") engine SMES output high enough, or not
turning its input from "Off" to "Auto", are surprisingly common. A loss
of coolant through filter failure or external chamber breach are also
possible sources of overheating. Otherwise, any number of things may be
tampered with by a troublemaker to cause things to go awry. Often,
simply finding and fixing the problem will cause the engine to stabilise
by itself. If, however, the core integrity drops below 50% and you have
not found the cause, you urgently need to cool the core if only to give
yourself time to find the root of the problem.

There are essentially three things you can do to get the engine
temperature down to safe levels while searching for and fixing the
source of the problem:

<b>Emergency Cooling Valves</b> are placed below and to the northwest of
the TEGs. Opening both valves combines the hot and cold loops, directly
connecting the core chamber input and output vents to the main radiator
array. This drasticly increases the rate that heat can be removed from
the chamber assuming there is any amount of coolant avaialable. Doing
this is a solid first move if stability is still dropping and the source
of the problem is not readily apparent. Note that while the loops are
merged minimal power will be produced from the TEGs, so this is not
ideal if the cause of overheating is lack of power to the engine room.

<b>Emergency Coolant Injection</b> is always a stopgap measure, but it
can be one that saves your life. Injecting fresh coolant into the engine
without getting rid of the current coolant is a quick way to bring the
overall chamber temperature back down while you work to resolve the
source of the overheating. This is especially effective if Atmospherics
have cooled some phoron especially for use as emergency coolant.

<b>Venting and replacing</b> the coolant is a faster, though more
wasteful, method of accomplishing the same thing. If core stability
drops below 40% and you aren't well on your way to resolving the primary
issue, a full replacement of the engine coolant can buy a significant
amount of time. Simply vent the engine core and then, once the vent has
been closed, inject fresh coolant.

<b>Ejecting the supermatter</b> is the final option and should not be
performed unless the situation is fully uncontrolled or a delamination
is inevitable. If stability drops below 20% and it seems that you cannot
stop the loss of stability regardless of actions taken, you should eject
the core as per Procedures above. If there are enough engineers on
staff, at least one should be standing by to eject while the others work
on other methods of getting the core under control, just in case it
becomes necessary.
