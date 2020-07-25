---
layout: post
title: A Scary Situation in Linux
---
The `ext4` filesystem that Linux uses is usually quite reliable, but as with all filesystems, it doesn't work too well when your computer crashes more than once.  This is because `ext4` is a journaling filesystem, which means that Linux doesn't write changes made to files right away, instead storing them in the RAM.  If the computer happened to be making changes to system files (like installing software), the result could be that the system files become corrupted, resulting in a bootable, but unusable, state.

## Symptoms of a corrupted filesystem

In Linux, you will see a black screen with a few lines of white text.  The rather cryptic instructions don't help waylayers, but the instructions are actually mildly helpful.  It probably looks somewhat like

```
/dev/s(x#): UNEXPECTED INCONSISTENCY; RUN fsck MANUALLY
```

where (x#) is the partition where your system is stored.

You'll usually be dropped inside a basic shell with root access.  If it prompts you for the root password and you don't know it, contact a person who does know it.  Assuming that you manage to obtain root access, run `fsck /dev/s(x#)`.  Answer 'y' to all of the questions and then reboot.

## Causes

There are many different causes of a corrupted filesystem.  One of them is a loss of power without a proper shutdown, like during a power outage.  This is probably the cause of most corruptions.  Another other one is a disk drive going bad, which at that point it's recommended to change out the disk.  The last one, which comes from the nature of `ext4`, is due to memory corruption.  As `ext4` stores changes in RAM, it will dutifully write all changes made to the filesystem, even if these changes were corrupted, resulting in an unstable system.  If you find yourself looking at the black screen a few too many times, consider swapping memory sticks or replacing a hard drive.
