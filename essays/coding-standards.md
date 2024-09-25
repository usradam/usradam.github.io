---
layout: essay
type: essay
title: "Writing Clean Code"
# All dates must be YYYY-MM-DD format!
date: 2024-09-24
published: true
labels:
  - Coding Standards
  - ESLint
---

<div align="center">
    <img width="900px" class="rounded" src="../img/coding-standards/code_quality.png" alt="xkcd: Code Quality">
</div>

Writing clean code involves ensuring readability and maintainability, whether for yourself in a solo project or for a group project with other developers. One way to ensure clean code is by setting coding standards. These are essentially guidelines put in place so that you can follow certain coding conventions. These conventions can be self-imposed, or you can use code analysis tools (also known as a [lint](https://en.wikipedia.org/wiki/Lint_(software))) to flag stylistic errors and evaluate patterns in code.

## My Introduction to Coding Standards

My first encounter with a strict set of coding standards was in my ICS 212 (Program Structure) class at UH Manoa. From the onset, it was emphasized that we should follow an established class coding style. This helps maintain readability across all students' code and encourages us to adhere to conventions that are personally beneficial as well. Some of these conventions are trivial, such as using 4 spaces for indentation, but there are also more practical applications of styling. This includes not using single-letter variables except in loops and ensuring that function names and arguments are self-explanatory. For example:

Good
```c
int number = 5;
int result;

result = is_odd(number);
```

Bad
```c
int a = 5;
int a2;

a2 = aa(a);
```

We also had to include file header comments at the beginning of each source and header file, alongside function header comments. This helps us understand the purpose of the overall program and each function. An example of a source file with the header and function comments would look like this:

```c
/*****************************************************************
//
//  NAME:        Jane Doe
//
//  HOMEWORK:    1
//
//  CLASS:       ICS 212
//
//  INSTRUCTOR:  John Doe
//
//  DATE:        May 18, 2055
//
//  FILE:        hw1main.c
//
//  DESCRIPTION:
//   This file contains the driver and the user-interface functions
//   for Homework 1 - the temperature conversion program
//
//
****************************************************************/

#include <stdio.h>
#include <stdlib.h>
 ...

int getinput(...);
void convertFtoC(...);
 ...

/*****************************************************************
//
//  Function name: getinput
//
//  DESCRIPTION:   A userinterface function
//                 This function obtains the values of the ... from the user
//
//  Parameters:    count (int) : contains the number of arguments
//                               which will be processed
//
//  Return values:  0 : success
//                 -1 : the value was not found
//
****************************************************************/

int getinput(int count)
{
    int buffer, i;

    for (i = 0; i < count; i++)
    {
        if (...)
        {
            printf(...);
        }
    }
}
...
```

Beyond this, we were provided with a customized version of Google's C/C++ self-check Python script called [cpplint.py](https://github.com/google/styleguide/blob/gh-pages/cpplint/cpplint.py). The script can check C/C++ code and suggest potential coding style violations according to Google's style guide. Though following the style guide was cumbersome at first, overall, this introduction to coding standards helped me write code more thoughtfully and consider readability as one of the main criteria for writing clean code.

## My Introduction to ESLint

<div align="center">
    <img width="330px" class="rounded pe-4" src="../img/coding-standards/eslint-logo.svg" alt="ESLint Logo">
</div>

In my ICS 314 (Software Engineering) class, we have so far focused on writing TypeScript code and were introduced to ESLint, a code analysis tool that identifies violations of specific coding styles and conventions. While ESLint primarily serves as a linting tool for the ECMAScript standard of JavaScript, it can also process TypeScript with the help of a plugin or a source-to-source compiler.

Like my introduction to coding standards in ICS 212, using ESLint felt tedious at first. However, I have come to appreciate the utility of the tool in ensuring consistency in my TypeScript code. For example, ESLint checks for issues like unused variables and missing `return` statements in property getters (you can find out more about the rules enforced [here](https://eslint.org/docs/latest/rules/)). In the long run, this tool will not only help maintain a consistent coding style but will also aid in avoiding bugs, ultimately leading to cleaner, more maintainable code.

## Future Use 

In the future, I plan to use coding style guidelines as valuable tools for writing clean and maintainable code. Sticking to these guidelines will not only improve my understanding of the code I write but also make it easier for other developers to read and collaborate on my projects. While it can be tempting to go with the flow and overlook certain conventions, using linting tools offers essential feedback to ensure consistency across the codebase. Ultimately, embracing these practices will lead to higher-quality software and a more efficient development process.
