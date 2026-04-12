---
title: Tiny News
description: Adding a title screen to my GBA Game Feline using HBlank Effects on Affine BGs
date: '2025-08-12'
tags: 
    - coding
---

### Inspiration

About 6 months ago I stumbled across the [Guten](https://amanvir.com/guten), a tiny newspaper printer. This discovery blew my mind and introduced me to the world of thermal printing - some of which I will explore here.

Immediately I jumped on a local auction site and started watching thermal printers. I think a lot of people's intuition here might be to buy new (and there is nothing wrong with that), but there is a world of commercial thermal printers that are miles better than the hobbyist ones you will find on electronics websites. These commercial ones are built reliable, they print quickly and many have additional features like an auto-cutter, USB connectivity, etc.

I was fortunate enough to pick up an Epson TM-82III for $50 from a cafe that was upgrading their POS system - these are worth around $550 brand new and luckily this one only had 13km on the clock. Yes, "only", this thing is good for 150km.

Once I got it I had fun printing a few demos...

- Using the auto-cutter in a loop to print a long strip with many cuts - when hung from either end the receipt looks like bunting.
- Printing a grocery list
- Using the built-in QR code hardware to rickroll my colleagues
- And finally unlocking the true power of the printer with Pillow (python library) and printing images to recreate Dwight's sign from The Office with only a single sheet of paper.

After the initial joy of discovery I decided that I should probably put this thing to use. I started a small journalism group making tiny newspapers for my office.

I was inspired by the idea behind Guten, but had a lot of tweaks that I wanted to make. My initial thought was making something I could set up in the office - then more people could benefit from it than just me. But first I needed content.

### Puzzles

Firstly, puzzles, when I worked at Vodafone there was a group of people that competed in the daily wordwheel in the New Zealand Herald at the time. Yes its cute, but this was before wordle - we didn't have a way to share the fact that we had completed the puzzle without giving away the answer. We went as far as using MD5 hashes on our answers and posting them to the group chat - that way you could prove you knew what it was without spoiling it for others.

As you can see, a great puzzle can foster a great community. I wanted to bring that to the table - which is probably why I have gone overboard on this aspect of tiny-news. I am finally at the point where I can say that I have unique puzzles for every day of the week for about 3 years.

- **Monday** - Takuzu - scrapped from [zuzu](https://api.razzlepuzzles.com/zuzu)
- **Tuesday** - Sudoku - a collection of 17 clue sudoku from [here](https://web.archive.org/web/20131019184812if_/http://school.maths.uwa.edu.au/~gordon/sudokumin.php) 
- **Wednesday** - Wordwheel - my own design using a dictionary and replacing high value (scrabble score) letters.
- **Thursday** - Mini Crosswords - scrapped from NYT
- **Friday** - Chess - Checkmate in one move puzzles taken from [lichess.org](https://lichess.org)

These are stored in json by date. I plan to generate more soon to ensure I have 5 years worth - they could start repeating long before that and I doubt anyone would notice.
### Everything else

Secondly, Guten is designed as a personalised newspaper, but I wanted everyone to get the same newspaper so they had something to discuss at the water-cooler (we don't have one in the office). 

To set up news I hooked in an RSS reader, finding good public sources was difficult though. I began with [RNZ](https://www.rnz.co.nz/) for local news and global - but quickly realised the global feed didn't update frequently enough for daily reading. I switched to BBC for global, but was quickly met with complaints (completely fair enough), so for now I have pulled international news - get in touch if you have any good sources (preferably RSS).

I hooked into [Open-Meteo](https://open-meteo.com/) for weather data - which has been both surprisingly accurate and has a lot of data to explore. I'm planning another update soon to include more information like sun-rise/set times, etc.

And that is it for now, although there are many plans to add additional features.

- **Word of the Day** - we have quite the diverse team and a lot of learners - so having Te Reo Maori, Russian, English and other words.
- **SCIENCE!** - we have bioinformaticians, physicists and other science people - having a daily science fact or article is something that has also been requested.
- **Quote of the Day** - self explanatory.
- **Star Chart** - what can you see in the sky tonight type of thing.

The only problem is keeping the receipt length manageable.

