# Introduction to OSINT
category: OSINT | practice chall | author: xzy_10

## Desc
Submit the name of this [place](https://drive.google.com/u/0/uc?id=1iYWl1Pkh7ZaKoXhjkwtaBM0Jb5o8oOe5&export=download), alongside the website name (not address) in all small letters without spaces, in the following flag format:

IRS{[NameOfPlace]_[WebsiteName]}

For example, if the place is "Apple Park", and is found from the website with the name "BBC News", the flag is as such: IRS{applepark_bbcnews}

To solve this challenge, one can consider the ways to search an image online. A good one would be Google reverse image search.

# Solution
how hard can reverse image search be 

![testpic](images/testpic.jpg)

generally I head over to <https://images.google.com>

then you just upload the image and look for a file that is exactly the same, with the same dimensions. 

another way I discovered recently is to open the image in a google browser, then right click and select "open with google lens". This uses <https://lens.google.com> instead of google images. I prefer it because it doesn't require opening the windows directoy to dig for the file and upload the file

either way you should come across <https://en.wikipedia.org/wiki/Googleplex> (the other entries about google are irrelevant as they do not discuss the location.)

hence the flag is IRS{Googleplex_wikipedia}

disclaimer i didn't note down what I exactly entered sooo I dunno maybe this exact flag is wrong 
