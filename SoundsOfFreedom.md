## OSINT - Sounds of freedom!

### Introduction
----
This is a challenge unlocked by completing the previous OSINT challenge: "Only time will tell!". This was a really interesting challenge that made me be scratch my head a little at the start. I was initially afriad that this would be too hard to solve for people without a good knowledge of Singapore's geography/housing, but it just reminded me that a keen eye and intuitive Googling can help solve many problems! Anyway, let's get into solving this.

### Solution
----
For some background, this challenge provided a cryptic video that panned over an area with trees and a body of water. To solve the challenge, you would have to find the postal code of the body of water and place it in the flag format of `govtech-csg{postal-code}`.

The cryptic video provided only gave a small glimpse of the surrounding areas of what seemed to be a park, a body of water and some HDB (Housing Development Board) flats. There was also a plane sound in the background that could give hints of a nearby military airbase.

![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2FpNiLpzVJK9.png?alt=media&token=a162f084-a551-4c94-af42-ce02ec3cbcc1)

Looking at the video, the location that this video was filmed from also seemed like a condominium or one of those fancier & newer block of HDB flats, from how the air-conditioner condensers were placed.

Due to my horrible lack of awareness of Singapore's geography, I was unfortunately unable to spot the location of this body of water on first sight (though I am sure that someone else playing this CTF did). Despite this setback, I turned to my trusty ole' friend that has never let me down: Google. Given that I knew that I was only looking for: 1: A body of water and 2: A condominium to look down from, I ran a quick search for "condo near body of water singapore".


This search returned a condominium and body of water (clearly) in Yishun; the Seletar Reservoir.
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2Fo1s_ocox1N.png?alt=media&token=7cc8a2f5-eec3-4d10-83c9-bfae89c54bd4)

From the satelite image, this was clearly **not** the correct body of water because the shape was wrong (the body of water in the video is surrounded by trees wheras this reservoir is HUGE).

I had to up my Google-fu game. I thought of possible types of places where a body of water could be enclosed by trees. That's it. It was a **lake** in a **park**!!
 
Now, with that information, it would be pretty simple to find. There are only so many parks with lakes that can be overlooked from a condominium while at the same time having HDB flats in view. So I Googled it.

(Yes, I really just searched for "parks with lakes singapore".)

![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2Fdb35py0zQF.png?alt=media&token=874f0f4e-fe27-413b-9bc4-23cf32282d56)


There were three hits on the first page: Fort Canning Park, Chinese Garden, and Punggol Park. The first two could be eliminated because 1: The video looked nothing like Fort Canning Park at all so it was easy to strike out and 2: Chinese Garden is temporarily closed for upgrading, and park goers could be seen exercising (walking? jogging? doing something fit?) in the video.  

![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2F3ttoo-msSJ.png?alt=media&token=4870838b-0990-4960-ab0b-f1c298e4f375)

This leaves Punggol Park as the first one to check out. Opening it in Google Maps satellite view was promising. The shape of the lake on the map seemed just about right from the video and the water looked like the same shade of green too!

![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2FuuNl0d18QI.png?alt=media&token=f1e961d3-0aef-4817-bf94-c67bfaa6c5a6)


Upon closer inspection, there is not only a new/fancy HDB to overlook the park (Hougang ParkEdge) but also a set of HDB blocks behind the park that match up in practically the same way as the video too!

![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2FaG-6aI-TwL.png?alt=media&token=358906d4-b85c-402d-8d5e-fcf8035d9ac1)

![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2FpNiLpzVJK9.png?alt=media&token=a162f084-a551-4c94-af42-ce02ec3cbcc1)

I digged a little further and found out that flying kites is actually prohibited at Punggol Park because of near by airbase (Paya Lebar Airbase), which could explain the noises in the video. I was sure that this was the right place.

![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2F6Z_fAuQna-.png?alt=media&token=6dd9dafd-3131-456a-9816-fcb1407576cc)

The postal code for Punggol Park is 538768, making the flag `govtech-csg{538768}`. I submitted it and... It was correct! Hooray for specific Googling!
![Pepe Silvia | Know Your Meme](https://i.kym-cdn.com/entries/icons/original/000/022/524/tumblr_o16n2kBlpX1ta3qyvo1_1280.jpg)



### Thoughts and Conclusions
----

My lines for solving this challenge were pretty interesting and, in my opinion, pretty out of my comfort zone. While I used Google Maps to find the cardinal direction of a sign in the previous challenge, stretching the same tool even further and using it in a slightly different way this time was an absolute blast! This challenge really reaffirmed the need to make use of every single bit of information that is given to you.
