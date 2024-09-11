---
layout: essay
type: essay
title: "Getting the Answers You Want"
# All dates must be YYYY-MM-DD format!
date: 2024-09-10
published: true
labels:
  - Questions and Answers
  - StackOverflow
---

<img width="300px" class="rounded float-start pe-4" src="../img/smart-questions/rtfm.png">

## Developing the Right Approach to Questions

Asking a well-constructed question will increase your chance of receiving well-constructed answers. Asking smart questions requires careful consideration of a few criteria so your question will not be seen as a time waste. Someone who is observant, thoughtful, and willing to learn is less likely to be neglected in a place like a forum where there are many questions that respondents can choose to answer. Following the approach by Eric S. Raymond and Rick Moen in their ["How To Ask Questions The Smart Way"](http://www.catb.org/esr/faqs/smart-questions.html) guide, it is important to take these initial steps to find an answer to your technical question before asking it yourself:

   1. Search archives of the forum you plan to post to or its mailing list.
   2. Search the web ("Google is your friend").
   3. Read the manual.
   4. Read an FAQ.
   5. Go through inspection and/or experimentation.
   6. Ask a skilled friend.
   7. If you program, try to read the source code.

## Constructing the Question

It is important to ask your question in the appropriate place. This encompasses choosing a forum where the question is on topic, deciding whether your question is suited for a technical or more elementary forum, and not cross-posting the question to too many places. There a many forums dedicated to specific niches; [StackExchange](https://stackexchange.com/sites) is a good place to start if you do not know where you may have the most success of getting an answer.

Next, you should make your subject header descriptive and specific. It should be easily understandable what your problem is so that another person with a similar question can look through your post instead of needing to create a new one. In general, the subject header should contain an "object" that specifies the thing having a problem and a "deviation" that describes the unexpected output/behavior. 

For the body of the message, proof read it to be clear, gramatically correct, and without spelling-errors. Then, provide a brief synopsis of your problem's symptoms in chronological order and your ultimate goal. Afterwards, describe the step(s) that your are stuck on. You want to ensure the question is specific without being overly verbose. In the context of code, provide a hint as to the problem respondents should be looking for. Provide a snippet of your code and specify the line(s) of code that failed and what you were expecting to see instead. If possible, provide a minimal test case by adding supporting code to illustrate the unexpected outuput/behavior. Lastly, do not attach an image of your code since the amount of code shown is constrained to the author's screen size. Also, you can not search for specific text in images, which makes it harder to pinpoint certain errors or typos.

## A Look at a Smart Question

Let's take a look at [an example](https://stackoverflow.com/questions/54695859/invalid-pointer-error-on-invoking-free-after-malloc-in-c) of a good question from StackOverflow, which reads:

#### Invalid pointer error on invoking free() after malloc in C

```
I am doing very basic dynamic allocation practice in C and I came across this issue: when I am trying to call `free()` with the pointer returned by `malloc()`, I am getting Invalid pointer error during run time.

When I remove `free()` from code, it works fine. The pointer that I am using is not modified anyhow after returned by `malloc` (except the casting). So that rules out some suggestion I found online. Below is my code:
```

 ```c
#include <stdio.h>
#include <stdlib.h>

int main() {
      int num = 0;
      //printf("Enter a number: ");
      //scanf("%d", &num);
      char* p = (char*)malloc(16*sizeof(char));
      printf("%p", p);
      if(p) {
              p = "mark";
              printf("\n%s\n", p);
              free(p); //when removed no error
      }
      return 0;
}
```

`Following is the error message:`

```c
0xa26010
mark
*** Error in `./a.out': free(): invalid pointer: 0x00000000004006b7 ***
======= Backtrace: =========
/lib/x86_64-linux-gnu/libc.so.6(+0x777e5)[0x7fa968aed7e5]
/lib/x86_64-linux-gnu/libc.so.6(+0x8037a)[0x7fa968af637a]
/lib/x86_64-linux-gnu/libc.so.6(cfree+0x4c)[0x7fa968afa53c]
./a.out[0x40061a]
/lib/x86_64-linux-gnu/libc.so.6(__libc_start_main+0xf0)[0x7fa968a96830]
./a.out[0x4004e9]
======= Memory map: ========
00400000-00401000 r-xp 00000000 08:03 6815746                            /home/kushal/Documents/GATE/prac_C/a.out
00600000-00601000 r--p 00000000 08:03 6815746                            /home/kushal/Documents/GATE/prac_C/a.out
00601000-00602000 rw-p 00001000 08:03 6815746                            /home/kushal/Documents/GATE/prac_C/a.out
00a26000-00a47000 rw-p 00000000 00:00 0                                  [heap]
7fa964000000-7fa964021000 rw-p 00000000 00:00 0 
7fa964021000-7fa968000000 ---p 00000000 00:00 0 
7fa968860000-7fa968876000 r-xp 00000000 08:03 39719295                   /lib/x86_64-linux-gnu/libgcc_s.so.1
7fa968876000-7fa968a75000 ---p 00016000 08:03 39719295                   /lib/x86_64-linux-gnu/libgcc_s.so.1
7fa968a75000-7fa968a76000 rw-p 00015000 08:03 39719295                   /lib/x86_64-linux-gnu/libgcc_s.so.1
7fa968a76000-7fa968c36000 r-xp 00000000 08:03 39714902                   /lib/x86_64-linux-gnu/libc-2.23.so
7fa968c36000-7fa968e36000 ---p 001c0000 08:03 39714902                   /lib/x86_64-linux-gnu/libc-2.23.so
7fa968e36000-7fa968e3a000 r--p 001c0000 08:03 39714902                   /lib/x86_64-linux-gnu/libc-2.23.so
7fa968e3a000-7fa968e3c000 rw-p 001c4000 08:03 39714902                   /lib/x86_64-linux-gnu/libc-2.23.so
7fa968e3c000-7fa968e40000 rw-p 00000000 00:00 0 
7fa968e40000-7fa968e66000 r-xp 00000000 08:03 39714844                   /lib/x86_64-linux-gnu/ld-2.23.so
7fa969046000-7fa969049000 rw-p 00000000 00:00 0 
7fa969064000-7fa969065000 rw-p 00000000 00:00 0 
7fa969065000-7fa969066000 r--p 00025000 08:03 39714844                   /lib/x86_64-linux-gnu/ld-2.23.so
7fa969066000-7fa969067000 rw-p 00026000 08:03 39714844                   /lib/x86_64-linux-gnu/ld-2.23.so
7fa969067000-7fa969068000 rw-p 00000000 00:00 0 
7ffcf8e4b000-7ffcf8e6c000 rw-p 00000000 00:00 0                          [stack]
7ffcf8f1d000-7ffcf8f20000 r--p 00000000 00:00 0                          [vvar]
7ffcf8f20000-7ffcf8f22000 r-xp 00000000 00:00 0                          [vdso]
ffffffffff600000-ffffffffff601000 r-xp 00000000 00:00 0                  [vsyscall]
Aborted (core dumped)
```

## A Question to Improve



## Your Turn
