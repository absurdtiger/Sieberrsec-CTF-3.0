# Basic scripting test

category: misc | practice chall | author: main 

## Description
Duchess Diana needs help mining some SieberrCoins (very similar to bitcoin) to run a rugpull on unsuspecting children -- you'd be one of the victims, if Diana hadn't hired you as a co-conspirator in cupidity.

To collect a SieberrCoin, you must to find [MD5](https://en.wikipedia.org/wiki/MD50) hashes which, in [hexadecimal](https://en.wikipedia.org/wiki/Hexadecimal), start with at least **five zeros**. The input to the MD5 hash is the string `sieberrsec` followed by a **number** in decimal. To mine a new SieberrCoin, you must find Diana the **lowest positive number** (no leading zeroes: 1, 2, 3, ...) that produces such a hash and has yet to be used for previous SieberrCoins on the blockchain.

For example,

- The first SieberrCoin in existence is represented by the number `381182`, because the MD5 hash of `sieberrsec381182` starts with five zeroes `(0000006c29d0...)`, and it is the lowest such number to do so.
- The second SieberrCoin was made with the number `609619` and has an MD5 hash of `00000237e50....`
- Submit the number that will produce the 10th SieberrCoin as the flag.

## Solution
considering that I don't code, and that I have next to no python experience, I firstly surprised myself by understanding what I needed to script. 

- you need to find the 10th valid sieberrcoin
- a sieberrcoin is a number 
- a sieberrcoin needs to fulfill the following criteria:
  - when run through md5, the first 5 characters must be zeros
- two examples are given, of the first and second coin. 
- you can hardcode the first coin since it is given (starting point) 
- the script should achieve the following 
  - have an integer that runs through a checking function to see if the md5 hash starts with 2 zeros
  - if it does, it recognises it as a valid coin, and should know the nth term, if n != 10 it should continue checking integers
  - if it doesn't, it keeps increasing the integer 

I know the nth thingy probably wasn't necessary but I wanted it to self terminate

I also know it can be done with a function and a couple if statements

the only thing I didn't know was how to md5 in python which was really easy to search. so after that I wrote the following script 

```python 
import hashlib

#reminds you what the starter is
print("the first sieberrcoin is 381182.")

#function to iterate through each possible coin and the nth actual coin
def check(sieberrcoin, end):

    #define the nth real coin
    n = 1
    #run the following as long as the endth coin is not found
    while n <= int(end) :

        #formatting
        hashinput = "sieberrsec" + str(sieberrcoin)
        #hashing function
        enc = hashlib.md5(hashinput.encode())
        hashoutput = enc.hexdigest()
        #print(hashoutput) #testing the hexd hash

        #check if the hash fulfills the requirement
        if hashoutput[0:5] == '00000' :
            print(str(sieberrcoin)+" is the "+str(n)+"th sieberrcoin")
            sieberrcoin += 1
            n += 1
        else :
            #print(sieberrcoin)
            sieberrcoin += 1

#actually run the thing
check(381182, 10)
```

let me repeat that I don't code so I honestly impressed myself doing this 
