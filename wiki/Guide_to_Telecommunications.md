---
title: Guide to Telecommunications
permalink: wiki/Guide_to_Telecommunications/
layout: wiki
---

The **telecommunication** system adds an entire realm of complexity to
the very simple and previously straight-forward process of radio
communication.

The Central Compartment
-----------------------

A functional telecommunication central compartment (otherwise known as
the "Server Room") contains several machines, each with its own isolated
function. These machines make up a usually independent telecommunication
network, with a pre-specified array of frequencies to process.
Optionally, monitoring computers may be used to keep track of
telecommunication activity and network integrity. It is important to
notice that the machines, most dominantly the *Processor Units*,
generate a significant amount of heat. The central compartment is
generally kept at a very low temperature to prevent the damage of the
hardware infrastructure, so maintenance is usually not done without
proper protective equipment.

A *central* communications compartment is not necessary for a functional
telecommunications network. In fact, it may be more efficient to
separate the network into sub-nets. Nanotrasen Tech Department, however,
strongly suggests the centralization of the machinery for easier
maintenance and bookkeeping. While a strong central compartment may be
easier to maintain, it is also easier to sabotage or blow up. The only
thing worse than explosive concussion damage and massive atmospheric
de-stabilization is a downed communication grid. A central compartment
should be well-fortified and stable, and fortunately for the crew,
Nanotrasen cannot pinch for pennies in this department. The station will
either receive a robust Communications Satellite or inner-station Server
Room.

The Machines
------------

There are 5 different kinds of machines essential for a healthy
telecommunication network. Without one or the other, the entire system
would cease to function or would not function optimally. All
telecommunication machines idle until they receive a signal, and all the
machines are built with Hyperwave Filtering modules that allow for the
scanning of signal's frequency regardless of intensity. This means each
machine can selectively choose which signals to pay attention to, if
there are any specified frequencies to tune into.

### <img src="Sreceiver.gif" title="fig:Sreceiver.gif" alt="Sreceiver.gif" width="64" /> Subspace Receivers

Subspace Receivers are essential to a subspace telecommunication
network. They have a long-term subspace window open at all times, and
create the subspace-equivalent of a gravity well in its warped version
of space-time. FTL signals traveling in subspace are going too "fast" to
be sucked into the gravity well, but a carbon copy of the signal is
produced whenever a signal passes through the pocket. This signal is
then converted into a real radio wave by the Subspace Receiver and
passed onto all immediately-linked machines. In a typical scenario only
Bus Mainframes would receive the signal.

![A simple visual synopsis of a basic radio telecommunication network.
It shows the "route" a subspace transmission travels before it reaches
its end
destination(s).](SpessChart.png "A simple visual synopsis of a basic radio telecommunication network. It shows the "route" a subspace transmission travels before it reaches its end destination(s).")

### <img src="Bus.gif" title="fig:Bus.gif" alt="Bus.gif" width="64" /> Bus Mainframes

*Bus Mainframes* regulate and handle the transfer of massive quantities
of data at near instantaneous speeds. They are not essential to a
network, but are required to keep data transfer instant. They usually
transfer data back and forth between servers and processor units. If a
Bus Mainframe is missing, network output may be unreliable or slow.

### <img src="Pro.gif" title="fig:Pro.gif" alt="Pro.gif" width="64" /> Processor Units

*Processor Units* decrypt, clean and stretch hyper-compressed radio
signals. Radio signals are sent into subspace using a preset encryption
hash but random seed, which makes the process of encrypting and sending
very light but unpacking and decrypting heavy due to the weird nature of
subspace. Processor Units can instantly make signals readable by other
machines. They are not essential to a subspace network but if one is
missing, network output may not be understandable.

### <img src="Server.gif" title="fig:Server.gif" alt="Server.gif" width="64" /> Telecommunication Servers

*Telecommunication Servers* log network statistics and signal traffic
for easy maintenance. Each server represents a "channel" in the
Nanotrasen default settings. They can listen in to multiple channels,
however. For each signal that is sent to a server, a database entry is
created and the signal's information is stored. The servers also help by
sorting the order in which signals are transferred to subspace
broadcasters, which is vital for instantaneous signal transferring.

### <img src="Broad.gif" title="fig:Broad.gif" alt="Broad.gif" width="64" /> Subspace Broadcasters

