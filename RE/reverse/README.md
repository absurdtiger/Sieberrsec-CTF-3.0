# reverse

37 solves

<https://github.com/IRS-Cybersec/Sieberrsec-CTF-3.0/tree/master/RE/reverse>

## Description

Reverse Engineering but in python?!!!

[reverse.py](https://github.com/IRS-Cybersec/Sieberrsec-CTF-3.0/blob/master/RE/reverse/reverse.py)

Author: noyou

## Solution

```python
print("Enter the flag and I will check it for you.")
enteredFlag = input()
coolarray = [[[], [], []], [[], [], []], [[], [], []]]
if len(enteredFlag) == 27:
    for i in range(3):
        for j in range(3):
            for k in range(3):
              print(i, j, k)
              coolarray[i][j].append(enteredFlag[i*9 + j*3 + k])
    newflag = ""
    for i in [coolarray[2], coolarray[0], coolarray[1]]:
        for j in i[::-1]:
            for k in [j[1], j[2], j[0]]:
                newflag = newflag + k
    print(newflag)
    if newflag == "1}c5f1bbeb4580{RSI43db46731":
        print("Your flag is correct!")
    else:
        print("Your flag is incorrect. :(")
else:
    print("Your flag is incorrect. :(")
```
yeah, very pain. 

Basically there is a function that takes somethingth letter, puts it into an array, does it a lot of times (with 3 nested for loops running 3 times), effectively doing some jiggly thing rearranging the letters of the flag. 

Then the function checks against the jumbled flag to see if you inputted the right flag. 

I know that I'm not going to waste time figuring out which letter goes into which index of the array, and since the scrambling function is fairly regular, I shall just run the jumbled flag through the program itself a few times. The number of times I have to run it will probably be a multiple of 3. 

flag in code: 1}c5f1bbeb4580{RSI43db46731 <br>
31746b3d4bebf15}c1SIR0{845b <br>
5b4{80IRSd436b4173c1}15febb <br>
bbe5f11}cRSI80{b45731b4643d <br>
3d446b317}c1f15beb45b0{8SIR <br>
IRS{805b41736b4d43ebb15fc1} <br>

not bad for just 6 times. This probably will never work again.
