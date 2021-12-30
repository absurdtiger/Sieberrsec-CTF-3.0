# Heads and Tails Part 3
163 pts | 25 solves | author: hongxun

## Description

Yet again..! (this time with a dollar coin)

If you finish this, I will give you a GIFt :)

[heads_and_tails_part3.jpg](/Misc/Heads&Tails/heads_and_tails_part3.jpg)

## Solution 

Running it through cyberchef doesn't immediately bring out any immediate strings. 

So, I run it through binwalk on a terminal

![p1](/Misc/Heads&Tails/h&t3sol1.png)

darn, a GIF file 

we can extract the bytes with `binwalk --dd='.*' /path/to/file` (easiest way)

![p2](/Misc/Heads&Tails/h&t3sol2.png)

or you can use the `dd` command as explained [here](https://unix.stackexchange.com/questions/450489/use-dd-to-extract-a-precise-portion-of-a-file). This is what I originally did, but it involves a roundabout calulating-number-of-bytes-to-extract-to-put-into-count-parameter <br>
`dd if=headtails3 of=example.gif bs=1 count=404675 skip=25412`

![p3](/Misc/Heads&Tails/h&t3sol3.png)

either works to obtain the GIF. 

I'm using wsl, so I use `wslview` to open image files. 

for demonstration purposes I've saved it as [example.gif](/Misc/Heads&Tails/example.gif).

You can either use OCR software or type it out like a lameo. You can also try to time a screenshot, or use a gifeditor to extract frames. Whatever method you prefer.

originally I typed it out but now I lazy so 

![GIFframe](/Misc/Heads&Tails/h&t3gifframe.png)

through online OCR

Nice! Here's your flag: VEF{n_pYBjA_Ulgg3A_nG_Yr_G4yY} 

...looks like rot13 to me

![finally](/Misc/Heads&Tails/h&t3finally.png)

IRS{a_cLOwN_Hytt3N_aT_Le_T4lL} 
