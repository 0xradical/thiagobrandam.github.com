---
layout: post
published: false
title: "How to modify readonly windows .isos in Mac OS"
date: 2013-01-07 19:04
comments: true
categories: [Disk Utility, Mac OS, Windows, hdiutil]
---

If you end up with a readonly windows .iso that you somehow
need to get its contents modified, you can do it easily
if you use Mac OS.

First, fire up Disk Utility and create a New Image.
This new image should be in the MS-DOS (FAT) format
and be a read/write disk image. The size should be at least 2.5 GB.
Fill in the "Save As" field and click "Create".
It will create a blank .dmg file.

Now, this image should be blank, but writable. Mount the
blank image, mount the windows .iso and
copy the original .iso contents into the blank image, modifying
what needs to be modified.

After these steps, fire up Terminal and enter:

hdiutil makehybrid -iso -joliet -o windows_iso_with_modified_contents.iso newly_created_dmg.dmg

This windows .iso should be ready to go, if you didn't screw up anything.
