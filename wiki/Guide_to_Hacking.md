---
title: Guide to Hacking
permalink: wiki/Guide_to_Hacking/
layout: wiki
tags:
 - Guides
---

<figure>
<img src="screehacking.png" title="&quot;Naturally, we don&#39;t condone this sort of thing.&quot;" alt="&quot;Naturally, we don&#39;t condone this sort of thing.&quot;" width="400" /><figcaption>"Naturally, we don't condone this sort of thing."</figcaption>
</figure>

What You'll Need
----------------

-   ![](Yellowgloves.png "fig:Yellowgloves.png") Insulated gloves -
    Hackables have power lines, and cutting/pulsing these without gloves
    can harm you.
-   ![](Screwdriver_tool.png "fig:Screwdriver_tool.png") Screwdriver -
    For opening up panels and the like. A necessary tool
-   ![](Wirecutters.png "fig:Wirecutters.png") Wirecutters - For cutting
    and mending wires. Also a necessary tool
-   ![](Multitool.png "fig:Multitool.png") Multitool - For pulsing
    wires; not necessary for most hacking, but makes life a lot easier.
-   ![](Crowbar.png "fig:Crowbar.png") Crowbar - For prying the door
    open once you've hacked it.

![](Airlock.png "fig:Airlock.png") ![](Airlock_external.png "fig:Airlock_external.png") Airlocks
------------------------------------------------------------------------------------------------

Both internal and external access airlocks are hackable, though
![](Hazard_Door.png "fig:Hazard_Door.png") hazard doors are not
hackable. Wires are randomized at the start of each round, but are
standardized throughout the station (e.g., every orange wire might
toggle the bolts). This is probably where you'll be doing the most of
your hacking. Remember, cutting power to the door will stop everything
else from working.

### ![](Multitool.png "fig:Multitool.png") With a Multitool

#### Finding the Right Wires

Remember, wires are randomized, so you need to identify them the first
time. The most important ones to identify are the "test light" wire and
the "door bolts" wire.

1.  Remember to equip ![](Yellowgloves.png "fig:Yellowgloves.png")
    insulated gloves to prevent electric shock.
2.  ![](Screwdriver_tool.png "fig:Screwdriver_tool.png") Screwdriver in
    hand, click on the airlock to open the panel and expose the wiring
3.  With a ![](Multitool.png "fig:Multitool.png") multitool, click on
    the airlock to access the wiring.
4.  Click each "Pulse" link to pulse the wires, and keep an eye on "The
    door bolts" and "The test light" at the bottom of the menu (two
    wires will cause this - pick either one). When you see either the
    "The test light is off!" or "The door bolts have fallen!", remember
    the colors of both wires.
5.  To put the door back to normal, the test light will need to be on
    first. It will come back on by itself after 10 seconds. Then,
    re-pulse the door bolts wire to put them "up" again, and close the
    wiring panel with your screwdriver.

#### Airlock Hack

If you have a multitool, getting through doors gets a lot easier and
faster.

1.  Have the ![](Multitool.png "fig:Multitool.png") multiool in one hand
    and a ![](Crowbar.png "fig:Crowbar.png") crowbar in another for
    quick switching. You'll only have 10 seconds (but you can retry if
    you fail).
2.  Pulse the **Test light** wire, then quickly switch to your crowbar
    and click on the door to pry it open while the power is off.
    -   *Note: The door will stay open. If you want to close it, click
        on it with the crowbar again, then use the screwdriver to close
        the wiring panel.*

### ![](Multitool_no.png "fig:Multitool_no.png") Without a Multitool

#### Finding the Right Wires

Make sure you choose a door that you and everyone else won't mind you
breaking, because in most cases this will prevent the door from opening
again until it's repaired by an Engineer.

1.  Remember to equip ![](Yellowgloves.png "fig:Yellowgloves.png")
    insulated gloves to prevent electric shock.
2.  ![](Screwdriver_tool.png "fig:Screwdriver_tool.png") Screwdriver in
    hand, click on the airlock to open the panel and expose the wiring
