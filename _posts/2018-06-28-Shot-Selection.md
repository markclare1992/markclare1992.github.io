---
title: "Does game-state affect shot selection & style"
date: 2018-06-21
layout: single
excerpt: Changes in football based upon score.
header:
  teaser: "assets/images/gamestatelocation.gif"
categories:
  - Football
tags:
  - football
  - gamestate
  - xg
  - opta
comments: true
---

## Shot location
I wanted to look at whether players take shots from different locations depending on what the current score is.  I was also interested in seeing how shots are generated and whether that chages too.
Removing penalties from the dataset and plotting the average locations for shots gave the plot below.

<figure class='centre'>
	<a href="/assets/images/avgshot.gif"><img src="/assets/images/avgshot.gif" width='1220' height='700'/></a>
	<figcaption>Click for clearer graphs.</figcaption>
</figure>
	
## Shot heat map
Looking at all shots and plotting a heat map for each game state.  I intended for these heatmaps to contain more gamestates and to be smoother but that takes a significant amount of computing power for large datasets.

<figure class='centre'>
	<a href="/assets/images/gamestatelocation.gif"><img src="/assets/images/gamestatelocation.gif" width='1220' height='700'/></a>
	<figcaption>Click for clearer graphs.</figcaption>
</figure>

## Shot generation
Does the way shots are generated change depending on the current score?

<figure class='centre'>
	<a href="/assets/images/buildup.png"><img src="/assets/images/buildup.png"></a>
</figure>

## Caveats
There is the possibility that good teams are more likely to be in a positive game state, and that they might be good teams because they take better shots and because they can advance the ball to better areas.

## Continution
- It would be interesting to do a similar analysis for successfully completed pass locations and type of pass.  
- Do proper spatial analysis and attempt to plot smoother density maps.