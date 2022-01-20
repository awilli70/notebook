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
- Gain exposure to research
- Get experience in modern debugging
- Fun?
Module 1: Distributed systems review
          Current debugging tools

Module 2: Emerging cloud architectures
          Techniques to understand/debug

Discussions - 1 paper per week
              One group presents summary
              Next reads summaries & presents critical analysis of paper

Projects - projects posted and ranked, and then select project groups (some projects will have external mentors!)
