# C++ Notes

This document contains my notes for C++. 
Most of this comes from either googling or from (C++ Tutorial for Complete Beginners)[https://www.udemy.com/course/free-learn-c-tutorial-beginners/], which is a free Udemy course by John Purcell.

## Getting Started

### C++ Pros and Cons

Pros of C++:

- Very Fast
- Low-level/hardware access
- Can get a lot of processing done in a short time
- Good for high-end games, AI, device drivers
- Pushes you to understand your computer
- Badge of honor!

Cons of C++:

- Challenging to learn
- Easy to introduce terrible bugs
- Often time-consuming
- Not truly platform independent

### Compilers

- GNU G++/GCC
- MinGW
- Visual C++ compiler

### IDE

- Eclipse CDT
- Visual C++
- Codeblocks
- Emacs, VIM, etc.

### Setup and Installation

- The software to install depends on the operating system and personal preferences.

## Basic Syntax

### Hello World

This very simple program prints out "Hello World!"

```
include <iostream>
using namespace std;

int main() {
  cout << "Hello World!" << endl;
  return 0;
}
```

### Output

- cout outputs the text
- endl ends the line
- several pieces of text can be included in one cout statement

```
cout << "text" << endl;

cout << "Banana. " << "Kiwi. " << "Orange." << endl;
```

- flush outputs the text, but doesn't create a line feed

```
cout << "more text" << flush;
```