3.  Equip ![](Wirecutters.png "fig:Wirecutters.png") wirecutters.
4.  Click on the door to open the menu, then slowly **Cut** each wire
    until you see "The door bolts have fallen!" at the bottom of the
    menu. Remember the color of the wire you cut that caused the bolts
    to drop.
    -   *Note: if you're lucky enough to be on the last wire and you
        haven't seen the bolts drop yet, you know that wire is the
        winner, so you don't need to cut it. Just remember its color.*
5.  **Mend** all the wires and leave that door alone.
6.  Now that you know the wire color for door bolts, move on to the next
    door (or if you were lucky and found the bolt wire without cutting
    it, you can continue with the same door and skip to step \#3 below.)

#### Airlock Hack

1.  Open the wiring panel with the
    ![](Screwdriver_tool.png "fig:Screwdriver_tool.png") screwdriver.
2.  Using the ![](Wirecutters.png "fig:Wirecutters.png") wirecutters,
    cut all wires EXCEPT for the door bolts wire that you found earlier.
3.  Use a ![](Crowbar.png "fig:Crowbar.png") crowbar on the door to pry
    it open.

#### Emergency Unbolting Procedure

Airlocks aboard the station are equipped with SecureDoor(tm)
inductive-coupling bolt triggers. By allowing the bolts to drop using
(ambient or artificial) gravity, bolts can be dropped and security
maintained even in low-power situations! The actuator used to raise the
bolts, however, requires power to function.

In an emergency, door bolts can be raised without power using the
following procedure.

1.  Weld the door shut using a ![](Welderon.gif "fig:Welderon.gif")
    welding tool.
2.  Next, break the protective cover behind the airlock electronics with
    a sturdy object (use harm intent).
3.  Finally, use a ![](Crowbar.png "fig:Crowbar.png") crowbar to
    manually raise the bolts from the inside.

### Wire Functions

-   **ID wire**: *Pulsing* will flash the 'access denied' red light;
    *cutting* will prevent anyone from opening the door if it's a
    restricted door; otherwise, it does nothing.
-   **AI control wire**: *Pulsing* will flash the 'AI control light' off
    and on quickly; *cutting* will prevent the AI from accessing the
    door unless s/he hacks the power wires
-   **Main power wires (2)** (Test light wires): *Pulsing* will turn off
    the 'test light' and kill the power for a short time; *cutting* will
    kill the power for a time before backup power kicks in. There are
    two of these, and both are needed for the main power to work.
    Cutting will cause sparks.
-   **Backup power wire (2)**: *Pulsing* will turn off the 'test light'
    kill the power for a short time if the main power is out, otherwise,
    nothing. *Cutting* will obviously disable the backup power. There
    are two of these, and both are needed for backup power to work.
    Cutting will cause sparks.
-   **Bolt control wire**: *Pulsing* will toggle the bolts; *cutting*
    will drop the bolts.
-   **Bolt light wire**: *Pulsing* will toggle if the bolt/access lights
    will flash or turn on. *Cutting* will turn the lights off until
    mended.
-   **Door control wire**: If the door is ID restricted, this is pretty
    much useless. If not, *Pulsing* will open/close the door and
    *cutting* will keep it that way, sort of like bolting.
-   **Electrifying wire**: *Pulsing* will electrify the door for 30
    seconds; *cutting* will permanently electrify it until mended. This
    will cause the safety light to flash. You can find the wire easily
    because the door shoots sparks when pulsed or cut. Obviously useless
    if there is no power to the door.
-   **Door safeties wire**: *Pulsing* will cause the check wiring light
    to toggle, causing the door to no longer check if someone is in the
    door before closing if it is on. *Cutting* will permanently turn off
    the safeties until mended
-   **Door timing wire**: *Pulsing* will toggle the door's timer, and
    the check timing light. If the light is on, the door will try to
    close as immediately as it can. *Cutting* it will turn off the timer
    until mended.

### Strategies

-   **Create an obstacle** by dropping the bolts, cutting all the wires,
    and then welding the door shut. This is especially effective if you
    happen to have the only pair of insulated gloves on the station.
-   **Remotely pulse an airlock** by attaching a signaler, which when
    signaled pulses the wire it's attached to. This allows you to
    remotely bolt and unbolt a door, for instance. Be sure to turn off
    the speaker so no one can hear it being toggled.
-   **Hacking without gloves**. First find two wires of importance. The
    bolts wire, and the test light wire. Pulse a random door to find out
    the wires. If you hear sparks, see your health going down or see the
    message "You feel a powerful shock coursing through your body!",
    close that hacking window and move onto another door. Once you got
    the main power wire, head to an unbolted door, pulse the wire,
    crowbar it open. You get a larger window of time to crowbar, and you
    can do it without gloves.

![](APC.png "fig:APC.png") APCs
-------------------------------

Used to control power to a certain room. All APC breakers can be
accessed via Power Monitoring Computers regardless of the lock status,
and can be remotely controlled from there.

1.  ![](Screwdriver_tool.png "fig:Screwdriver_tool.png") Screwdriver in
    hand, click on APC to open the panel and expose the wiring.
2.  Equip a ![](Multitool.png "fig:Multitool.png") multitool.
3.  Put ![](Wirecutters.png "fig:Wirecutters.png") wirecutters in your
    other hand to quickly **Cut** and **Mend** a wire if you short out
    the power accidentally (which will likely happen).
    -   **Power wires (2)**: *Pulse* will short out the APC. You must
        *cut and mend* the wire to restore power. Not repairing the
        short will render the main breaker moot, even if accessed
        remotely.
    -   **AI control wire**: Like the airlock, *pulsing* will flash the
        light off and on quickly; *cutting* will disable AI control
    -   **APC lock wire**: This is the wining wire you want to pulse in
        order to unlock it.
4.  Use a screwdriver to close the wiring panel back up.

![](AirAlarm.png "fig:AirAlarm.png") Atmospheric Alarms
-------------------------------------------------------

Used to monitor environmental factors in a room, such as temperature,
pressure, toxins, etc.

1.  ![](Screwdriver_tool.png "fig:Screwdriver_tool.png") Screwdriver in
    hand, click on Air Alarms to open the panel and expose the wiring.
2.  Equip a ![](Multitool.png "fig:Multitool.png") multitool
    and![](Wirecutters.png "fig:Wirecutters.png") wirecutters.
    -   **Id Scan**: *Pulsing* will unlock the alarm for 30 seconds.
        *Cutting* will not allow people to access the alarm even if they
        have the correct ID. *Mending* will allow normal operation.
    -   **Alarm**: *Cutting* will cause an atmos alert in the area, and
        most likely alert the AI as well. *Pulsing* will reset the alarm
        status. *Mending* allows the alarm to work again.
    -   **Panic Syphon**: *Cutting* or *Pulsing* this wire will activate
        the panic syphon. *Mending* does nothing, and it must be turned
        off from the actual alarm.
    -   **AI Control**: *Cutting* this wire will prevent the AI from
        using the alarm. *Pulsing* it flashes the light on and off
        quickly. *Mending* allows AI control.
    -   **Power**: *Cutting* this wire will deactivate the alarm.
        *Pulsing* it turns it off for 30 seconds. *Mending* restored
        power.
3.  Use a screwdriver to close the wiring panel back up.

![](Autolathe.gif "fig:Autolathe.gif") Autolathes
-------------------------------------------------

1.  ![](Screwdriver_tool.png "fig:Screwdriver_tool.png") Screwdriver the
    autolathe to open the maintenance panel.
2.  Click on the autolathe with an empty hand to access the wiring.
3.  There are three important wires. Cutting them toggles their light
    permanently, pulsing does so temporarily. Red light is power, green
    light is electrocution and blue is hacked options.
4.  Have fun accessing some new options:
    -   Compressed matter cartridges (for the RCD)
    -   Handcuffs
    -   Infrared beam (security)
    -   Infrared sensor
    -   Bullets
    -   Other stuff

![](MULE.gif "fig:MULE.gif") MULEs
----------------------------------

1.  Unlock the controls with a Quartermaster's ID.
2.  Unscrew the maintenance panel with the screwdriver.
3.  Pulse various wires with a [multitool](multitool "wikilink"). Pay
    attention to the reaction the MULE gives. Also note that these wires
    are randomized for each MULE
    1.  Cutting the wire that causes the loading bay to thunk will
        remove cargo restrictions.
    2.  Cutting the wire that leads to the safety light will awaken its
        thirst for blood and cause it to run over people in its path. DO
        NOT DO THIS UNLESS YOU HAVE A VERY GOOD REASON.
    3.  Cutting *one* of the wires that makes the motor whine will
        safely speed up the MULE. Cutting both will immobilize it.
4.  Screw the panel back on.

### Wire Functions

| Response from multitool                    | Effect if cut                                                                                                             |
|--------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|
| The drive motor whines briefly.            | Increases speed, disables motor if both wires are cut                                                                     |
| You hear a radio crackle.                  | Disables PDA control                                                                                                      |
| The charge light flickers.                 | Disables power                                                                                                            |
| The external warning lights flash briefly. | Disables safety, awakens thirst for blood (DON'T DO THIS UNLESS YOU'RE A TRAITOR. EVEN THEN IT'S REALLY NOT A GOOD IDEA.) |
| The load platform clunks                   | Allows nonstandard cargo such as humans, cyborgs, and other bots                                                          |

![](Security_Camera.gif "fig:Security_Camera.gif") Cameras
----------------------------------------------------------

Used to view rooms from, they also have upgrades which allow them to see
through walls, be invincible against EMPs and have a motion detection
system.

1.  With a screwdriver in hand, click on the camera.
2.  After opening the panel, use your wirecutter on the camera. You will
    now get a wire cut menu like the airlock. There are multiple wires
    to look out for. NOTE: Every camera will have randomized wires.
    -   **Power Wire** - Cutting it will disable the camera, fixing it
        will enable the camera. Pulsing toggle the camera on and off.
    -   **Alarm Wire** - You do not want to cut this wire. You have to
        use a multitool to detect this, as it'll give off a beeping
        sound when pulsed. Cutting will trigger an alarm, fixing it will
        cancel the alarm.
    -   **Light Wire** - Cutting this will stop the AI from using the
        camera's light, fixing it will allow the AI to use the camera
        light. Pulsing toggles it.
    -   **Focus Wire** - Cutting this will shorten the vision range to a
        default set of 2 tiles, fixing it will return it back to a
        normal 7 vision range. Pulsing it will toggle between the short
        and normal vision range.
    -   Two **Nothing Wires** - They do nothing, still required to
        deconstruct the camera.

You can find a guide to deconstruct cameras
[here](/wiki/Guide_to_construction#Security_Camera_2 "wikilink").

Particle Accelerator
--------------------

What a better way to release the
[singularity](/wiki/Singularity_Engine "wikilink") than to do it REMOTELY!
That or you can hack it to make it shoot more powerful particles!

1.  Setup the PA if you haven't already, then use a screwdriver on the
    computer to open the panel/expose the wires.
2.  Now click on the computer with a hand to bring up the wire menu.
    Here you can then get your tools in hand.
    -   The **toggle wire** will toggle the PA on or off when pulsed, if
        cut it will disable the PA and stop it from turning on.
    -   The **strength wire** will increase the strength of the PA when
        pulsed, if cut it will toggle the strength to 0 and stop people
        turning it up.
    -   The **interface wire** will stop people being able to use the
        control computer. Pulsing will toggle this, cutting/mending will
        toggle it on/off.
    -   The **limit power wire** will allow the PA to be turned up to
        strength 3 when cut. When pulsed it will beep.
    -   The **nothing wire** will do nothing, it's just here to make
        life harder.
3.  Close the panel for the PA to then work again. **IMPORTANT:** Don't
    forget to scan the parts again.

Now remember, you can attach a signaler to these wires to release the
singularity, such as remotely pulsing the strength wire. Bonus points if
you also pulse the interface wire so that people can't stop it!

Syndicate Bomb
--------------

A bomb! Are you a bad enough dude to attempt to defuse a live explosive
that, if it were to explode, could reduce you to a fine red mist?

1.  Check the description of the bomb to see if you have enough time
    left to even attempt a defusal. Use your best judgement for how much
    time you will need.
2.  If the timer is very long you might want to ask toxins for a bomb
    suit in case you fail, you'll still be killed, but at least you'll
    leave a corpse
3.  Screwdriver in hand, click on the bomb to open the panel and expose
    the wiring
4.  With multitool, wirecutters, or an empty hand, click on the bomb to
    access the wiring.
5.  CAREFULLY fiddle with the wires by pulsing to test each one and
    cutting what you need to.
    -   **Boom wire**: *Pulsing* will explode the bomb instantly if the
        bomb is live and *cutting* will do much the same! There's no way
        to prepare for the boom wire if the bomb is already live, it's
        just an inherent risk. Cutting a boom wire that's not live will
        make the bomb unusable.
    -   **Bolt wire**: *Pulsing* will hint at this wire's function,
        *cutting* will release the bolts holding the bomb down if they
        were activated to begin with. Ditch that bomb!
    -   **Delay wire**: *Pulsing* will add time to the clock of the
        bomb, giving you a little more breathing room.
    -   **Proceed wire**: *Pulsing* will reduce the clock, making your
        life that muich harder. *Cutting* this wire while the bomb is
        live will explode the bomb!
    -   **Activate wire**: *Pulsing* a bomb that isn't live will start
        the countdown and *cutting* a bomb that IS live will stop the
        countdown. If you've identified this wire, you've won!

Keep in mind that randomly pulsing a live bomb carries a 20% risk of
sudden death, but randomly cutting carries a 40% risk. Ultimately you
will HAVE to cut a wire to stop the explosion, but with a little
research with pulsing you can improve your success rate.

Hardsuits
---------

These hightech [hardsuits](hardsuit "wikilink") are hard to come by, but
can be hacked to be bent to your will.

1.  Swipe your ID on the Hardsuit to unlock the panel, then use a
    <file:crowbar.png> to open it. An [emag](emag "wikilink") might come
    in handy.
2.  Equip a ![](Multitool.png "fig:Multitool.png") multitool
    and![](Wirecutters.png "fig:Wirecutters.png") wirecutters.
    -   *' Security Wire*': Can be cut to disable Security Checks on the
        suit. The suit will twitch when this wire is pulsed.
    -   *' AI Override*': Can be pulsed to toggle whether the AI can
        control the suit. A red light will flicker when this wire is
        pulsed.
    -   *' System Control*': Can be pulsed to toggle some malfunctions.
    -   *' Interface Lock*': Can be pulsed to toggle whether the
        interface can be accessed. The suit will click audibly when this
        wire is pulsed.
    -   *' Interface Shock*': Can be pulsed to toggle whether the suit
        shocks the user or not.
3.  Close the panel.

Minor Hackables
---------------

I haven't a clue why you'd ever want to hack any of these things, but
you can!

### ![](FireAlarm.png "fig:FireAlarm.png") Fire Alarms

Fire alarms on getting cut will not detect or activate the fire doors in
the case of a fire or a breach.

### ![](Station_Bounced_Radio.png "fig:Station_Bounced_Radio.png") Station-Bounced Radios & ![](Signaler.png "fig:Signaler.png") Signalers

1.  Screwdriver in hand, click on the offending radio so it can be
    modified or attached
2.  The usual radio use panel will pop up, but now with access to the
    wiring. If you've closed it by accident, just click on the radio as
    if you were going to change the settings on it.
3.  There are three wires. Two have apparent uses; the third is pretty
    much useless.
    -   **Output wire** will disengage the speakers (or signal-receiving
        on a signaler)
    -   **Input wire** will permanently disengage the microphone (or
        signal-sending on a signaler)

Interestingly, tracking beacons and station intercoms also count as
radios.

### ![](Securebriefcase.png "fig:Securebriefcase.png") Secure Briefcases

1.  Screwdriver in hand, click on the (briefcase/safe) to open the panel
    and expose the wiring
2.  Multi-tool-spam the (briefcase/safe) until you get a confirmation
    that the memory is reset.
3.  The memory is now reset. Punch in your favorite code and hit E to
    set it.
4.  Screwdriver the panel shut.

### ![](Vendcola.gif "fig:Vendcola.gif") Vending Machines

The only thing worth hacking!

Four wires

1.  **Firing wire** when cut fires stuff at people. When pulsed will do
    so. Controlled by the blinking light.
2.  **Contraband wire** does nothing when cut, when pulsed unlocks
    illegal or rare goods. Wire is unknown.
3.  **Access wire** when cut it turns on a orange light, allowing for ID
    restricted machines(med machines, sec machines, possibly botany
    machines) to be used by anyone.
4.  **Shock wire** Like the firing wire in effects from hacking, except
    it shocks instead of shoots.
