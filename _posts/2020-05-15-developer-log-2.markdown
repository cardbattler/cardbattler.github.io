---
layout: post
title:  "Developer Log 2"
date:   2020-05-15
categories: devlog
---

### Animation: When Push Comes to Shove - Alex

Time to get things moving. This week we attacked the first pass on animations, not letting ourselves sit on idle hands.

Before animation, the game state was updated as soon as a turn ended. For players not taking their turn, characters popped from point to point and swung an axe without moving a muscle. Fantastic material for theater of the mind, but a hint as to why your character is halfway to defeat is usually appreciated. You want to see fists fly, boots scoot, and heads bob.

During my original pass on some developer assets, I had put together some crude animations. As the reader will witness shortly, the graphic arts are not my strength. Each animation is two to four frames of 100 X 100 pixels made in GIMP. The frames are pixel art only because I had dabbled in making custom avatars for Kingdom of Loathing 10 years ago. The final art style, though still being discussed, will not be pixel art.

The following idle animations feature our placeholder characters:

![Archer idle animation.](https://cdn.discordapp.com/attachments/575192288951533571/708945614674853909/archer.gif)![Grappler idle animation.](https://cdn.discordapp.com/attachments/575192288951533571/708945691262844988/grapp.gif)![Juggernaut idle animation.](https://cdn.discordapp.com/attachments/575192288951533571/708945751417421844/jugg.gif)

<!--end_excerpt-->

The frames I made were imported into Godot and added as texture keys in an AnimationPlayer. The AnimationPlayer updates the character’s avatar image, animating it.

![Demonstration of the animation keys for the Archer attack animation.](https://cdn.discordapp.com/attachments/575192288951533571/708946437714608138/animating.gif)

After some research into the docs, we chose not to utilize Godot’s built in animation queue features. We want each character to show being attacked, pushed, or affected by other characters. but we don’t use collisions to tell characters to animate appropriately. The emit_signal in the image above lets the target characters know to animate being hit (for the time being means flash red).  Because of this “subqueue” of animations, we chose to develop our own animation queue.  Rather than building movement into animations, we chose to use Godot’s Tween’s to move pawns around the field.

Below is an example of Juggernaut playing “Charge.” He moves, then attacks and pushes Archer back. Because Archer is taking damage after the front swing is finished, Archer can take damage and move while Juggernaut completes his animation. The speed is reduced to emphasize the attack’s front swing.

![](https://cdn.discordapp.com/attachments/575192288951533571/708946835510919228/action.gif)

The reader may notice that Archer is blue before the attack but teal and purple after. Archer changes colors because currently both team assignment and taking damage modify the “modulate” value of the pawn, which changes the hue .

P.S. Here are some more examples of placeholder animations. I particularly enjoy the MC Hammer shuffle from Archer and the Juggernaut waddle.

![Grappler punching.](https://cdn.discordapp.com/attachments/575192288951533571/708948344961105950/pun.gif)![Grappler walking.](https://cdn.discordapp.com/attachments/575192288951533571/708948348236988506/pun2.gif)![Juggernaut jabs forward with halberd.](https://cdn.discordapp.com/attachments/575192288951533571/708948350531272774/pun3.gif)![Juggernaut walking.](https://cdn.discordapp.com/attachments/575192288951533571/708948352641007656/pun4.gif)![Archer pulling back and shooting an arrow.](https://cdn.discordapp.com/attachments/575192288951533571/708948354905800784/pun5.gif)![Archer moving.](https://cdn.discordapp.com/attachments/575192288951533571/708948357523046451/pun6.gif)
