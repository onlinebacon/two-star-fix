# Two Star Fix

## Summary

Here is a step-by-step guide on how to perform a celestial navigation two-star fix with no need for an assumed (dead reckoning) position.

## Contents

- [Introduction](#introduction)
- [How celestial navigation works](#how-celestial-navigation-works)
    - [Zenith Angle](#zenith-angle)
    - [Geographical Position](#geographical-position)
    - [Circle of Position](#circle-of-position)
    - [Nautical Almanac](#nautical-almanac)
    - [Position Fix](#position-fix)
- [The Method](#the-method)

## Introduction

When I heard about the idea of figuring out your location on the surface of the earth based on observations of celestial bodies it caught my attention. When I realized my current knowledge should be enough to do that I couldn't wait another second before writing some code to see if it would work.

Celestial navigation didn't start in modern days when we have portable, fast and precise calculators, it started around the 1800's so navigators had to rely on a lot of tables and pen and paper maths. I was no where near interested on diving deep into complicated math developed to deal with the absence of a device we have everywhere.

Given all that I went to the most straight forward way to get the coordinates of my location based on readings of positions of celestial bodies.

## How Celestial Navigation Works

In this section I will be describing some basic concepts of celestial navigation. If you are already familiar with them, feel free to skip the explanations.

### Zenith Angle

The point right overhead an observer is called the **Zenith** of that observer. So for example if you happen to be at the subsolar point (the point on the surface directly below the sun) then the sun would be at your zenith. But that won't last for too long, of course, the sun won't stay overhead forever, after a couple of minutes the sun will be lower in the sky. It will have moved from your zenith. With the correct tool you could tell how much it moved. That gets called a **Zenith Angle**.

### Geographical Position

If you're again at the subsolar point, that can also be called the **Geographical Position** of the sun, or just the sun's GP. The GP of a celestial body is simply the position on the earth where you could see that celestial body directly overhead (at your zenith).

### Circle of Position

If a certain celestial body isn't at your zenith then you're not at its GP. But its GP is somewhere else, at a certain distance from you. It turns out that distance can be determined by the zenith angle of that body. Each degree of zenith angle corresponds to around 69 miles of distance between your position and the geographical position of that celestial body.

Say for example you observe Venus 25° below your zenith, that implies you're around 1725 miles away from its GP. Let's also say you don't know where you are but you know where the GP of venus is. Having both a position for the GP of venus and your distance of 1725 miles, we could draw a circle on the earth, centered at the GP of venus, with a radius of 1725 miles.

If you were inside of this circle, the distance to Venus' GP would be smaller than 1725 miles, so you would observe the zenith angle of Venus to be lower than 25°. If you were outside of the circle, the distance would be greater than 1725 miles, and the zenith angle would be larger than 25°. The only place where you could be to observe Venus to be at 25° below your zenith would be at the very edge of that circle. This circle gets called a **Circle of Position** (CoP) because it describes all possible positions you could be at given those two pieces of information.

### Nautical Almanac

The geographical positions of celestial bodies change constantly and quickly. The GP of a celestial body might move as fast as a thousand miles per hour. To be able to create a CoP using the zenith angle of a celestial body you need to know where its GP was right at the moment of the reading. This information is usually acquired from a book called **Nautical Almanac**.

I won't describe in this document how to use the nautical almanac not to extend the content too much. But it's a pretty easy process that requires no more than interpolating values. It's also not necessary to know how to operate the almanac to learn the method I intend to describe.

### Position Fix

When practically navigating, a common method to figure out your position is to start with your current best guess, usually called a dead reckoning position, or an assumed position, and plot a small section of the circles of position on a chart representing your local region. You can mark where the circles intersect and get a better pair of coordinates that you previously had. This process of improving a previous guess by using celestial body readings is called a **position fix**.

## The Method

Given the context explained so far, by reading two zenith angles of two different celestial bodies, recording the exact time of the readings, with the help of a nautical almanac, you should have enough information to built two circles of position. Because you must be at the edge of both circles at the same time, you can pinpoint your location by finding their intersection.

It was said previously that each degree of zenith equates to 69 miles of distance. That equates to a 1° arc over the surface of the earth. So the zenith angle establish a 1 to 1 relationship to the surface of the earth.
