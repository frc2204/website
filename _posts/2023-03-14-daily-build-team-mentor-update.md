---
layout: post
title:  "Daily Build Team Mentor Update"
date:   2023-03-14 00:00:00 -0700
categories: mentors
author: James Ding
---


# Accomplishments and Road Blocks

## Electrical

Currently, the Rev Pneumatics Hub is having issues with powering the compressor. We’ve decided to swap it out for the PCM from CTRE for now.

## Fabrication

### RSL

“*Hey it got mounted, we can be more safe now!”*

### Bumpers

To my knowledge so far, Titus has finished cutting the angled brackets and is very close to being finished with mounting the bumpers.

### Third Joint

The third joint has been laser cut, and has been verified to fit within starting configurations.

### Chain tensioner

Chain tensioner has been installed, the only thing missing is a proper spring mount to further tension the chain - another tensioner has been ordered as this tensioner is easily mountable to our arms.

## CAD

### Joint Positioning

Arm starting configuration

Fully extended

Partial extension

Because the arm has a 5x3 1” pattern for mounting, while the arm has a 3x3 1” pattern. On the CAD, the claw is mounted to the pattern closest to the outside. Having an extra 2” of adjustability will allow us to compensate for bumper thickness, etc.

### Third Joint Spacers

The large spacer highlighted has an angled wedge to contact the limit switch on the second joint for homing and safety. The bottom spacer is just a normal spacer.

### Claw Piston Retention

A retention clip to prevent the piston from moving wildly has just been designed, but will need testing to ensure it actually works. Will provide updates later.

## Programming

After some code review, it appears that the homing command could have the possibility of occurring concurrently with a given position command, which could lead to stability issues (doubt it though). While this issue is already mitigated in our custom homing library via the `HomingState` enumeration class unique to each `HomingNEOSparkMax` instance, it is better to address this issue from the `CommandScheduler` level and prevent the command from being queued within the first place. Not the highest priority at the moment, though.

# Next Steps

## Electrical

Finish wiring PCM, Limelight, and Limit switches. Currently, we are waiting for a 20’ L ethernet cable from Amazon to arrive to network the claw. We may just supply power to the Limelight via POE too to reduce the amount of cable management

## Fabrication

Mounting all the components and just integration hell.

## Programming

Announce driver deadlines and figure out who’s driving the robot. Autonomous and tuning still TBD.

## CAD

James will confirm with Mr. Gin about having the revised third joint plates fabricated. Additionally, James will need to design the second joint homing limit switch mechanism as well as polycarbonate protection/sponsors plates so they can be fabricated.

In order to mount the polycarbonate protection, there most likely will be a need to print standoffs, TBD.

Thank you mentors for your dedication towards the team!

## Friday Late Meeting

This Friday, we will be having an extended meeting from 3:45-11pm. Mr. Sam will be supervising us from 6-11pm. Mentors, feel free to attend if it works with your schedule. I’ll be posting something in the discord to get dinner options hopefully sorted out?