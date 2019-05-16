---
layout: post
title: "secure copy"
date: 2015-03-17
categories:
---
The scp command allows file transfers between hosts via ssh, offering the same level os security and authentication method.

Local -> Remote


```
$ scp file.txt user@host:/home/user/remote-directory/
```
      
Multiple files: Local -> Remote


```
$ scp file.txt file2.txt user@host:/home/user/remote-directory/
```
      
Remote -> Local


```
$ scp user@host:/home/user/remote-directory/file.txt /home/user/local-directory/
```
      
Multiple files: Remote -> Local


```
$ scp user@host:/home/user/remote-directory/\{file.txt, file2.txt\} /home/user/local-directory/
```
      
Directory


```
$ scp -r /home/user/local-directory user@host:/home/user/remote-directory/
```
      
Remote -> Remote


```
$ scp user@host:/home/user/remote-directory/file.txt \ another-user@another-host:/home/another-user/remote-directory
```
      
Port


```
$ scp -P 13579 file.txt user@host:/home/user/
```
      
scp uses Triple-DES by default to encrypt the data being transfered.Some tests show that using Blowfish is faster.


Use the option **-c**


```
$ scp -c blowfish file.txt user@host:/home/user/
```
      
Use the option **-C** to compress


```
$ scp -C file.txt user@host:/home/user/
```
      
As expected it is possible to combine the options:


```
$ scp -P13579 -C -c blowfish file1.txt user@host:/home/user/
```
      