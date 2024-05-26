---
layout: post
title:  "Developer Log 3"
date:   2020-05-18
categories: devlog
---

### From Version to Version - Mitch

This past week the team switched over to the next version of the game, V5 to V6, so this felt like an opportune time to share a bit of our process. I can’t say it’s anything special, but it works for us so on some level that just means it works.

The first step is our roadmap. A while back we created a list of rough grain features that we thought were essential to our games completion. Using those features we project out about 2 months on our roadmap on Trello.

<img src="{{site.url}}/assets/images/2020-05-18-developer-log-3/Screenshot_9.png" alt="Two Trello lists for our V5 and V6 roadmap." longdesc="{{site.url}}/assets/long_descriptions/trello_v5andv6">

<!--end_excerpt-->

The rest of the roadmap is going to be kept private for internal use, but this gives you an idea of how we arrange things.

When we arrive on a new version we take the roadmap features and translate them into an outline document. This is where the features and the support features that they require get laid out so that we can have a sense of the scope and goal of the version. As an example:

#### High level description of V6

A True vertical slice of our game.

#### Game setup

* Choose between existing and new modes
  * 1v1 mode
  * Local sandbox
  * (3v3 as is)
* Reconnect

#### UI

* Ghoooooooooost
* UI for timers
* Action log

And then lastly we convert the outline into to do items on another Trello board.

![Trello to do lists with the tasks described in the outline.]({{site.url}}/assets/images/2020-05-18-developer-log-3/Screenshot_8.png)

It all ends up working fairly smoothly and there haven’t been any hiccups with the process itself. The versions feel concrete and chunky with a general goal of them being about a month worth of development. Entering V6 our hopes are that by V11 we’ll be ready for launch.

### Card UI Goes to the Spa - Matt

A fun project I tackled this week was updating our card layout and UI. In our game, the cards pose an interesting design challenge because there are two opposing forces driving them. On one hand, our cards need to have a broad and expressive language to enable rich and complex strategies. But on the other hand, cards are a fundamental component of our gameplay and therefore they need to be easily understandable and concise.

Cards right now consist of an initiative value, a title, and a list of actions. We have a special action type called SelectTile which encompasses all user input (ie target selection, path selection for moving, and orientation selection for area of effect). We chain actions together by passing targets from one to the next, and all actions other than SelectTile depend on a preceding SelectTile to populate their targets. This implementation detail was easy to see in our old card UI:

![Simple verbose card layout example.]({{site.url}}/assets/images/2020-05-18-developer-log-3/old_card.png)

This design mostly succeeded in expressing all the actions, but failed at being concise and understandable. Our goals for the new card were:

* Never say “Select”; it felt backwards in the old design and input should be implicit.
* Get rid of the scroll bar; the whole card needs to be visible at once.
* Be concise enough to fit cards with many actions.

The solution I implemented was to store the range from the SelectTile actions, then take all following non-select actions and display them in a single block since the targets are chained together. For Move actions, the range of the select is displayed as the value of the move. For other actions range is displayed below and indented. One extra thing we did for range was to make range 1 implicit and to call range 0 “Self” (other values look like “Range 2”). Throwing this together with Alex’s newly-designed card background, our new cards look like:

![Cleave card with a move 3 and attack 20 in an area of effect.]({{site.url}}/assets/images/2020-05-18-developer-log-3/new_card_3.png)![Grapple shot card with a pull two at range 5 that applies the hindered status.]({{site.url}}/assets/images/2020-05-18-developer-log-3/new_card_2.png)![Charge card with a move 6 and an attack 20 that pushes 3.]({{site.url}}/assets/images/2020-05-18-developer-log-3/new_card.png)

We have more work to do on displaying statuses (“Hindered 1,1” with a pixelated arrow won’t cut it), but other than that cards are looking much better and I was able to accomplish the three goals we started with.
