---
title: Keeping Tempo
layout: post
date: 2026-04-08
comments: false
excerpt_separator: <!--more-->
---
Made a lot of progress.
<!--more-->   
It’s best to keep a balance of getting things prototyped quickly, while also keeping code clean and organized to build upon. Even still, as the project gets bigger, errors and bugs are bound to show up and the limitations of old systems begin to showcase themselves.  

Enemy spawning was a problem area. Originally setup in Blueprints, battles were triggered through player overlap with an invisible collision box. A fairly standard implementation, it was working as needed. At least until I needed multiple character types spawning in groups over multiple waves of enemies. Adding onto my old system was quickly making the code convoluted and messier.  

![](/assets/images/OG_SpawnSystem.png)

So, I took a step back. I needed a system capable of spawning waves derived from my Base Character while maintaining control over the flow of battle. This needed to support a more dynamic enemy composition alongside room sealing mechanics.

My search for a solution led me to build an Encounter system, to better manage the lifecycle of a combat arena.

The system consists of three main components:

1. Encounter: Controls the overall flow of battle, spawn queueing, delay timing, enemy groups data
2. Spawn Points: Locations where enemies can spawn
3. Gates: Actors used to seal the player within an arena during combat

Each wave contains the enemy class and counts. Handling it this way allows me to setup wave groups with varying enemy types (i.e. 3 Ninjas, 2 Archers, 1 Swordsman), with more precise control over the timing of their spawns too.

![](/assets/images/Encounter_DataAsset.png)

Since the encounters utilize a data asset, this makes for a much more convenient way to adjust individual encounters. In theory, this should make balancing easier in the long run too.

This new encounter system will be a driving force behind the game's combat scenarios and will also be useful for the game's training mode. There, players will be able to adjust factors such as enemy or soul behavior, as well as reference the in-game movelist to practice their skills.

![](</assets/images/Training Menus.png>)

I'm hoping these upfront investments will help speedup prototyping and development for the future.

![](/assets/images/PS2Modeling.png)

On the visual side, I've been hard at work updating the player character model. I'm aiming for a PS2-era look for the game. Characters from that era tended to use textures no higher than 512x512, while contains containing most of the detail seen on a character. In many cases, having even shadows detailed on the texture files themselves. It's been a fun, albeit slow experience getting back to work in Blender. A goal of mine is to aim for higher polygon counts seen in more cinematic titles like Metal Gear Solid, Silent Hill, or Tekken. The game will have several non-player characters in addition to enemies, so the sooner I establish a pipeline for character and environment art the better. There's a wealth of concept art I've been itching to get into the game.

