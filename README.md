# cxxmgr - C/C++ Project Manager

Tired of the weird CMake syntax? Want something simple and fast? Well, say no more!
Welcome to cxxmgr (Read: seexmanager), a simple, featureless solution to managing
gcc dependencies and compiler flags.

## Installation

To install cxxmgr, simply download `cppcr` or `ccr` (depending on your needs),
    and put it somewhere in your `$PATH`. That could be `.local/bin`, `.scripts`,
    or whatever else you want, even `/usr/bin`, but that's not recommended.

## How to use

To use cxxmgr, you need a `cxxproj` file in your source folder. That file is going
to be parsed by a shell script and its contents put in as arguments for `gcc` or
`g++`.

After that's done, simply run `cppcr` or `ccr` and your program will be compiled
and run.

## cxxproj Syntax

```
-SOURCE
src/main.cpp

-COMMANDS
pkg-config gtkmm-3.0 --cflags --libs

-LIBS
glibmm-2.4
gtkmm-3.0
```

- -SOURCE

anything put in here will be copied as-is to the compiler, so, in here, you can put
source files (`src/main.cpp`, `my-cool-project/main-cplusplus-file.cpp`, ...) and
other custom arguments such as `-Wall`, if you want to.

- -COMMANDS

anything put in here will be run and the results will be copied into the compiler.
This is useful for libraries like `gtkmm` that have a lot of dependencies and you
can't be bothered to write out all of them. Instead, you simply put in
`pkg-config gtkmm-3.0 --cflags --libs` and it works perfectly!

- -LIBS

Libraries, as the name suggests. Writing an `ncurses` app? Put in `ncurses`!
OpenGL? `GL`, `GLEW` and/or `glfw`!

- And that's it!

I started writing these for personal use because I was too stupid to use Cmake. It
doesn't have pretty much any features, is weird to install, and was initially
posted by an account that was 5 days old. If you want to use it, go ahead, I'm glad
you like it. If not, I definitely understand why :b!
