# Class Notes 2022/01/20

## ED 01
* Lots of readings, writing (maybe PF?)
* Prof seems awesome
* Project
* Introductions!
  * Why? Personal experience and other experiences ground learning
  * Meeting others and seeing how people thought about schools
  * Most of us went to one highschool and assume that most highschools are similar
  * Get people to say something in class :)
  * Learning names (Steve-centric)
* Class policies
  * No cold calling, but participaite

ASSIGNMENT 1:
* Read things for Tuesday
* Paper 5-8 pages due Thursday

## CS 150 DCC
### What is this class about?

* Finding & analyzing bugs in distributed systems
* Debugging is twice as hard as writing a program - write clever code, you will not be able to debug it
* Computers are deterministic - why is debugging so hard?

### Cloud Computing overview
* Hardware/Software infra: datacenter
* One or more datacenters owned by same org: cloud
* cloud and apps by same org: private
* cloud and apps owned by different orgs: public
* Cloud ecosystem
  * Many datacenters, many layers, many distributed services, many parties
    * dcs: 100s of thousands
    * layers: guest OS, network
    * dist services: 1000s of nodes in clouds
    * parties: tenants, cloud providers

### What can go wrong?

* Application Layer - Poor performance due to bad hashing function (very difficult to debug)
* Virtualization Layer - Poor performance due to contention between to VMs
* Internet/ Network Layer - Apps cannot send data across clouds due to dropped packets
* Combined layers/ whole system - code was doing the right thing, but doesn't behave with other code

### How do clouds stay up?

* Hope things work or fix them on the fly
* High velocity debugging
* LOTS of money
AND THEY STILL DON'T WORK

### Overview - seminar course on techniques and tools
Why? 

* Gain exposure to research
* Get experience in modern debugging
* Fun?

Module 1: Distributed systems review, Current debugging tools

Module 2: Emerging cloud architectures, Techniques to understand/debug

Discussions - 1 paper per week

* One group presents summary
* Next reads summaries & presents critical analysis of paper

Projects - projects posted and ranked, and then select project groups (some projects will have external mentors!)

## PHIL 45
3 essays, grading adjusts if later essays are better

### Getting off the ground

There must be real questions to ask - why care?

* People seem to think that there's something paradoxical about mass-killing ethics, and end up having moral views on it (eg. killing prisoners, targeting civilians)
* If people actually believe that terrorism is only bad, then philosophically there is not much to address (there have to be live questions)
  * War bad (but what if in national self defense?) : predisposed to believe that people would take up arms anyway
* Institutions like West Point are discussing/ are intellectually engaged in these questions

Standard Just-War Theory vs Revisionist Theory vs Political Realism

* Just-War theorist - fundamental very important distinction between who is responsible and who can be targeted
  * Doesn't matter if you fighting for a just cause morally (for soldiers) - automatically justified as a soldier
  * Moral/ legal importance is fighting with the rules of war
  * Unjust wars are crimes, but impossible to criminalize (for world superpowers) - leadership supposed to bear the responsiblity, not the public at large or the soldiers

How could you believe (if you're enlisted and sent to fight in an unjust war) that it's ok to be fighting individuals who are only fighting to defend themselves from you? 

* Revisionist
  * The best a soldier has fighting in an unjust war is an excuse ("Good Citizen, Coerced")

* Political Realism/ Shock-and-Awe
  * Comply with the laws of war (legal not moral compliance)
  * Ok as long as civilians/ dedicated civilian infrastructure not targeted directly
  * Forsee that civilian infrastructure will be damaged, but this is the goal - cost to civilians without targeting
  * No ethics/ morality of war being considered whatsoever (legal doctrine)

### Hedges Reading

We start with torture. Why?

* It's a little bit of an aside, but it brings in the issues outside of morality, but gets political violence issues on the table
* Gets to the subject matter very quickly (provides an early exit point)

So lets get grounded before we get abstract.

* United States are usually at war, but the reasons are not compelling (homeland isn't really under attack)
* We don't appreciate what is being done to the other country, the collateral, the costs

Back to Just-War theory

* Collateral damage is unacknowledged, despite the high costs
* In fact, it is almost welcomed, because it's just seen as an inevitability
* We never need to hear about the cost to the opponent

Does leadership actually get held accountable? Nope

Terrorism bad, guerilla warfare good?

* Standard, war is between combatants, not civilians
* Really, how can one safely draw the distinction between the two?

Civilians support a war at it's start (~65%)

* Citizens should thus bear some responsibility BUT it's a small amount per individual


## CS 111 OS

### What is systems software? 

A: Software that provides services to help other software run (eg. operating systems, distributed systems, middleware, virt systems, cloud computing management)

What operating systems can you name? (Participation)

### Arduino vs. Raspberry Pi

* Arduino is a low power micro-controller, no gui
* Raspberry Pi can run an OS on top of it
* Arduino only loads one program at a time
* Raspberry Pi can run multiple programs, potentially at the same time (concurrency not parallelism)
* Arduino has no display capability, no usb
* Raspberry Pi has usb, ethernet, mini-hdmi, audio -- possible BECAUSE of operating system

### What does an OS do?

* Manage hardware resources
  * CPU, memory, I/O, etc
* Provide abstractions to applications
  * consistent interface to devices, files & directories, virtual machines

More specifically:

* extensibility (new drivers, etc)
* resource sharing
* security
* performance (Don't want to add too much overhead, take up too much memory)

### How an operating system acutally runs

Limited direct execution

* If it has an instruction to run, it directly executes it on the hardware

Discontinuities

* Direct execution is interrupted, either by HW (interrupt or exception)
* Interrupt
  1. Hardware throws interrupt/ exception
  2. OS handles input from I/O device (interrupt) or Processor (exception)
  3. OS runs code using direct execution, then resumes application (if still running) - Context Switch based upon interrupt, represent overhead to change what's being executed

* UNIX signals (application interacting with the OS [potentially for I/O])
  1. Application sends trap signal to switch from app to OS
  2. OS does something
  3. OS sends an upcall to the application, transfers execution back
  * In UNIX, app has signal handler

Internal/External - originates from on/ off the CPU

Synchronous/Asynchronous - occurs at a point in code, or happens at any point

|          	| Sync           	| Async     	|
|----------	|----------------	|-----------	|
| Internal 	| &nbsp;Trap/Exception 	|           	|
| External 	|                	| Interrupt 	|
