# Two Star Fix

## Summary

Here is a step-by-step guide on how to perform a celestial navigation two-star fix with no need for an assumed (dead reckoning) position.

## Index

- [Introduction](#introduction)
- [How celestial navigation works](#how-celestial-navigation-works)
    - [Zenith Angle](#zenith-angle)
    - [Ground Position](#ground-position)
    - [Circle of Position](#circle-of-position)

## Introduction

When I heard about the idea of figuring out your location on the surface of the earth based on observations of celestial bodies it caught my attention. When I realized my current knowledge should be enough to do that I couldn't wait another second before writing some code to see if it would work.

Celestial navigation didn't start in modern days when we have portable, fast and precise calculators, it started around the 1800's so navigators had to rely on a lot of tables and pen and paper maths. I was no where near interested on diving deep into complicated math developed to deal with the absence of a device we have everywhere.

Given all that I went to the most straight forward way to get the coordinates of my location based on readings of positions of celestial bodies.

## How celestial navigation works

### Zenith Angle

The point right overhead an observer is called the **zenith** of that observer. So for example if you happen to be in the subsolar point (the point on the surface directly below the sun) then the sun would be at your zenith. But that won't last for too long, of course, the sun won't stay overhead forever, after a couple of minutes the sun will be lower in the sky. It will have moved from your zenith. With the correct tool you could tell how much it moved. That gets called a **zenith angle**.

### Geographical Position

If you're again in the subsolar point, that can also be called the geographical position of the sun, or just the sun's **GP**. The GP of a celestial body is simply the position on the earth where you could see that celestial body directly overhead (at your zenith).

### Circle of position

If a certain celestial body isn't at your zenith then you're not at its GP. But its GP is somewhere else, at a certain distance from you. It turns out that distance can be determined by the zenith angle of that body. Each degree of zenith angle corresponds to around 69 miles of distance between your position and the geographical position of that celestial body.

Say for example you observe Venus 25° below your zenith, that implies you're around 1725 miles away from its GP. Let's also say you don't know where you are but you know where the GP of venus is. Having both a position for the GP of venus and your distance of 1725 miles we could draw a circle on the earth, centered at the GP of venus, with a radius of 1725 miles. If you were inside of this circle, the distance to its GP would be smaller than 1725 miles, so you would observe a zenith angle to Venus lower than 25°. If you were outside the circle, the distance would be greater than 1725 miles, and the zenith angle would be larger than 25°. The only place where you could be to observe Venus to be at 25° below your zenith, would be at the very edge of that circle. 