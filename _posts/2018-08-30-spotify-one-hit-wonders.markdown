---
layout: post
title:  "One hit wonders on Spotify"
date:   2018-08-30 14:16:59 -0600
categories: jekyll update
---
In an effort to practice building an app from start to finish, I followed through on an idea that came to me pretty much out of nowhere. I present the [One-Hit-Wonder-Calculator][app-url]

Theory: If you can quantify how popular a musician’s songs are, you can quantify how much of a one-hit-wonder (OHW) they are.

Method: Popularity data for an artist’s top tracks is available from Spotify. I take this data, sort it from high to low, then run it through a function that fits according to

y = Ae^(-bx)

The assumption is that the parameter “b,” in describing how quickly an artist’s popularity drops after their first track, describes how much of a OHW they are.


I define the one-hit-wonder factor as
​
OHW = b x 1000

and end up with numbers ranging from the low teens to… well I won’t give it away. I define several ranges in the app, and I say that anything over 100 is a “Certified One-Hit-Wonder,” but I probably haven’t found the highest. That’s a different project.

Limitations:
Spotify does not publish how it arrives at the popularity of a track, but we can be sure that their algorithm involves play counts and how recently those play counts were tallied. So we’re calculating an artist’s *current* one-hit-wonder status.

Some artists are so much of a one-hit-wonder (eg Vanilla Ice) that their “hit” shows up multiple times as different versions in their top-ten, throwing off the fitting data and decreasing their OHW factor. I've taken out duplicate tracks and tried to compensate by adding 1/6th of the popularity of the duplicate to the first instance of the song.

I could just take the popularity of the artist’s first track and divide by that of the second track and receive a similar result, but I kind of like the way I’m doing it. By taking into account all of the top-10 tracks, you also catch “two-hit-wonders.”

Currently all the data is for Canadian users.

It’s fun to try and guess which band has the highest OHW factor, but it’s also fun to find the lowest. A very low OHW means that an artist’s 10th most popular track is about as popular as their 1st - it doesn’t necessarily mean that an artist is more or less popular than other artists.

[app-url]: http://www.onehitwondercalculator.com
