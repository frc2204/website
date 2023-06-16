---
layout: post
title:  "Midweek Build Team Mentor Update"
date:   2023-02-22 00:00:00 -0700
categories: mentors
author: James Ding
---
# Accomplishments and Road Blocks

Swerve drive works

## Electrical

Electrical has finished wiring up the temporary electrical board as well as troubleshooting issues with the CANCoders. A basic cable management cutout has also been created by electrical team

## Fabrication

Fabrication has begun cutting more metal for the chassis, as well as beginning to prepare raw parts for assembly as well as cutting from Mr. Gin. Last Saturday, Raymond (Sam) had cut the aluminum sheet metal and gave them to Mr. Gin. Additionally, the parts from McMaster Carr have been placed and will expect to be delivered this Friday.

## CAD

CAD has made some final tweaks to the CAD model of the robot. James has sent a email to Mr. Gin requesting for final opinions on the CAD before we begin laser cutting the sheet metal.

## Programming

Swerve drive, teleoperated control has been tested and configured properly. A few road blocks that we ran along the way included incorrect kinematic configurations, PID tuning, and odometry issues. The robot was accidentally set to 23ft.x23in, instead of the 23in.x23in., which resulted in proper translational movement but incorrect rotational movement. This issue has since been resolve and fixed.

Currently the only issue is with the odometry, which results in what seems like overscaled units, but have not been confirmed.

# Next Steps

## Electrical

Electrical has begun fixing soldering joints on the CANCoders as well as crimping PWM-style connectors for CAN bus. Once the robot base plates are laser cut, electrical will begin wiring up the base of the chassis.

## Fabrication/CAD

CAD will begin considering the polycarbonate cover for the robot, as well as designing and laser-cutting wood drill-hole patterns for fabrication to use, which Mr. Sam has suggested in doing.

## Programming

Programming will begin working on integrating MegaTag (AprilTag based localization) with odometry, which will begin providing real-time synchronization and updates for the robot position relative to the field.

Additionally, programming team will begin working and configuring autonomous trajectory values.

Once the robot arm and claw mechanisms have been built, programming will begin to need to consider how the arm will be positioned. 