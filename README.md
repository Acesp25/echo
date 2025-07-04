# Simple FreeBSD Echo Driver
This is a slight modification/extension of a simple FreeBSD echo driver written in C. The 
original, written by Murray Stokely, Søren (Xride) Straarup, and Eitan Adler can be found 
here: https://docs.freebsd.org/en/books/arch-handbook/driverbasics/#driverbasics-char

I will be modifying it how I see fit as I learn about proper driver implementation methods.

## How to compile and run?
1. Clone repo into a directory of your choice
2. cd into repo, do ```make```
3. Load the module: ```kldload -v ./echo.ko```
4. Test the module by:
```sh
echo -n "Hi :D" > /dev/echo 
cat /dev/echo
```
6. Unload the module: ```kldunload echo```

## Current Fixes
Implemented QUIESCE event to handle soft and hard unloading. 
