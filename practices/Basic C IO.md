# Basic C I/O

Category: BE | Practice chall | author: main

## Description
> Different languages have different functions for I/O. Python has input() and print(), C++ has cin and cout, and C has gets, puts, fgets, fputs, scanf, printf, getchar, putchar, read, write....
> 
> CTF challenges tend to mix and match a lot of these input functions, so it's important that you understand the minututae differentiating them.
> 
> As an example, consider this program:
> ```c 
> int main() {
>   printf("hello");
>   putchar(' ');
>   puts("world!");
> }
> ```
> 
> If you compile this program to the executable a.out, running the program should give you an output like this:
> ``` 
> $ ./a.out
> hello world!
> $
> ```
> **The C representation of the entire output is "hello world!\n".** The funny \n character is an escape sequence; \n in particular is basically equivalent to the enter key on your keyboard.
> 
> Here is another program:
> ```c
> #include <stdio.h>
> int main() {
>   setbuf(stdout, NULL);
>   printf("%p\t- ", 2);
>   write(1, "hellllllllllllllllllllooooo", 16);
>   fputs("p me!",stdout);
>   putchar(10);
>}
>```
> The flag for this challenge is the C representation of the expected output of this program. Make sure you include the quotation marks.

# Solution
don't ask me why I decided to put the entire desc in a block quote. I'm never doing that again. 
originally I read a bit too much into the c code and bothered a few people trying to understand what the `setbuf` function did, out of my complete unfamiliarity with c. 
eventually it got into my head that they literally just wanted the formatted output as the flag. 

how is this pwn even

either way I was stuck trying to concatenate strings for a while, until I opened a ticket and asked for help. response I got hinted to the bolded text **The C representation of the entire output is "hello world!\n".**, which I had completely overlooked. In my defence, bold white text is not easy to discern on a dark background. 
I also realised I was a doofus and I didn't save my final input anywhere, so I will just wing and say it was 
`"0x2\t- hellllllllllllllp me!\n"`
without having concrete verification that this is the correct answer. 
I don't mentally consider this a valid chall but it was interesting I suppose 
