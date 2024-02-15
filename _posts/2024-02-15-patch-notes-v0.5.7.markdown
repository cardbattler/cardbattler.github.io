---
layout: post
title:  "Patch Notes - v0.5.7"
date:   2024-02-15
categories: patches,devlog
---

We have a lot of exciting updates this month! Read the following paragraphs for details or jump to the bottom for a short bullet list summary.

In this patch, the animation queue got a lot of love! Now all movement and forced movement types have their own animations! Several characters have special Drag animations now, and Sayyora even has a Jumping animation. This also comes with improvements to the directions that pawns face. Everything is looking smooth and even more readable.

Speaking of animations, all of the pawns are now using our new animation and vfx system, and the game now has dynamic timing tweaks to normalize animation durations as well! We may need more tinkering to dial in timings, but already our longer animations are feeling more snappy.

In other art news, we have several new map backgrounds in the works that better fit the game's aesthetic and are focused on the World Beasts of Constelleum's lore. We are showcasing some new background concept art in this update as a teaser and to hear your thoughts.

We got a lot of great user feedback last month, and on top of bug fixes and some quality of life tweaks, we improved the UI for deck select. These updates will make it clear when you are waiting for other players to select decks and make the tutorial more intuitive.

And lastly, we have a few big gameplay changes in this update. First, Gimbal got some big improvements – check out the refinements to existing cards along with three new ones in deck builder! We hope you enjoy the new and improved Charge status and find creative ways to use it's Refresh and max value mechanics. Second, cards in your hand will now have a vision indicator showing whether or not other players are able to see them. Played cards have always been revealed to other players, but now each character has their own unique hand slots that start visible. We think this will add a new layer of strategy and intrigue to deck building while also giving new players a bit more info on what cards to expect in the game.

Wishing you a happy Valentines Day from the Constelleum team!

## Gameplay

- Gimbal updates: 3 new cards, Charge status now increases when Refreshing and has new effects when at max value, existing cards reworked to better utilize multi choice functionality
- Some cards now start visible to opponents based on position in hand (even before being played)

## Art

- Selene got most of her new vfx
- Tophat and Mulberry got their new animations concluding our migration to the new animation system
- New map background concept art

## UI/UX

- You can now invite friends to your lobby or join friends' active lobbies via Steam
- Major animation queue rework: all movement/forced movement types are distinct
- Improve when and how pawns change which direction they face, particularly in interactions with forced movement, AOEs, and ranged targeting
- Deck select now better signals when you have completed selecting vs when action is required
- Minor tutorial visual and layout improvements
- Added character names to tooltips when hovering characters on the field
- Added secondary confirmation step to abandoning a game or restarting a challenge

## Backend

- Game engine and Steam library upgrades to the latest and greatest
- Background work on our tutorial management system, new visuals and experience for these coming soon!
- If someone abandons a game, the server now defaults their selections without waiting for them to timeout

## Bug fixes

- Submitted card now always shows up correctly in the hand
- Re-added missing action information in tooltips
- Characters now correctly disabled once picked during Character Select
- Fixed a bug where typing Disrupt in a search bar returned all cards
- Improved notification upon entering a wrong password when joining a protected lobby
- Made focus-based tooltips a little less intrusive in Deck Builder
