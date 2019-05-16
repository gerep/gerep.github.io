---
layout: post
title: "hard link soft link"
date: 2015-02-06
categories:
---
The **ln** command is responsible for creating links.

If no option is used a **hard link** will be created:


```
ln file1 file2
```
      
This command will create a **hard link** called **file2**.

Hard links doesn't have any aparent difference when using the ls command.

Use the option **-l** (long) with the **ls** command and the number 2 will appear after the permissions and this number is the amount of hard links:


```
-rw-r--r-- 2 gerep users 0 07.02.2015 00:46 arquivo1
-rw-r--r-- 2 gerep users 0 07.02.2015 00:46 arquivo2
```
      
Using `ls -i file1 file2` will show something like this:


```
6817649 file1  6817649 file2
```
      
Those numbers are the inode and both files are sharing the same one.

Any changes on file1 will happens on file2 and vice-versa but if one is removed the other isn't.

**Hard links** can't be created for directories, between particions or file system.

**Soft links** can be created for directories, between particions or file system.

Use the options **-s** with the ln command to create a soft link:


```
ln -s file1 file2
```
      
Using the option **-l** (long) will show the letter **l** before the permissions:


```
-rw-r--r-- 1 gerep users 8 07.02.2015 00:41 file1
lrwxrwxrwx 1 gerep users 5 07.02.2015 00:41 file2 -> file1
```
      
file2 is now showed as a link and the amount is still 1.

The inode value is different, using ls -i file1 file2:


```
6817649 file1  6816910 file2@
```
      
Any changes will be applied in both files but if one is deleted the other one becomes invalid.