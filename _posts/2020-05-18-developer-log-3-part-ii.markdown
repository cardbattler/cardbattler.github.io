---
layout: post
title:  "Developer Log 3 - Part II"
date:   2020-05-18
categories: devlog
author: Matt Cotter
---

## Card UI Goes to the Spa

A fun project I tackled this week was updating our card layout and UI.
In our game, the cards pose an interesting design challenge
because there are two opposing forces driving them.
On one hand, our cards need to have a broad
and expressive language to enable rich and complex strategies.
But on the other hand, cards are a fundamental component of our gameplay
and therefore they need to be easily understandable and concise.

Cards right now consist of an initiative value, a title, and a list of actions.
We have a special action type called SelectTile
which encompasses all user input
(ie target selection,
path selection for moving,
and orientation selection for area of effect).
We chain actions together by passing targets<!--end_excerpt--> from one to the next,
and all actions other than SelectTile depend on a preceding SelectTile
to populate their targets.
This implementation detail was easy to see in our old card UI:

![Simple verbose card layout example.]({{site.baseurl}}/assets/images/2020-05-18-developer-log-3/old_card.png)

This design mostly succeeded in expressing all the actions, but failed at being concise and understandable. Our goals for the new card were:

* Never say “Select”; it felt backwards in the old design and input should be implicit.
* Get rid of the scroll bar; the whole card needs to be visible at once.
* Be concise enough to fit cards with many actions.

The solution I implemented was to store the range from the SelectTile actions, then take all following non-select actions and display them in a single block since the targets are chained together. For Move actions, the range of the select is displayed as the value of the move. For other actions range is displayed below and indented. One extra thing we did for range was to make range 1 implicit and to call range 0 “Self” (other values look like “Range 2”). Throwing this together with Alex’s newly-designed card background, our new cards look like:

![Cleave card with a move 3 and attack 20 in an area of effect.]({{site.baseurl}}/assets/images/2020-05-18-developer-log-3/new_card_3.png)![Grapple shot card with a pull two at range 5 that applies the hindered status.]({{site.baseurl}}/assets/images/2020-05-18-developer-log-3/new_card_2.png)![Charge card with a move 6 and an attack 20 that pushes 3.]({{site.baseurl}}/assets/images/2020-05-18-developer-log-3/new_card.png)

We have more work to do on displaying statuses (“Hindered 1,1” with a pixelated arrow won’t cut it), but other than that cards are looking much better and I was able to accomplish the three goals we started with.
