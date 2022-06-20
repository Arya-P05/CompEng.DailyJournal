---
layout: post
title: Specifics About Computer Storage
---

### Storage Mediums in Computers Continued

- What’s the access time for a hard drive:

  - Around 10 milliseconds

- **The time required to access DRAM is around 50 ns (nanoseconds) - about 180,000 times as fast**

- Memory vs Storage:

  - HDDs are for local storage of all of the information (and applications) that a computer may need
  - RAM is the working memory that contains the things on which the computer is working _at the time_

    - Data files that are being processed
    - Applications that are presently loaded

  - **The more RAM you have, the less often you need to load information from the HDD - Your computer works faster**

- The physical Basics of Dynamic RAM:

  - RAM is composed of densely-packed transistors and capacitors. Transistors control the flow of information and the capacitor contains the information
  - Each bit is stored in a capacitor
  - Reading or writing the bit requires transistors. (Switches that can be turned on or off)
  - Capacitors store a small amount of electrical energy, but this energy slowly dissipates

  - **DRAM must be constantly refreshed, or it is lost.**

- How is DRAM Rewritten:

  - In a DRAM chip, each bit of memory data is stored as the presence or absence of an electric charge on a small capacitor on the chip. Each memory refresh cycle refreshes a succeeding area of memory cells, thus repeatedly refreshing all the cells in a consecutive cycle.

- Static RAM:

  - Static RAM has a flip-flop composed of extra transistors that mean it never needs to be refreshed, as long as power isn’t interrupted
  - The lack of a refresh requirement means that it can be accessed much more quickly
  - The downside is that the additional transistors cost money and space
  - Modern computers tend to use SRAM for the CPU cache
  - Things that we need now, the things it's working at that very second

  - **The typical access time for SRAM is about 10 ns (nanoseconds)**

- Upgrading RAM:

  - Memory upgrades are an inexpensive way to improve computer performance.
  - Best option to replace RAM
  - There are lots of options for RAM modules
  - You can make sure that the RAM you purchase is suitable:
    - Match all parameters (RAM Speed Mhz, Latency - Lower the better)
    - Don’t exceed published limitations of OS, MoBo
  - Or, use a website like [www.crucial.com](http://www.crucial.com) to match your RAM requirements to your machine
  - [Amazon.ca](http://Amazon.ca) can help with price comparisons

  - Make sure quotes are in $CAD

- Can ROM be updated:

  - Non-volatile does not mean permanent

  - Your BIOS can be updated on your computer (or it can be restored)

- Flash Memory Application Examples:

  - SD cards
  - Phone memory

  - External SSDs

- How long will it last?

  - Flash memory stores data for a long time without losses. (Up to 10 years)
  - Unlike HDDs, SSDs wear out when data is regularly overwritten

  - A given bit on an SSD can wear out after being overwritten as few as 1000 times

**Parameters For Each Solid State Drive:**

| Parameters        | DRAM  | SRAM  | Flash |
| ----------------- | ----- | ----- | ----- |
| Volatile?         | Yes   | Yes   | No    |
| Refresh Required? | Yes   | No    | No    |
| Access Time       | 50 ns | 10 ns | 10ns  |
