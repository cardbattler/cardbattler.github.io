---
layout: post
title:  "Patch Notes - v0.6.1"
date:   2024-09-10
categories: patch-notes
author: Constelleum Team
---

We have a relatively light set of notes for you with this patch. There was a lot of background programming work done building towards something big that we're not ready to talk about, but we also found some time to add some nice new visual effects and fix some recent bugs

## Art

* Added vfx for picking up orbs
* Added vfx for scoring a goal

## UI/UX

* Brought back character outlines in an initial form. More work is being done to restore old functionality

## Gameplay

* Added a setting under Gameplay that allows environment characters in the sandbox to take turns

## Ecosystem

* Updated to Godot 4.3
* Further upgraded our automated test suite to make it easier for us to find pesky bugs in multiplayer games
* Worked on some tech debt to pave the road for something big coming in the future

## Bug Fixes

* Fixed controller mappings only working for the device that made the mapping and therefore only one device at a time
* Fixed broken orb tooltips
* Fixed the Drag action not showing modification from movement statuses
* Fixed edit settings button showing up for non lobby owners
* Fixed character select sidebar expanding off screen
* Card discard and therefore refresh effects now uniformly happen before turn end effects
