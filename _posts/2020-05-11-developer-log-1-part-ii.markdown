---
layout: post
title:  "Developer Log 1 - Part II"
date:   2020-05-11
categories: devlog
author: Matt Cotter
---

## Starting Positions and Where to Find Them

One thing I worked on this week was adding a new game phase
for players to select their starting positions.
Previously, starting positions existed in a predefined list,
and they were assigned to players on a first-come-first-serve basis
upon character selection.
When you started the game, you were placed somewhere on the field
with no explanation—maybe near friends and maybe near foes.

Our new implementation is to instead
define an area of possible starting positions by team,
then have players choose their individual starting positions from this area.
This allows more control, more visibility, and a new element of strategy.

The starting position draft phase begins
when everyone has selected their characters.
All possible starting positions are sent to everyone,
and players must decide where in a highlighted area they want to pick.
Clicking / keyboard-navigating to a tile will move your character icon
to the tile both locally and for all teammates.
(This was the first place in our server with an RPC
to all players on one team and not the other; progress!)
Here is a screenshot of this process<!--end_excerpt-->:


<figure>
    <img
        src="{{site.baseurl}}/assets/images/2020-05-11-developer-log-1/8hfn2-ivD26z4IFfR8mhHh55Jfxgvny9D2_-LmWu8IMpWjG6qowPKKrufVJA81erMU4ynh6s0gGXQUVeLdVSkbqdC69CznWtgfSm.png"
        alt="Starting position hexagons are highlighted. 2 characters have been tentatively placed."
    >
</figure>

To prevent overlap between player’s selections, the server is the arbiter of all position choices. To save a round trip to the server, the clients use an optimistic concurrency control where they update locally assuming no conflicts but are able to roll back to an open position if the server indicates that the user choice was invalid. Once a player confirms their starting location, the tile is unhighlighted as an indication to teammates.

<figure>
    <img
        src="{{site.baseurl}}/assets/images/2020-05-11-developer-log-1/bIoz62zYmjd7FW1tJynPlQlTmlVk-xCRTiYDW3OEmn7Cu1jkfg1kAcQ5juHp_kYdDf9u3C2H0eOSadY2cU8OgumK-XE_l2jdgJsd.png"
        alt="Starting position hexagons are highlighted. One player has submitted their position and the hexagon unhighlighted."
    >
</figure>

Once the whole team is locked in, all tiles are unhighlighted. When all players have selected their starting positions, players from the opposing team appear on the field, and the game starts!

To facilitate this new starting position draft, I also made a few updates to our internal map editor tool to easily define the starting position areas for both teams. This tool had been broken since we added the obstacle system, so my work on it turned into a big update/refactor. A nice byproduct of that work is that we now have a library of obstacles that we can place in any space on the field with a simple dropdown. Here’s how it looks:

<figure>
    <img
        src="{{site.baseurl}}/assets/images/2020-05-11-developer-log-1/maptool.gif"
        alt="Clicks and highlights hexagons before adding the wall obstacle from a drop-down."
    >
</figure>
