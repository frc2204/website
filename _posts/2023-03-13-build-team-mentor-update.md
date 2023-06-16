---
layout: post
title:  "Build Team Mentor Update"
date:   2023-03-13 00:00:00 -0700
categories: mentors
author: James Ding
---

I’ll be sending mentor updates daily (after each meeting) until competition as competition draws near

# Accomplishments and Road Blocks

## Fabrication

### Chain Tensioners

Fabrication is having a bit of trouble mounting a chain tensioner to the arm - more news to come about that.

### Claw

✅ Tests with the piston have proven it to be successful with pressure ranging from 30-40psi.

The full metal assembly of the claw has been built (with what has been 3D printed so far), however there are still many improvements to be designed and made, such as a piston guard mechanism which prevents the piston from excessively moving on perpendicular from where it extends.

We should consider grip tape and a slight modification of the shape of the grippers.

### Bumpers

Titus is nearly finished with Bumpers, all that remains is getting the corners done.

Something to note is that the number positioning and count is different for the blue and red bumpers as they accidently placed one set of numbers on the inner side of the cloth.

## CAD

Whole robot CAD images

Robot by itself

Robot relative to cone station

### Arm

The third joint is currently too long to to properly fit within the starting configuration by roughly a foot. This is because James didn’t take into account the length of the claw when designing the arm, welp. A shorter version has been designed to take this into account.

Side view of shortened third joint

Top view of shortened third joint

I have tested this within Fusion and it meets all legal starting configuration requirements.

### Homing Mechanisms

The homing mechanism for the third joint has been designed and 3D printed, and the limit switch has been mounted. All that remains is mounting it to the support plate and wiring

Side view of limit switch relative to robot

Top view of limit switch

Bottom view of limit switch

The other homing joint is still in progress - will try to get this done tomorrow.

### Chain Guards

Designed one set of chain guards, currently in queue for printing

Inner view

Outer view

## Programming

### Homing Code

Within the past week, a wrapper library has been created for a `CANSparkMax` instance, with homing features and safety measures, located in `org.crosspointacademy.lib.control.homing`. This hasn’t been tested yet.

A command has also been created to handle requests to position the arm, implementing proper auto-cancelation and scheduling to ensure only one active command is being sent to the arm at any specific time.

[frc-2023/src/main/java/org/crosspointacademy/lib/control/homing at master · FRC2204-Rambots/frc-2023](https://github.com/FRC2204-Rambots/frc-2023/tree/master/src/main/java/org/crosspointacademy/lib/control/homing)

### Claw Code

We created a new file `ClawSubsystem` that contains one instance of the `PneumaticsHub`. More to come lol.

## All Changes

[Comparing 2ef435e22e8f...ca93aa71425b · FRC2204-Rambots/frc-2023](https://github.com/FRC2204-Rambots/frc-2023/compare/2ef435e22e8f...ca93aa71425b)

[Comparing ca93aa71425b...c6abe097cf87 · FRC2204-Rambots/frc-2023](https://github.com/FRC2204-Rambots/frc-2023/compare/ca93aa71425b...c6abe097cf87)

# Next Steps

## CAD & Fabrication

### Arm

On Tuesday’s meeting, new version of the third joint will be laser cut and mounted, and temporarily supported with L brackets. James will send the DXF files to Mr. Gin once it has been proven to be compatible with starting configuration and rules.

## Programming

### Homing and Tuning

Arm needs to be able to accurately home, PID values will need to be tuned properly to ensure safe and controlled movements of the arm.

### Autonomous Testing & Field Marking

To occur on Friday or Saturday in the Student Union?