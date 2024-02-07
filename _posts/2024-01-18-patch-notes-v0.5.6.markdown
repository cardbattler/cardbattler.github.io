---
layout: post
title:  "Patch Notes - v0.5.6"
date:   2024-01-18
categories: patches,devlog
---

Hey folks we've got an update chocked full of goodies for you this week. You can read more about the high-level big new features below or skip to the bulleted lists below,

Meet Sayyora, the newest addition to the Constelleum cast! She is a traveling prosthetist who gains a "Rambling" resource with each space she moves on the field. This resource counter affects when and how she can collect orbs and score, and also enhances several of her cards. She was inspired by the Rambler prototype character, but she is fully unique with reworked mechanics and full art/vfx. She is still movement focused with exceptional positioning options, but her "Rambling" status resource management is now much more interactive and will remain an important consideration throughout the entire game instead of just the first and last round. Her cards also have some creative new uses of old mechanics, so expect novel gameplay beyond her Rambling status! We hope you have fun with this new character. To learn more, check out Sayyora in the Deck Builder and Sandbox.

A ton of work this patch went into making the game fully playable via focus. All while trying to make sure that as little functionality as possible was lost when not using a mouse. This means that everything can be traversed and activated with a keyboard. There were some interesting technical challenges with getting the UI to play nicely with the hexagons and to making sure tooltips worked whether you hover something or focus it.

This work will go a long way towards our goals of being playable with almost any input scheme imaginable which has already born fruit because Constelleum now also supports controllers! This does come with a caveat as Steam's built in input system collides with the one we use in our game. For the time being if you want to use a controller you need to go to Steam -> Settings -> Controller and disable the feature for your controller type. We are already investigating solutions for this and will come up with a full fix in the future.

Lastly we added some automated data recording so that we can more easily analyze the numbers behind the gameplay and move towards fine tuning the game. This may not sound big, but being able to have easily accessible information about how much disrupt characters are doing or when people are running out of time will all be incredibly valuable for future work.

And that's all the "big" stuff this patch, but there's more great stuff below too! Please report any bugs you find with these new features so that we can continue to iterate on them and make them as good as they can be.

Wishing you a happy new year from the Constelleum team!

## Gameplay

* Rambler added to the game now known as Sayyora with brand new cards, reworked old cards, and fully implemented character art with animations and vfx

## Art

* Awali got his updated animations with a whole bunch of cool vfx
* Selene has her new base animations, vfx still to come
* Gnamma has her new base animations, vfx still to come

## UI/UX

* The game is now playable with just keyboard through a suite of focus improvements
* Constelleum now supports controllers. See the above paragraphs for a note about a known issue with Steam Input
* The round history display now behaves more like a popup that closes like normal popups

## Backend

* Added some automated data collection from matches
* We worked on the reconnect functionality to hopefully improve the ease of reconnecting
