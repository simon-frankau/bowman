># The Sherwood Bowman 68000 Single Board Computer

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

 * [bowman](./bowman) - A scan of the main manuals, minus the
   schematics.
 * [kaybug-1.0](./kaybug-1.0) - A scan of the Kaybug version 1.0
   manual.
 * TODO - further manual scans, ROMs

## Notes

To me, the board looks pretty fully-featured, and doesn't cut corners
on optional features - supporting external DTACK (with bus timeout),
and vectored interrupts, a watchdog timer and power failure
circuitry. The external bus access lines are properly
buffered. There's battery-backed RAM. Plenty of jumpers for
configurability. It feels "well-engineered" and rather unlike the "if
in doubt, leave it out" kind of design I've seen with some other 68K
designs, such as the early Macs (with their Woz-style minimisation).

AFAICT, not all components are properly identified on the schematic,
the default jumper configuration isn't clear, and the circuit
descriptions in the manual leave you flipping back and forth through
the schematics to find the relevant circuit.

It's fun to see that the demuxing of the address bus into RAS and CAS
is done for odd and even bits of the address bus, rather than low and
high parts. I hadn't really thought before about how this is a
perfectly valid way to do it (and necessary to support different DRAM
sizes)!

I'm thinking of building my own 68000 board with DRAM, so it was
interesting to see how simply the RAS/CAS and refresh circuitry are
implemented, even if this is because they use DTACK rather than try to
squeeze between memory accesses. Not a PAL or GAL in sight.

## TODO: EEPROM disassembly?
