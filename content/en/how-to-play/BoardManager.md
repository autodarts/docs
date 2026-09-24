---
title: Board Manager
author: Steve_Mutter
lang: en
weight: 4
draft: false
---

{{<hint type=warning icon=gdoc_error_outline >}}
**Earlier versions only.** Board Manager is the browser interface of Autodarts 0.x and is not supported from version 2 on. In version 2, everything it did is in the [Autodarts Desktop](/Autodarts-Desktop/) window, or on the `autodarts` terminal screen of a headless install (see [Installation](/getting-started/installation/)).
{{< /hint >}}

# Open Board Manager

To open the Board Manager, go to your Boards on https://play.autodarts.com and select the 'Board Manager' icon on your board’s tile. The marked icon in the image shows exactly where to click.

{{< figure src="/how-to-play/images/boards_bm_nav.jpeg" width="500px" alt="Open Board Manager" >}}

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
- Wait (awaiting Darts) </br>
- Stable (Images are stable) </br>
- Empty (Board is empty) </br>
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
