---
layout: post
title:  "Weekly Build Team Mentor Update"
date:   2023-03-18 00:00:00 -0700
categories: mentors
author: James Ding
---

# Accomplishments and Road Blocks

## Electrical

Crimped and troubleshooted issues with the ethernet cable leading to the second limelight. The second limelight was originally receiving power, but no data. The issue has been resolved

## Fabrication

### Motors

Fabrication team along with electrical team were able to fix issues with slipping gearboxes by reapplying grease as well as placing spacers to prevent keys from falling out. Additionally, the 1:60 ratio 1:20 were swapped, the current configuration being the 1:20 (total 1:100 after sprocket) for the first joint and 1:60 (1:200) for the second joint.

### Cable Guard

Cable guard was added to the the Pneumatic tubing as well as ethernet cable going to the claw.

### LED Strips

The robot now has LED strips to give visual feedback to the drivers about the current state of the robot

## CAD

CAD should almost be done - I was able to design a couple parts to mount the polycarbonate plate while not interfering with bumper mounts.

## Programming

### Arm Positioning

During some testing on Saturday, we’ve found suitable PID values for the arm. Apparently there is no need for the integral and derivative terms - the proportional term by itself is suitable enough. This form of control, along with a `SlewRateLimiter`, should result in rather smooth and stable control of the arm.

I’m also beginning to question the practicality of having a homing mechanism. Tests that were run on Friday did not use a homing mechanism. We shall see.

The position command was changed from having multiple instances of a `Command` running and managing them through WPILib’s native `CommandScheduler` singleton, to one continuous command polling a position present.

See commits:

[c61467ec8e2f850b0422ce558da8bc69bc3abd16](https://github.com/FRC2204-Rambots/frc-2023/commit/c61467ec8e2f850b0422ce558da8bc69bc3abd16)

[9d6cc52efba7dfa296f982f05448dfcd93d76a54](https://github.com/FRC2204-Rambots/frc-2023/commit/9d6cc52efba7dfa296f982f05448dfcd93d76a54)

### Swerve Drive Odometry

An bug was discovered with how each `SwerveModule` reported their position. The getter function for the `position` attribute was converting native falcon units to meters per second instead of just meters.

See commit:
[88b2648d813e82188ab94abd57349911528cdd42](https://github.com/FRC2204-Rambots/frc-2023/commit/88b2648d813e82188ab94abd57349911528cdd42)

### Swerve Module Full 360 Initialization Issue

A solution was found online for an issue where swerve modules made a full 360 as a result of a negative absolute encoder value due to a race condition from motor/encoder initialization. While a fix for this race condition isn’t solved, a solution that was implemented was to force the values of the encoder to be positive, as highlighted in the `CTREModuleState` object

See commit: [572e2109bdaba7dae9714c1cf879b19ccacf76ae](https://github.com/FRC2204-Rambots/frc-2023/commit/572e2109bdaba7dae9714c1cf879b19ccacf76ae)

See the ChiefDelphi post where this issue was highlighted and solved:

[Swerve Modules Rotate Upon First Enable](https://www.chiefdelphi.com/t/swerve-modules-rotate-upon-first-enable/426785/24)

### Claw Opening and Closing Commands

Two commands were created to open and close the command, which are single use commands bound to the left and right bumpers on the Xbox Controller

See commit: [535a5d6a9133dc501eeda8abfc33bde0569045c2](https://github.com/FRC2204-Rambots/frc-2023/commit/535a5d6a9133dc501eeda8abfc33bde0569045c2)

### LED Control

We began using Rev’s Blinkin LED controller to control LED strips. In order to interface with the Blinkin, the Enum class `BlinkinPattern` was created to translate patterns to Spark values [-0.99, 0.99] according to Blinkin Driver Documentation.

To have full control over the LED controller, we extended the `Spark` class and overrode the `stop` and `disabled` methods to maintain control of the LED controller even when the robot is disabled. This feature can then be used to quickly recognize issues with the robot (for example, if any CAN devices are missing, the LED’s can turn red). This feature is yet to be implemented.

See commit: [a421239bb57d065a14b6ed46ff75100a0cb89b49](https://github.com/FRC2204-Rambots/frc-2023/commit/a421239bb57d065a14b6ed46ff75100a0cb89b49)

### Pose Estimation with Unfiltered Kalman Filters

Re-enabled the Limelight to process positions from AprilTags, which will be run through an UKF with generic standard deviations.

See WPILib docs:

[State Observers and Kalman Filters](https://docs.wpilib.org/en/stable/docs/software/advanced-controls/state-space/state-space-observers.html)

[Pose Estimators](https://docs.wpilib.org/en/stable/docs/software/advanced-controls/state-space/state-space-pose-estimators.html)

See commit: [24400a61ffaaf0f45bb3aeead89615cb65731d66](https://github.com/FRC2204-Rambots/frc-2023/commit/24400a61ffaaf0f45bb3aeead89615cb65731d66)

### Repository Link

[frc-2023](https://github.com/FRC2204-Rambots/frc-2023)

# Next Steps

## Fabrication

The existing cart for the robot will need to be modified, which include modifying the block configuration as well as shortening the height

## Programming

### Autonomous & Odometry

After odometry issue was solved (https://github.com/FRC2204-Rambots/frc-2023/commit/88b2648d813e82188ab94abd57349911528cdd42), the next goal is to test autonomous routines and just general odometry

If possible I would like to have auto-snapping to quickly position the robot in positions for scoring

Auto-balance is currently on the low end of my priority list, if odometry works well I might as well just go with no PID logic and straight up positioning with pose estimation to be honest.

### Pose Estimation

Confirm whether the UKF standard deviations are suitable to use on the field and adjust if necessary.

Adjust settings for the center of the Limelight.

### Presets

More presets and control mode options need to be explored and tested in following meetings

There’s alot more to practice and develop on the programming side and I will try to see what I can squeeze in before comp.