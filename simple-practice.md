Reverse Basics - A Simple Practice for Reverse Engineering
==========================================================
Introduction
------------
In this post, I will explore the basic concepts of reverse engineering by reversing a simple crackme.

The crackme used in this tutorial is from [hacking1now](https://sites.google.com/site/hacking1now/crackmes) course attachment. As my previouse post about background knowledge of Assembly and Disassemblers which are required to understand for this post. I will use IDA Disassembler as it is the most powerful disassembler exists in the market.

Reversing in Action
-------------------
Load file in IDA Pro. After that, run the application independently like a normal application not under debugger and feed some garbage value and note the message that we get.

![Alt text](re_simple1.png)

In the picture the crackme is poping up some messages on invalid input. The string "Invalid! Username Length" or "Invalid! Password Length" is an important hint as we can find these string in IDA Pro - I will open each function and look for the magic string i.e "Invalid! Password Length". Continue with the process until we can find it:

![Alt text](re_simple2.png)

Now, start to backtrace and find out the starting point of string matching:

![Alt text](re_simple3.png)


