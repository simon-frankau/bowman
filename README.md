# The Sherwood Bowman 68000 Single Board Computer

The Sherwood Data Systems Bowman was a 68000-based single-board
computer from the 1980s.

It's pretty obscure; I could find very little about it on the
internet, so I decided to document it. This repo contains scans of the
manuals I have, and the EPROM monitor it runs.

I *did* however, manage to find an advert for it, to give you an idea
of the context:

![An advert from Sherwood Data Systems Ltd. for the SDS Archer and SDS
Bowman](./advert.png)

(Taken from
[https://www.worldradiohistory.com/UK/Wireless-World/90s/Wireless-World-1990-11.pdf](https://www.worldradiohistory.com/UK/Wireless-World/90s/Wireless-World-1990-11.pdf)).

## Background

In 1995, I had a summer job working at MRG Systems in Stroud, UK. They
developed teletext systems and display systems used in betting
shops. I believe their custom hardware was 68k-based. At the end of my
job, I rather cheekily asked if they had any old, unused hardware
going spare, and thus managed to score this (then obsolete) board. I
had some fun working with 68K assembly, and cross-assembling for it,
with the aim of producing a very basic LISP (a language I was rather
interested in, at the time).

I find it a little interesting/scary, since it's a single unenclosed
PCB with a mains PSU and all the logic on the same board. While the
12V to 5V step-down is switch-mode, the main power supply is linear,
so it's got this huuuge transformer slapped onto one end of a chunky
PCB. It's a crazy design!

## Contents

The board came supplied with a "Kaybug" monitor (which at least has a
few more hits on Google). When I received the board, it came with
three manuals - one for the board itself, and two for two different
versions of Kaybug. The board manual includes schematics on fold-out
A3 sheets. I've organised this content into the repo as follows:

 * TODO - manual scans, ROMs

## TODO: EEPROM disassembly?
