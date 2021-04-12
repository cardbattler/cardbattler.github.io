---
layout: post
title:  "Developer Log 4"
date:   2020-05-21
categories: devlog
---

#### Bugs and Bugs and Bugs, Oh My! - Alex

Our first playtest in mid-April revealed nasty bugs already present in our still simple game. Players reported crashes when viewing their own hands on other player’s turns, starting positions were determined based on connection order instead of team (A feature -Mitch), and attacks that were not meant to deal damage could be buffed to deal damage. The bugs were fantastic to see and fascinating to squash, because they drew us deeper into the very powerful Godot engine.

Matt posted last week on how he implemented a Starting Position Phase to fix the initial violation of personal space.

![Two players starting next to one from the opposing team with the words fancy meeting you here.](https://cdn.discordapp.com/attachments/575192288951533571/711812751218966569/fancy_meeting.png)

<!--end_excerpt-->

This week, Mitch and I went after crashes, odd interactions, and other bugs that surfaced since the playtest. We did not (and probably still don’t) fully understand childing and how nodes could be modified before entering the scene tree. If one player was viewing their hand at the end of another player’s turn, the server updated the hand viewer’s unchilded battlefield view, which crashed their game. To remedy this, the battlefield is now persistent and the handview is overlaid. The general user interface (UI) still needs tidying. Time and resources permitting, an option will be included to show a quick animation to display the hand.

To fix buffing zero strength attacks, we added a new action, “Apply Status,” which adds statuses to the target without referencing health. Direct application of statuses adds a lot of flexibility to utility focused cards.

#### The Great Word Exchange - Alex

The words that are chosen to describe a game are important. They paint a picture before anything even starts moving, a theater of the mind strengthened by the following visuals. Because this game is about a sport-like competition rather than gladiatorial combat, we knew we wanted to stay away from words that implied death, e.g. poisoned, attack, killed. And there is language that has become a staple of the fantasy genre. A balance was struck between language that new players may recognize from role playing games, avoiding using tropes as a crutch, and inviting all players to a unique and complex world.

![Fast scroll of all of the vocabulary in the game.](https://cdn.discordapp.com/attachments/575192288951533571/711812758802268200/vocab_list.gif)

A list of all terms currently used in the game was compiled, shown above. The list was gone through term by term, each being weighed and measured to decide if it developed or distracted from an intended theme of intense yet healthy competition. This was a surprisingly lengthy process but yielded lore-backed justifications for how in a setting of war, death, and pain the Constelleum remains a place of playful contest.

![New cut-out animation style Grappler walking away rubbing his stomach.](https://cdn.discordapp.com/attachments/575192288951533571/711812755149029456/flow_off_to_lunch.gif)

Grappler is off to lunch for now, but he will be back next week to show what we have learned about Godot’s rigging and animation features!
