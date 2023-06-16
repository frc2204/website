---
layout: post
title:  "Midweek Build Team Mentor Update"
date:   2023-03-08 00:00:00 -0700
categories: mentors
author: James Ding
---
# Accomplishments and Roadblocks

## Fabrication

Arm has been verified to work with minimal power settings (movements with ~10% motor power are slow, stable, and smooth), both joints have full range of motion. We have ran tests with ~60% motor power which has shown to be sufficient to quickly move the arm about effectively.

First Joint Test at ~20%

Regarding chain tensioning, Mr. Shen has pointed out how a removal of a link (and therefore replacing it with a half link) allows for the chain to sit tightly for 2 out of 3 chains. For chain tensioners, we may opt for some bicycle-style ones off Amazon.

## Electrical

SparkMax’s have been wired up. Onboard pneumatics now has the compressor, air tank, and pneumatic hub wired up.

## CAD

### Claw

Jeremey has finalized the CAD for the claw, however some further changes will be needed to be made to improve the design. Some improvements that were pointed out would include having a fixed piston (the previous piston could move around freely), eliminating the spring/hinge design fragile), as well as addressing issues pertaining to overextending

James has redesigned the claw:

The redesign utilizes TPU as a compliant material that can be printed on Sam's 3D printer. The design also includes the 2x1 Rev MaxTube as support and an ABS adapter for the 3x3" holes on the arm. Furthermore, a limelight will be included on the camera to aid the driver in aligning with cones on the field.

### Arm

We found a 1”x1”x36” L bracket that may be used in addition with a horizontal plate to support the arm and prevent twisting.

### Swerve

Covers for the Swerve and CANCoders have roughly been finalized and will be 3D printed

## Programming

Programming has begun writing the `ArmSubsystem` which will incorporate PID controllers with GravityFeedForward (maybe? I would need to see if I have enough time to tune kV, kG, and kA). The goal is to currently have `setPosition()` functions to be finished, so creating presents will be a matter of tuning some constant fields.

Currently there are some Odometry scaling issues… odometry may not be a go for this season. I’ll try to get a temporary fix to “rescale” autonomous driving. All of this is in the air however until fabrication can be done.

After this, auto-balance would be the goal. No idea if we would have enough time for that though.

NavX is being weird too, we’ll just be sticking to the ADIS1670 as our primary gyroscope.

# Next Steps

Robot weight could be a concern this year, so far the robot weights approximately ~100lbs (jankily weighed with a bathroom scale). We will attempt to get an accurate reading of the weight for the robot this year, hopefully this weekend.

James will finalize the structural support structure for arms to minimize twisting or other undesirable motions. The DXF’s should be done by this Wednesday or latest by this Thursday, so Mr. Gin can cut the remaining metal.

Find better spot to mount Limelight, or create roll cage for Limelight. Probably will go with the first though.