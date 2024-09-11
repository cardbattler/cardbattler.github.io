---
layout: post
title:  "Patch Notes - v0.6.0"
date:   2024-07-13
categories: patch-notes
author: 
---

Its been almost 3 months since our last patch. For a lot of that we've been working on more business related things behind the scenes, but that didn't stop us from producing one doozy of a patch that we are thrilled about.

One of the massive achievements of this patch is that we finally have our new background properly implemented in all its glory. We had static versions of this art in previous patches, but this is the first time we've brought together all of Jeff's incredible artwork with Antourenein's technical art wizardry.

But that's not all when it comes to visuals! We also have vfx for entering and exiting the field, brand new hex highlights, and some experimental hex texturing that can be changed in the settings.

This patch is also a huge step in the right direction for making Constelleum as accessible as possible. New color, size, and input related settings have been added throughout the game. Mitch was just having some fun playing Constelleum with a dance pad this past week,

We've also added new setting presets in Accessibility for increasing the size of everything or the color palette. This should make it easier than ever to quickly adjust the game to your needs. We're still always improving these features to make them as comprehensive and powerful as possible. If you experience any issues please report them so we can continue to improve our accessibility offering.

There's so much more to unpack: cinematic camera, new lobby settings, an experimental mac build, but the last thing we'll leave you before the bullets is that we've added a new character Druid to the game! Druid is still in early stages of gameplay and lore development and may leave for a short while, but we are super excited for you to meet this new character and explore their mechanics. We'll dive into them a little deeper in the future when they are fully realized.

## Ecosystem

* New Experimental Mac Build

## Gameplay

* Druid has been introduced in an early form. They come with a new status called Rot that can lead to the defeat of opponents
* Water obstacle was changed to apply clumsy

## Art

* Fully realized background art of the 3 worlds created by Jeff and brought to life by Antourenein
* VFX for entry and exit onto the field
* New experimental hex grid textures that can be selected in Accessibility -> Field settings

## UI/UX

* New hex highlights
* New lobby settings for banning characters or using queue modes to get easy default settings
* Players that aren't the lobby owner can now see the current settings
* Added cinematic camera settings that can be changed under Camera. These are on by default
* Added cinematic camera settings as easily available in sandbox tools and added a reset round button to make it easier than ever to quickly try things out
* Settings can now be copy and pasted to quickly share with friends. They copy the highest visible level of settings or all if nothing is selected
* Preset profiles for UI size and color palette are now available to make it simple to get the settings you need
* Color settings now have a floor on their alpha level
* Individual colors can be copied and pasted
* Added new settings for color adjustment for a wide range of UI especially related to the HUD and Field
* Added new size settings especially related to the HUD and Field
* Added setting for the debounce time when using the double select to submit selection setting
* Added settings for the display duration for the phase overlay under Accessibility -> HUD (the banner that says when to pick a card, etc)
* Added settings for hiding unwanted HUD elements
* Added slight delay after a controller passes focus for the first time (this helps prevent overshooting the item you want to focus)
* Added focus related settings under Input to help with controller usage and require less input

## Bug Fixes

* Fixed a whole bunch of broken layout issues when using higher than default UI sizes
* Fixed issue with resetting settings in Accessibility -> Menu
* Fixed backward ping setting
* Fixed saving a deck and then trying to use it requiring relaunching
* Fixed submit button's use of character names
* Fixed issue with defeating dummy in defeat tutorial
* Fixed issue with ghost pawns flickering when rebuilding a move path
* Fixed animation bug when dragging over orbs or obstacles
* Fixed issue with controller based input remapping not recognizing the input type correctly and therefore causing issues when saving settings
* Fixed orbs disappearing at the wrong time
* Fixed disrupt reactions queueing and being poorly timed when something like getting pushed over multiple disrupting obstacles occurred
* Fixed issue with settings sliders being able to overshoot their minimum and maximum values when using focus based change
