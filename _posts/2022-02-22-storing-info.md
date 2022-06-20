---
layout: post
title: Storing Information Lesson
---

### Introduction to how we store information | Day to Day Storage

**Hard Drives - The Basics:**

- Non-volatile magnetic storage of information (stores data w/ and w/out power)
- Each bit is defined by the magnetic orientation of a specific part of the disc.
- When we write to the disc, a strong magnetic field physically aligns the magnetic material
- When re-read, we simply determine the orientation of the magnetic material for that physical location
- The reading process is based on the force that a permanent magnet experiences
- Magnetic 1s and 0s
  - .004 mm can hold 6 bits of data (can be compressed into that space - nano)

**The History of Hard Drives:**

- The idea is not new: the first magnetic storage of info was on wires - 1888
- Tape recorders (audio) were developed in 1928.
- In 1954 IBM invented the hard drive:
  - $50,00 (500K in today's terms)
  - As big as a refrigerator
  - Weighed about 1 ton
  - 5 MB
- Our need for more storage seems to be increasing every day as technology improves.

**Videos:**

<iframe width="560" height="315" src="https://www.youtube.com/embed/wteUW2sL7bc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<iframe width="560" height="315" src="https://www.youtube.com/embed/p3q5zWCw8J4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

**Types of Hard Drive Connectors:**

- IDE
- SCSI
- SATA

**Data Organization:**

- Partitioning
- File Systems

**Partitioning:**

- Hard drives can be divided into two or more partitions:
- This can help with data organization and/or multiple operating systems on the same computer
- Various utilities can be used to partition drives
  - Lixus will automatically put partitions on our hard drives during installation

**Windows File Systems:**

- File systems define how data is stored on a drive
- FAT - “File Allocation Table”
- FAT16
- FAT32 - up to 2 TB
- NTFS - NT File System - much much more.
- There is no reason to use other than NTFS in a modern build.

**File Systems and Formats:**

- macOS: APFS
- Android & PC: NTFS
- Linux: Ext4

**Additional Information About Hard Drives:**

- There are billions of hard drives currently in use
- Moving parts = finite lifetime
- Magnetic sectors are vulnerable to destruction
- The actuator arm can only be in one place at a time:
  - It takes time to read and write from the hard drive.
- Hard drives are large, heavy, fragile, and slow.
