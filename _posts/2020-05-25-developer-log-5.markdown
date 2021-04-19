---
layout: post
title:  "Developer Log 5"
date:   2020-05-25
categories: devlog
---

#### Animation - Alex

This week Dev-Level animations were completed for the first three characters, Adrenaline, Flow, and The Elemantalist replacing Juggernaut, Grappler, and Archer. 

![Dev art Adrenaline tapping her foot and bobbing her axe above her shoulder.](https://cdn.discordapp.com/attachments/575192288951533571/714358323691913236/Adrenaline_Idle.gif.gif)![Dev art Flow holding onto his walking stick.](https://cdn.discordapp.com/attachments/575192288951533571/714358325487337522/flow_idle.gif)![Dev art Elementalist holding his hands in a spell casters pose at chest height.](https://cdn.discordapp.com/attachments/575192288951533571/714358321355685898/elementalist_idle.gif)
    
<!--end_excerpt-->
	
These are our first non-placeholder characters (though how they look will certainly improve.) These characters are why this game idea excited me so much when Mitch first proposed it. Each character has a completely unique interaction with their base mechanic, and a card library that is diverse enough to allow for multiple play styles beyond standard fantasy archetypes.

Following the Godot tutorial on cutout animation, some dev assets were quickly connected by a 2D skeleton. The previous pixel-style art was replaced by vector graphics, using the old graphics as a guide. By implementing inverse kinematic chains and some touch up by hand a result was achieved that almost conveys what might be happening. The assets are expected to improve considerably, but the idea is there. A graphic novel style is desired, and cut out animation services that feel well.
    
![Elementalist juggling icons representing fire, water, and earth](https://cdn.discordapp.com/attachments/575192288951533571/714353859308290058/elementalist_juggle.gif)

#### User Experience and Readability - Alex

While designing status effects, (that is, buffs and debuffs,) it became clear some statuses might confuse players if the statuses have multiple numbers. The current strength and/or duration system was also visually busy.

To solve this, statuses were redesigned in function and display. All statuses now have only one value associated with them which can be displayed largely and clearly. What the value represents will vary from status to status, but understanding the function of any statuses currently affecting a character is available via a hoverable tool-tip.
    
![Tooltip describing the status critically empowered.](https://cdn.discordapp.com/attachments/575192288951533571/714353850345062430/tooltip_example.png)

The status redesign also incorporates a critical-hit-ish mechanic that is enjoyed in various other fantasy role playing games. For example, a character that is Critically Empowered will break down a lot more Shields on their next Disrupt (attack) action.

An Action Tracker was also added. Previously, if a player was taking many actions on a card, it was not always clear which action they were currently taking. Now, on a player’s turn, the action they are taking is highlighted on the active card.
    
![Actions highlighting on a card as they are submitted.](https://cdn.discordapp.com/attachments/575192288951533571/714353854480777216/action_tracker_example.gif)
