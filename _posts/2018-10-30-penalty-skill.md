---
title: "How bad is Riyad Mahrez at penalties?"
date: 2018-10-30
layout: single
excerpt: Modelling penalties to look at player skill.
header:
  image: "assets/images/mahrez.jpg"
  filter: 0.5
  teaser: "assets/images/pen.jpg"
categories:
  - Football
tags:
  - football
  - penalty
  - xg
  - stan
  - pymc3
comments: true
---

## Penalties
As soon as Riyad Mahrez missed his penalty against Liverpool, the commentators were already questioning whether he was the right man to have taken it.  After-timing aside, do they have a point? He had missed his previous 2 attempts, is there anything we can learn from this or is it too small a sample size?

## Averages
The table below shows the breakdown of all the penalties in my database.

| Outcome | %   |
|---------|:----|
|Goal     |0.757|
|Miss/Save|0.243|

Prior to his Liverpool penalty Mahrez had a conversion percentage of 64.3% from 14 penalties.  Is this enough information to suggest he is bad at penalties?

## Player conversion
By grouping the penalties by player they were taken by we can look at player conversion, the table below shows the 5 players who have taken the most penalties in the dataset.

| Player            | No. Pens| Conversion % |
|-------------------|:--------|:-------------|
|Cristiano Ronaldo  |86       |0.826         |
|Lionel Messi       |57       |0.789         |
|Zlatan Ibrahimovic |55       |0.873         |
|Edison Cavani      |44       |0.75          |
|Sergio Aguero      |39       |0.769         |

The mean conversion for a player is 69.4%, there is a lot of players in the dataset who have taken only 1 penalty (1041 out of 2494 players)

<figure class='centre'>
	<a href="/assets/images/pen_average.jpeg"><img src="/assets/images/pen_average.jpeg"></a>
</figure>

## Modelling 
We have $$N$$ players
