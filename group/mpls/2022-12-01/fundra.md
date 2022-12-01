---
title: A page there I take a look at "back to MPLS approach"
description: Describing label stack and functions
published: true
date: 2022-12-01T20:42:54.976Z
tags: 
editor: markdown
dateCreated: 2022-11-30T14:06:48.460Z
---

# Back to traditional MPLS design 
Recent discussion have brought the argument the MNA should be be done "the MPLS way", one way that be tested is model it the same way as we did with multi-cast, i.e. dual labels, one for forwarding and one "modifier" that tells which action(s) that should be performed.

# MNA Labels
Tentatively the SPL allocation for MNA are abandoned, instead we use labels from the labels we normally allocate for LSPs, by signaling or configuration.

## The idea
The idea is that an LSP has two different lables that gives the same forwarding result,

- one label a is a "normal" forwarding label, it is swapped and forwarded by every transit node, PHPed by the pen-ultimate node, and the egress LER sends original packet towards is destination.

- one label is a that has an MNA FEC, it will be swapped and forwarded as the normal forwarding label, but it also tells any MNA capable node to go look at the next label in the stack. 

  - The next the next LSE identify what actions to perform and how to find reuquired ancillary data

## Forwarding level Label stack example


       normal              MNA case
     +--------+           +--------+
     |   L1   | IP FEC    |  M1    | MNA FEC
     +--------+           +--------+
     |payload |           |Modifier|
     +--------+           +--------+
                          |  PSD   |
                          +--------+
     
     
     
     
     
~~~    
  Normal      MNA case
+--------+   +--------+
| IP FEC |   | MNA FEC|
+--------+   +--------+  

 0                   1                   2                   3
 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+ Label
|                Label                  | Exp |S|       TTL     | Stack
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+ Entry

~~~
text

~~~
    normal
+--------
~~~