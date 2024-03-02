---
title: Board Manager
author: Steve_Mutter
lang: en
weight: 4
draft: false
---

# Status Bar

![BM Status Bar](/how-to-play/images/StatusBar.png)

## Status
connection state of the Board Manager is shown. 
Possible values: </br>
- Connected </br>
- Disconnected

## Client Version
Actual Version of your Client (Board Manager)

## FPS Lock
Frames per second defined in the configuration of your Board Manager

## FPS Cams
Frames per second of your cameras individually

## Resolution
Resolution defined in the configuration of your Board Manager

## Board State
Actual State of the Board. Possible Values: </br>
- Throw (Board awaits Darts for Detection) </br>
- Throw detected (Board Manager detected a Dart) </br>
- Takeout (Board finished detection of 3 Darts) </br>
- Takeout started (Board recognized Hand) </br>
- Takeout finished (Takeout finished successfully)


## Detection State
These Values are for better Debugging if there are problems with the detection or takeout
- Wait (awating Darts) </br>
- Stable (Images are stable) </br>
- Empty (Board is emtpy) </br>
- Dart (Dart detected) </br>
- Hand (Hand detected) </br>
- Partial Takeout (Takeout is not finished) </br>
- Takeout (Takeout is in progress) </br>


## Board Manager Controls
- Start / Stop (Start or Stop the Board Manager) </br>
- Reset (Reset the Board Manager) </br>
- Connect / Disconnect (Connect of Disconnect the Board Manager)


## Counted Darts
Values of detected Darts
