---
layout: post
title:  "Developer Log 6"
date:   2020-05-28
categories: devlog
---

### Sandbox - Matt

This week I implemented a Sandbox mode in our game client. This allows us (and any player) to run the game locally and test cards and mechanics against dummy players. To accompany this, I also made a new map with clusters of obstacles. Here’s how it looks:

![Map with circles of cracks, vines, and walls](https://cdn.discordapp.com/attachments/575192288951533571/715638648132862043/sandbox.png)

<!--end_excerpt-->

This project was particularly valuable to us because it makes testing significantly easier. Before this, to test any card, we had to: change the card data on the server, run it, start two instances of Godot for the client, run them both, connect to the server, go through character and position draft, then finally test the card all while managing 9 godot windows (one editor, one console, and one game window per each client and server). Now we can change the card data in the client, start the client and go to sandbox, pick a character and position, and then test the cards. This significantly reduces the time and complexity of testing new features.

Implementing this first pass of sandbox mode was thankfully pretty simple. In our game, the server has been and will always be the final authority on current game state. For security (and fair rankings), we are operating under the assumption that once the client binary leaves our machines, we no longer trust it. Because of this, the server always validates all user inputs and fully tracks the game state. However, any unmodified client will also validate all inputs and track game state in order to only allow players to make valid selections. With all this in mind, we arrived at an api that (after connecting and character/position drafts are done) looks like this:

* Clients send card choices to the server.
* The server accepts or rejects until all characters have selected a valid card.
* The server sends the first card (in initiative order) to all clients.
* The player who chose this card makes selections for all actions on the card.
* The server accepts or rejects the selections, and once accepted sends the selections to all clients.
* Clients show animations for the selections and update their game state.
* The server sends the next card and repeats the previous steps until all cards for this round are handled.
* Go back to card select, repeat until the game is over.

The sandbox mode implementation is a substitute for the code in the client that handles communications with the server. This required a little refactoring, but now the boundary between the game management and the networking code is extremely clear and well defined. In sandbox mode, instead of sending selections to the server, selections are immediately accepted with no additional validation. When the player chooses a card, it is put first in initiative order and sent back. When the player submits selections for the card, the selections are accepted, then the dummy characters both mend their shields to full, and lastly the client is sent back to the card selection phase.

This sandbox mode is a precursor to our future tutorial implementation as well as a player-vs-environment (ie play against the computer) mode. As the current version of our game progresses, it is really starting to look like our vision for the finished product!
