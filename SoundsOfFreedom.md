- STACKTheFlags Write Ups
- **OSINT - Only Time Will Tell**
    - This was a pretty fun, albeit easy, challenge. Definitely had some feelings of **power** when I solved this though! 
    - You are given this image and have to find the time, date and place (in GPS coordinate) that this photo was taken. Sounds easy enough, right?
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2Fp34bqKzN2l.png?alt=media&token=4c9ed79d-d1dd-492c-b2cf-6c11fde01799)
    - First things first, in hopes that I could get the flag on my first attempt I used EXIFTool to get all metadata of the file 
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2Fq3bnLWTPUK.png?alt=media&token=99d841a9-63f8-4a6b-ac6e-d19679f5fc6d)
    - I converted the GPS Latitude and Longitude with the provided calculator
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2FD6SgLWby8Z.png?alt=media&token=97802bca-6410-4910-bf36-127342c15f13)
    - Next, pulled the date and time from the File Modified time and got this flag: `govtech-csg{1.286647_103.846836_2020:12:01_1000-1200} ` 
    - Obviously, this flag was wrong because they would not make it that simple for us to solve. Next I noticed that there was a small barcode at the bottom of the image, so I cropped it out and ran it through a barcode scanner.
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2FT3D6sdO1rj.png?alt=media&token=a8da5a20-3c96-432d-a55c-297b0a1e4909)
    - After running it through the scanner, it returned `25 October 2020`
    - My new flag read `govtech-csg{1.286647_103.846836_2020:10:25_1000-1200}`
    - This flag still did not work so I had to take a step back and ask myself: "What could I possibly miss that would make me slap my forehead in frustration at my own stupidity and lack of awareness?". I took another hard look at the image and realised a key piece of information was right under my nose. They were **shadows**.
    - The picture was pretty self explanatory with the sign clearly being at Speaker's Corner but knowing next to nothing about the geography of Singapore, I had no clue what cardinal direction this sign was facing.
    - Thankfully, Google Maps automatically sets their maps to face the North so finding the sign was a lot less difficult than I thought it would be. I loaded up the general location of Speaker's Corner on Google Maps Satellite View.
    - After poking around, I realised that the sign seen in the picture was in the red circle below:
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2FQJ4-fBL9is.png?alt=media&token=adc4ea85-b5d3-4996-8690-cbe7df2c5c9e)
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2FOzZIKuy7xK.png?alt=media&token=c23de3b7-f7c5-4a52-905b-c22248d4a18a)
    - Because it was pretty clear that the sun was beating down furiously from the west (the shadow was pretty long, after all), it was safe to assume that the most likely possible base times would be 3pm, 4pm or 5pm. At 6pm, the picture would have an orange hue, and at 7pm the picture would be too dark to be midday.
    - I picked the first base time 3pm and put it in the 2 hour block format of `1500-1700` and got the new flag of `govtech-csg{1.286647_103.846836_2020:10:25_1500-1700}` which was, thankfully, correct on the first try!
- **OSINT - Sounds of freedom!**
    - This is a challenge unlocked by completing the previous OSINT challenge: "Only time will tell!"
    - The cryptic video provided only gave a small glimpse of the surrounding areas of what seemed to be a park, a body of water and some HDB (Housing Development Board) flats.
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2FpNiLpzVJK9.png?alt=media&token=a162f084-a551-4c94-af42-ce02ec3cbcc1)
        - There was also a plane sound in the background that could give hints of a nearby military airbase
    - The location that this video was filmed from also seemed like a condominium or a newer block of HDB flats, from how the air-conditioner condensers were placed.
    - Due to my horrible lack of awareness of Singapore's geography, I was unfortunately unable to spot the location of this body of water on first sight (though I am sure that someone else playing this CTF did)
    - Despite this setback, I turned to my trusty ole' friend that has never let me down: Google. Given that I knew that I was only looking for: 1: A body of water and 2: A condominium to look down from, I ran a quick search for "condo near body of water singapore".
    - This returned a condominium and body of water (clearly) in Yishun; the Seletar Reservoir.
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2Fo1s_ocox1N.png?alt=media&token=7cc8a2f5-eec3-4d10-83c9-bfae89c54bd4)
    - From the satelite image, this was clearly **not** the correct body of water because the shape was wrong (the body of water is supposed to be in the middle of a bunch of trees).
    - I had to up my Google-fu game. I thought of possible types of places where a body of water could be enclosed by trees. That's it. It was a **lake** in a **park**.
    - Now, with that information, it would be pretty simple to find. There are only so many parks with lakes that can be overlooked from a condominium while at the same time having HDB flats in view. So I Googled it.
    - Yes, I really just searched for "parks with lakes singapore".
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2Fdb35py0zQF.png?alt=media&token=874f0f4e-fe27-413b-9bc4-23cf32282d56)
    - There were three hits on the first page: Fort Canning Park, Chinese Garden, and Punggol Park. The first two could be eliminated because 1: The video looked nothing like Fort Canning Park at all so it was easy to strike out and 2: Chinese Garden is temporarily closed for upgrading, and park goers could be seen exercising (walking? jogging? doing something fit?) in the video.  
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2F3ttoo-msSJ.png?alt=media&token=4870838b-0990-4960-ab0b-f1c298e4f375)
    - This leaves Punggol Park as the first one to check out. Opening it in Google Maps satellite view was promising. The shape of the lake on the map seemed just about right from the video and the water looked like the same shade of green too!
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2FuuNl0d18QI.png?alt=media&token=f1e961d3-0aef-4817-bf94-c67bfaa6c5a6)

    - Upon closer inspection, there is not only a new/fancy HDB to overlook the park (Hougang ParkEdge) but also a set of HDB blocks behind the park that match up in practically the same way as the video
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2FaG-6aI-TwL.png?alt=media&token=358906d4-b85c-402d-8d5e-fcf8035d9ac1)
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2FpNiLpzVJK9.png?alt=media&token=a162f084-a551-4c94-af42-ce02ec3cbcc1)
    - The postal code for Punggol Park is 538768, making the flag `govtech-csg{538768}`, which was correct! Hooray for specific Googling!
![Pepe Silvia | Know Your Meme](https://i.kym-cdn.com/entries/icons/original/000/022/524/tumblr_o16n2kBlpX1ta3qyvo1_1280.jpg)