*Subspace Broadcasters* are impressive pieces of hardware that are
capable of opening large enough subspace windows to transfer
de-compressed data bursts, in encoded radio waves, through. They are
necessary for any network that is expected to output information back to
receiving radio devices. They operate by directing high-powered lasers
into a small subspace window and fluctuating the amplitude of radio
waves through subspace, allowing the large data packets easier entering
and exiting of subspace.

Maintenance Guide
-----------------

Telecommunications machines are flexible and can adapt to structure
changes, and they are otherwise immortal to mundane errors and crashes.
However, in the event of a catastrophe such as an explosion,
singularity, or anything of the like the default warranty becomes void
and the machines will probably be destroyed or totaled. If one or more
machines are destroyed, chances are the entire communication grid or at
least part of it will be down. While intercoms and station bounced
radios are capable of limited non-subspace communication it is most
definitely not reliable. It should be maximum priority to get those
machines up again.

If you suspect the machines aren't working properly (or at all), you
should identify the cause first. Probably the most common issue is an
exploded central compartment. Repair any structural damage and assess
the machines. If they're still on (flashing/blinking lights, etc) then
they are relatively functional. If there's been some atmospheric
depressurization you're going to want to pump supercooled air into room;
the machines need cold gas to survive or they will not be able to
diffuse their heat into the environment, and will overheat.

![The multitool-telecomm
interface.](MultiTool-Telecommunications.png "fig:The multitool-telecomm interface.")
If the machines have been overheated, you can fix them by simply
reconstructing them. To do this, first unfasten the exterior bolts with
a screwdriver. Next, dislodge the plating with a wrench. Next, remove
the internal cables with some wirecutters. After that, you can use a
crowbar to remove the internal components and circuit board. From there,
you can either deconstruct the empty frame or simply rebuild it. If the
machines have been completely destroyed, you're going to want to build
more. You're going to have to bug R&D for some really high-tier circuit
boards and stock parts, or salvage some parts from other toasted
telecomm machines. Keep in mind, you don't have to reconstruct ALL the
machines. At the very minimum you need 1 receiver, 1 processor, 1
server, and 1 broadcaster.

Telecommunication Polymorphism
------------------------------

The machines can be retrofitted manually to work with other machines
that normally would not be very common or wise. In the case of an
emergency, however, it can be a life-saver. You can use a multitool to
interface with telecommunication machines, which will allow you to
modify some of the machines' properties. You can also link together
machines with this interface, which is possibly the most important
function.

In order to link two machines, access one of them with your multitool.
Select \[Add Machine\] at the bottom of the window to store this machine
in the buffer of the multitool. Now access the other machine with the
same multitool. The machine previously buffered should still be in the
buffer of the multitool. Select \[Link\] to add the machine currently
buffered to the list of machine links of the machine currently accessed.
This will establish a link between these two machines. (Note that it is
possible to link a machine to itself; this is both harmless and
pointless.)

### Subspace Receivers

You can link Subspace Receivers to *Processor Units* if you are unable
to link to a functional bus mainframe. This can and will create
substantial network lag, because Bus Mainframes are needed for rapid
information transferring and advanced port configurations.

### Bus Mainframes

You can link Bus Mainframes to *Subspace Broadcasters* if you are unable
to link to a functional server. This will not have much of an effect
besides a very miniscule performance decrease.

If you do not link to a Processor Unit, signals' readability will suffer
substantially. It will also make it impossible to directly link to
broadcasters.

### Processor Units

You can link Processor Units to *Telecommunication Servers* if you are
unable to link to Bus Mainframes. This will naturally have a significant
performance cost.

### Telecommunication Servers

These cannot really be linked to anything else other than a broadcaster.
They are only needed to store logs and maintain sane bookkeeping.

### Subspace Broadcasters

These are essential if you want an output. There is nothing you can do
with these in terms of polymorphism.

Radio Silence
-------------

A useful traitor tactic to either stop your target using the radio, or
luring the [Chief Engineer](/wiki/Chief_Engineer "wikilink") to the area. Here
are some easy ways to make nobody hear the screams of the station.

1.Turn off the coolers. If you read the rest of this post then you know
that these machines overheat without the freezer running.

2.Destroy the sub-space broadcaster. Those screams will be uttered, But
not heard.

3.Deconstruct the processor. This makes the radio blast gibberish that
nobody can comprehend.

4.Deconstruct the server. Depending on which ones you knock out, you can
disable most of the command channels and such.
