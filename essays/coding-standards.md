---
layout: essay
type: essay
title: "Writing Clean Code"
# All dates must be YYYY-MM-DD format!
date: 2024-09-23
published: false
labels:
  - Coding Standards
---

<img width="200px" class="rounded float-start pe-4" src="../img/difficulty/degree_difficulty.jpg">

Writing clean code invovlves ensuring readability and maintainability, either for yourself in the case of a solo project or for a group project with other developers. One way to ensure clean code is by setting coding standards. These are essentially guidelines put in place so that you can follow certain coding conventions. These conventions can be self-imposed or you can use code analysis tools (lint) to flag stylistic errors and evaluate patterns in code.

## My Introduction to Coding Standards

My first encounter with a strict set of coding standards was in my ICS 212 (Program Structure) class at UH Manoa. From the onset, it was emphasized to follow an established class coding style. This helps to maintain readability across all students' code and forces us to adhere to conventions that are personally beneficial as well. Some of these conventions are trivial such as using 4 white spaces for indentation, but there were some more practical applications of styling. This includes not using single letter variables except for loops and ensuring that function names and arguments are self-explanatory. For example:

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

We also had to include file header comments at the beginning of each source and header file alongside function header comments. This helps us understand the purpose of the overall program and each function. An example of asource file with the header and function comments would look like this:

```c
/*****************************************************************
//
//  NAME:        Adam Graham
//
//  HOMEWORK:    1
//
//  CLASS:       ICS 212
//
//  INSTRUCTOR:  John Doe
//
//  DATE:        May 30, 2024
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

Beyond this, we were provided with a customized version of Google's C/C++ self-check Python script called [cpplint.py](https://github.com/google/styleguide/blob/gh-pages/cpplint/cpplint.py). The script can check C/C++ code and suggest potential coding style violations according to Google's style guide. Overall, this introcution to coding standards helped me to write code more thoughtfully and to think about readability as one of the main criteria to follow for writing clean code.

## My Introduction to ESLint

In my ICS 314 (Software Engineering) class, we were introduced to ESLint, 

## Future Use 

So in the end, we realize that all engineering and programming is there for a reason - to serve human needs. Maybe that's why those things are difficult, because they both involve humans and are for humans.

Relationships, regardless if they're romantic or not take work. Humans are fickle creatures and relationships can come and go with the wind. To properly maintain something over time requires work. Family takes work. Marriage takes work. We live to figure out what works and what doesn't and hope that as we move forward we're improving.

Relationships have always been difficult, and by nature will continue to be so.
