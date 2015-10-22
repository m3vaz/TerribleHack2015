# Tsundere Sharks!

m3vaz: General Idea, Flask/Bluemix integration, JQuery Bootstrapper

celelista: Shuffling and Bogosort, Sleight of (computer) hand, The "good" ending.

jothamchow: 

1rheefra: The "bad" ending, Ambience musician


The goal here was to create something terrible, and in the process learn something new.

From the [Terriblehack site](http://terriblehack.website/):
>Most hackathons are about coming up with innovative new ideas and making plausible startup prototypes. This one is different. This one is about having fun and programming for the sake of programming, even if it means reinventing a less efficient wheel.

[Devpost](http://terriblehack.devpost.com/) lists several criteria to build towards: 
> Security (lack thereof)

> Horrible Design

> Inefficiency

> Meme integration

> Funny Pitch (which goes hand-in-hand with funny idea)

> Involving the organizers

> Cats

> Bad Hardware Hacks

[The site is live](http://tsundere-sharks.mybluemix.net/) and should stay up for as long as we have credit on the bluemix account. 

The idea was to create a web app that sorts a file and returns the sorted file. How did we achieve this while staying true to the spirit of TerribleHack?

###### Security
Fortunately, the file I/O is fairly well locked down in browser implementations. The only file javascript can look at is the one that the user selects. Then again, the site doesn't really say anything about how the file is used beyond "sorted". We could have improved on the security criteria by using URL query parameters that redirect the user without checking the destination. 

###### Design
The horrible design should speak for itself. Bootstrap was specifically avoided, to give that raw 1990's look and feel. Splitting up the html into multiple files could have been done, but then we wouldn't have had merge conflicts during development and we would probably avoid confusion when we return to the code further down the road. 

###### Inefficiency
If you actually look at the code that's concerned with sorting, it uses a flawed version of bogosort. Bogosort takes a lift, shuffles it and checks if the list is sorted, if it isn't it repeats the shuffle and check until it is sorted. Bogosort itself has an average case with a factorial and an unbounded worst case. There are flaws in the bogosort (it doesn't iterate) and the shuffle (it doesn't really shuffle). 

The site is hosted in a Python Flask application, but all the Flask code does is read and send the HTML page. 

###### Meme Integration

[Tsundere Sharks](https://www.reddit.com/r/TsundereSharks/) is a subreddit that takes shark images and adds text or modifies the image such that the sharks look like they're acting according to the [Tsundere trope](http://tvtropes.org/pmwiki/pmwiki.php/Main/Tsundere). 
