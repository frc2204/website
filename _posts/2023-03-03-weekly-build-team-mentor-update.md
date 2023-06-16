---
layout: post
title:  "Weekly Build Team Mentor Update"
date:   2023-03-03 00:00:00 -0700
categories: mentors
author: James Ding
---

# Accomplishments and Road Blocks

## Fabrication

Limelight installed with 3D printed attachment, holes drilled on 2/3 sprockets, and

## Electrical

Limelight has been wired up. However, there seems to be some intermittent issues with the CANCoders (too much heat applied to them?). Electrical team will most likely be upgrading their soldering station with a Hakko and practicing through-hole soldering. Additionally, there will be a purchase made for backup CANCoders.

## Programming

Programming has switched from pure odometry to the use of a SwerveDrivePoseEstimator, which uses a Unscented [Kalman Filter](https://docs.wpilib.org/en/stable/docs/software/advanced-controls/state-space/state-space-observers.html#kalman-filters) to compensate the latency between Limelight and robot location.

## CAD

Jeremey is working on finalizing the claw CAD by this week.

Limelight cover was finished with the Ultimaker.

# Next Steps/Saturday Briefing

## Fabrication

Fabrication will need to finish building the first joint (sprocket assembly, etc.) next Saturday, so that the first joint is able to move freely. Additionally, Titus will be in charge of bumpers (which should be done within the next week)

## Electrical

Eliminate reliability issues with CAN Bus, whether that be securing connections or resoldering.

## Programming

### Arm

Implement Gravity-Based FeedForward + PID control for the first joint. James will talk to Mrs. Connie Fong about inverse kinematics using the Jacobian Inverse Matrix. If inverse kinematics becomes too complicated, we will just be using presents with minute corrections.

### Drive Train

Add SlewRateLimiters to $x,y, \theta$ axis on the robot. Test autonomous routines

## CAD

Must finalize claw by the end of this week. Finalize swerve drive covers with CANCoder protection. Add RSL mount.
