---
platform: https://overthewire.org/wargames/bandit/bandit2.html
level: 1
date: 2026-06-27
Author: Pasan Sanjana
os: Kali Linux
tags:
  - bandit
  - ssh
  - linux-basics
  - Write-Ups
  - OverTheWire
related:
  - bandit-overview 
  - bandit1
Status: Done
---
---
## Goal

Find the password for bandit1, stored on the bandit1 server.

## Recon

To solve this task need to use two commands 

`ls` - for list files directories 
`cat` or `tac` - to read the files 

```shell
ssh bandit1@bandit.labs.overthewire.org -p 2220
# password: password from bandit0-1

ls 
cat ./- 

```

> Output:


```shell

bandit1@bandit:~$ ls 
- # - (file name is -)
bandit1@bandit:~$ cat ./- # with file name '-' cannot use cat command as usual need to use ./ before the name 

PK8fYLZg2hnHSz83plBL1iEPKdD3QToB #password

bandit1@bandit:~$ tac ./-

PK8fYLZg2hnHSz83plBL1iEPKdD3QToB

bandit1@bandit:~$ 

 
```

> [!note]
> The `-` file  in bandit1's home directory contains the bandit2 password.

## Answer 

Password for bandit2: `PK8fYLZg2hnHSz83plBL1iEPKdD3QToB` 