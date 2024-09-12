---
layout: essay
type: essay
title: "Getting the Answers You Want"
# All dates must be YYYY-MM-DD format!
date: 2024-09-11
published: true
labels:
  - Questions and Answers
  - StackOverflow
---

<img width="300px" class="rounded float-start pe-4" src="../img/smart-questions/manual.jpg">

Photo by <a href="https://unsplash.com/@mattseymour?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Matt Seymour</a> on <a href="https://unsplash.com/photos/orange-and-red-plastic-pack-3ljBiiW5Chg?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>
  

## Developing the Right Approach to Questions

Asking a well-constructed question increases your chances of receiving well-constructed answers. Smart questions require careful consideration to avoid being seen as a waste of time. An observant, thoughtful, and eager-to-learn individual is less likely to be ignored in forums where respondents can choose which questions to answer. Following the approach outlined by Eric S. Raymond and Rick Moen in their ["How To Ask Questions The Smart Way"](http://www.catb.org/esr/faqs/smart-questions.html) guide, it is important to take these initial steps before asking your technical question:

1. Search archives of the forum you plan to post to or its mailing list.
2. Search the web ("Google is your friend").
3. Read the manual. 
4. Read an FAQ. 
5. Conduct inspection and/or experimentation.   
6. Ask a skilled friend.  
7. If you program, try reading the source code.

## Constructing the Question

It is important to ask your question in the appropriate place. This means choosing a forum where the question is on topic, deciding whether your question is suited for a technical or more general forum, and avoiding cross-posting to too many places. There a many forums dedicated to specific niches; [StackExchange](https://stackexchange.com/sites) is a good place to start if you are unsure where you might have the most success in getting an answer.

Next, make your subject header descriptive and specific. It should be clear what your problem is so that others with similar issues can find your post rather than creating a new one. Generally, the subject header should include an "object" that specifies the thing having the problem and a "deviation" that describes the unexpected output or behavior.

For the body of the message, proofread it to ensure it is clear, grammatically correct, and free of spelling errors. Provide a brief synopsis of the problem’s symptoms in chronological order and state your ultimate goal. Then, describe the step(s) where you are stuck. Ensure your question is specific but not overly verbose. In the context of code, hint at the problem respondents should look for. Include a snippet of your code, specifying the line(s) that failed and what you expected to see instead. If possible, provide a minimal test case with supporting code to illustrate the unexpected output or behavior. Lastly, avoid attaching images of your code since the amount of visible code is limited to the author’s screen size, and searching for specific text in images is difficult, making it harder to identify errors or typos.

## A Look at a Smart Question

Let's take a look at [an example](https://stackoverflow.com/questions/54695859/invalid-pointer-error-on-invoking-free-after-malloc-in-c) of a good question from StackOverflow, which reads:

---
> ##### Invalid pointer error on invoking free() after malloc in C
>
> I am doing very basic dynamic allocation practice in C and I came across this issue: when I am trying to call `free()` with the pointer returned by `malloc()`, I am getting Invalid pointer error during run time.
>
> When I remove `free()` from code, it works fine. The pointer that I am using is not modified anyhow after returned by `malloc` (except the casting). So that rules out some suggestion I found online. Below is my code:
> 
>
> ```c
> #include <stdio.h>
> #include <stdlib.h>
>
> #include <stdio.h>
> #include <stdlib.h>
>
> int main() {
>         int num = 0;
>         //printf("Enter a number: ");
>         //scanf("%d", &num);
>         char* p = (char*)malloc(16*sizeof(char));
>         printf("%p", p);
>         if(p) {
>                 p = "mark";
>                 printf("\n%s\n", p);
>                 free(p); //when removed no error
>         }
>         return 0;
> }
> ```
>
>Following is the error message:
>
>```c
> 0xa26010
> mark
> *** Error in `./a.out': free(): invalid pointer: 0x00000000004006b7 ***
> ======= Backtrace: =========
> /lib/x86_64-linux-gnu/libc.so.6(+0x777e5)[0x7fa968aed7e5]
> /lib/x86_64-linux-gnu/libc.so.6(+0x8037a)[0x7fa968af637a]
> /lib/x86_64-linux-gnu/libc.so.6(cfree+0x4c)[0x7fa968afa53c]
> ./a.out[0x40061a]
> /lib/x86_64-linux-gnu/libc.so.6(__libc_start_main+0xf0)[0x7fa968a96830]
> ./a.out[0x4004e9]
> ======= Memory map: ========
> 00400000-00401000 r-xp 00000000 08:03 6815746                            /home/kushal/Documents/GATE/prac_C/a.out
> 00600000-00601000 r--p 00000000 08:03 6815746                            /home/kushal/Documents/GATE/prac_C/a.out
> 00601000-00602000 rw-p 00001000 08:03 6815746                            /home/kushal/Documents/GATE/prac_C/a.out
> 00a26000-00a47000 rw-p 00000000 00:00 0                                  [heap]
> 7fa964000000-7fa964021000 rw-p 00000000 00:00 0 
> 7fa964021000-7fa968000000 ---p 00000000 00:00 0 
> 7fa968860000-7fa968876000 r-xp 00000000 08:03 39719295                   /lib/x86_64-linux-gnu/libgcc_s.so.1
> 7fa968876000-7fa968a75000 ---p 00016000 08:03 39719295                   /lib/x86_64-linux-gnu/libgcc_s.so.1
> 7fa968a75000-7fa968a76000 rw-p 00015000 08:03 39719295                   /lib/x86_64-linux-gnu/libgcc_s.so.1
> 7fa968a76000-7fa968c36000 r-xp 00000000 08:03 39714902                   /lib/x86_64-linux-gnu/libc-2.23.so
> 7fa968c36000-7fa968e36000 ---p 001c0000 08:03 39714902                   /lib/x86_64-linux-gnu/libc-2.23.so
> 7fa968e36000-7fa968e3a000 r--p 001c0000 08:03 39714902                   /lib/x86_64-linux-gnu/libc-2.23.so
> 7fa968e3a000-7fa968e3c000 rw-p 001c4000 08:03 39714902                   /lib/x86_64-linux-gnu/libc-2.23.so
> 7fa968e3c000-7fa968e40000 rw-p 00000000 00:00 0 
> 7fa968e40000-7fa968e66000 r-xp 00000000 08:03 39714844                   /lib/x86_64-linux-gnu/ld-2.23.so
> 7fa969046000-7fa969049000 rw-p 00000000 00:00 0 
> 7fa969064000-7fa969065000 rw-p 00000000 00:00 0 
> 7fa969065000-7fa969066000 r--p 00025000 08:03 39714844                   /lib/x86_64-linux-gnu/ld-2.23.so
> 7fa969066000-7fa969067000 rw-p 00026000 08:03 39714844                   /lib/x86_64-linux-gnu/ld-2.23.so
> 7fa969067000-7fa969068000 rw-p 00000000 00:00 0 
> 7ffcf8e4b000-7ffcf8e6c000 rw-p 00000000 00:00 0                          [stack]
> 7ffcf8f1d000-7ffcf8f20000 r--p 00000000 00:00 0                          [vvar]
> 7ffcf8f20000-7ffcf8f22000 r-xp 00000000 00:00 0                          [vdso]
> ffffffffff600000-ffffffffff601000 r-xp 00000000 00:00 0                  [vsyscall]
> Aborted (core dumped)
> ```
---
This constitutes a smart question. The user clearly identifies the "object" and "deviation," where the object is invoking `free()` after `malloc` and the deviation is the invalid pointer error. The user also succinctly describes the problem in the message body, outlining the source of the error and showing that they have inspected and experimented with the code, as well as searched online for suggestions. The error message provides additional context for the problem. As a result, the user receives a helpful answer with a suggested fix. The top-voted answer is as follows:

- You have a variable `p` that points to the memory returned by `malloc`. Then you change the variable p to point to the memory occupied by the string literal "mark". When you try to delete it, you are trying to `delete` the string literal.

  In short, the line `p = "mark"` is not doing what you think it's doing. It isn't copying that value into the memory returned from malloc.

  Try changing that line to `strcpy(p, "mark")` and I suspect things will start working better.

  (That being said, I shouldn't even mention `strcpy` because it's so unsafe and there are alternatives that will prevent buffer overrun problems. But that's a separate question, and there are a lot of discussions about it here on SO.)


## A Question to Improve

Now, let's take a look at [a not so smart question](https://stackoverflow.com/questions/48500558/python-making-a-project), which reads as follows:

---
> ##### Python: making a project
>
> hello i am new in python and i started learning from a book called "automate the boring stuff" and there was a project in it called Character Picture Grid and i did it but i think my code is little bit stupid and anyone tell me the right way to do this project ? :D thank you ^^
>
> code:
>
> ```python
> grid = [['.', '.', '.', '.', '.', '.'],
>     ['.', 'O', 'O', '.', '.', '.'],
>     ['O', 'O', 'O', 'O', '.', '.'],
>     ['O', 'O', 'O', 'O', 'O', '.'],
>     ['.', 'O', 'O', 'O', 'O', 'O'],
>     ['O', 'O', 'O', 'O', 'O', '.'],
>     ['O', 'O', 'O', 'O', '.', '.'],
>     ['.', 'O', 'O', '.', '.', '.'],
>     ['.', '.', '.', '.', '.', '.']]
>
> def x_y_1(grid):
> for y in range(9):
>     for x in [0]:
>         print(grid[y][x],end='')
> print(end='\n')
> def x_y_2(grid):
> for y in range(9):
>     for x in [1]:
>         print(grid[y][x],end='')
> print(end='\n')
> def x_y_3(grid):
> for y in range(9):
>     for x in [2]:
>         print(grid[y][x],end='')
> print(end='\n')
> def x_y_4(grid):
> for y in range(9):
>     for x in [3]:
>         print(grid[y][x],end='')
> print(end='\n')
> def x_y_5(grid):
> for y in range(9):
>     for x in [4]:
>         print(grid[y][x],end='')
> print(end='\n')
> def x_y_6(grid):
> for y in range(9):
>     for x in [5]:
>         print(grid[y][x],end='')
> print(end='\n')
> x_y_1(grid)
> x_y_2(grid)
> x_y_3(grid)
> x_y_4(grid)
> x_y_5(grid)
> x_y_6(grid)
> ```
---

The question has several issues. The subject header is vague and doesn’t indicate the specific problem or its causes. This lack of detail continues into the message body, which lacks error output, making it hard to pinpoint the issue. Additionally, the user doesn’t explain the ultimate goal or provide context about the project mentioned. This confusion is evident in the replies, including the following:

- "Could you please tell us what you want to do?"
- "If it's working, consider asking on codereview.stackexchange.com. Otherwise, question seeking for debugging help must include the desired behavior, a specific problem or error and the shortest code necessary to reproduce it in the question itself."

## Your Turn

Now that you have a foundational understanding of how to approach asking questions, it’s time to put this knowledge into practice. Following these guidelines won’t guarantee that you’ll get the exact answer you’re looking for, but adhering to these best practices will significantly improve your chances of receiving helpful responses. By reviewing these guidelines myself, I’ve gained insight into how to construct a good question and how neglecting these practices can make answering questions more difficult. Good luck!
