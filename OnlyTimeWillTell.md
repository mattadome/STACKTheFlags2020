## OSINT - Only Time Will Tell

### Introduction
-----
Over the past weekend, despite being swamped with projects and presentations to prepare from, I managed to take a short breather to attempt some challenges for the GovTech CTF - STACK The Flags 2020! I really wish
This was a pretty fun, albeit easy, challenge. Definitely had some feelings of **power** when I solved this though! Let's get into how I managed to solve it.



### Solution
-----
You are given this image and have to find the time, date and place (in GPS coordinate) that this photo was taken. Sounds easy enough, right?
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2Fp34bqKzN2l.png?alt=media&token=4c9ed79d-d1dd-492c-b2cf-6c11fde01799)



First things first, in hopes that I could get the flag on my first attempt I used EXIFTool to get all metadata of the file. EXIFTool is an insanely useful tool that manages to list out information such as GPS coordinates that the photo was taken at, and sometimes even the make of the camera taking the photo!

![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2Fq3bnLWTPUK.png?alt=media&token=99d841a9-63f8-4a6b-ac6e-d19679f5fc6d)


I converted the GPS Latitude and Longitude with the provided calculator
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2FD6SgLWby8Z.png?alt=media&token=97802bca-6410-4910-bf36-127342c15f13)


Next, pulled the date and time from the File Modified time and got this flag: `govtech-csg{1.286647_103.846836_2020:12:01_1000-1200} ` 

Obviously, this flag was wrong because they would not make it that simple for us to solve. Next I noticed that there was a small barcode at the bottom of the image, so I cropped it out and ran it through a barcode scanner.

![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2FT3D6sdO1rj.png?alt=media&token=a8da5a20-3c96-432d-a55c-297b0a1e4909)


After running it through the scanner, it returned `25 October 2020`. My new flag read `govtech-csg{1.286647_103.846836_2020:10:25_1000-1200}`

This flag still did not work so I had to take a step back and ask myself: "What could I possibly miss that would make me slap my forehead in frustration at my own stupidity and lack of awareness?". I took another hard look at the image and realised a key piece of information was right under my nose. They were **shadows**.

The picture was pretty self explanatory with the sign clearly being at Speaker's Corner but knowing next to nothing about the geography of Singapore, I had no clue what cardinal direction this sign was facing.

Thankfully, Google Maps automatically sets their maps to face the North so finding the sign was a lot less difficult than I thought it would be. I loaded up the general location of Speaker's Corner on Google Maps Satellite View.

After poking around, I realised that the sign seen in the picture was in the red circle below:

![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2FQJ4-fBL9is.png?alt=media&token=adc4ea85-b5d3-4996-8690-cbe7df2c5c9e)

![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FFirstDatabase%2FOzZIKuy7xK.png?alt=media&token=c23de3b7-f7c5-4a52-905b-c22248d4a18a)

Because it was pretty clear that the sun was beating down furiously from the west (the shadow was pretty long, after all), it was safe to assume that the most likely possible base times would be 3pm, 4pm or 5pm. At 6pm, the picture would have an orange hue, and at 7pm the picture would be too dark to be midday.

I picked the first base time 3pm and put it in the 2 hour block format of `1500-1700` and got the new flag of 

`govtech-csg{1.286647_103.846836_2020:10:25_1500-1700}` which was, thankfully, correct on the first try!




### Thoughts and Conclusions
-----


