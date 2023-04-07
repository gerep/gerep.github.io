---
layout: post
title: "can you produce MU?"
date: 2019-06-11
categories:
---

This is a challenge from the book [Godel, Escher, Bach: An Eternal Golden Braid](https://www.amazon.com.br/Godel-Escher-Bach-Eternal-Golden/dp/0465026567).

You are given the string *MI* and you need, by following the rules, change it to *MU*.

#### Rules:

**#1**: If the last letter is *I*, you may add a letter *U* at the end.

**#2**: If you have M*x*, you may duplicate the *x*, like: *MIU* becomes *MIUIU*, *MUM* becomes *MUMUM*, *MU* becomes *MUU*.

**#3**: If *III* occurs, you may replace it with *U*, like: *MIII* becomes *MU*, *MUIIIU* becomes *MUUU*, *MIIII* becomes *MUI* or *MIU*; The reverse is not aplicable, you cannot turn a *U* into *III*.

**#4**: If *UU* occurs, you may drop it, like: *UUU* becomes *U*, *MUUUIIU* becomes *MIIU*

You do not need to apply the rules whenever possible but only when you judge necessary.

An example:

```
Given MI
Rule 2: MII
Rule 2: MIIII
Rule 1: MIIIIU
Rule 2: MIIIIUIIII
Rule 3: MIUUI
....
```
