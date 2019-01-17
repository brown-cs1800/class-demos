# Hashcast Demo Cracking eHarmony Passwords

## Setup

1. Install hashcat

How to setup hashcat?

You can use legacy-hashcat (https://github.com/hashcat/hashcat-legacy) which doesn’t have GPU. You can clone the git repo and follow along or try this demo on your own.

2. Get a dictionary file: I used rockyou.txt (https://wiki.skullsecurity.org/Passwords) which lists most common passwords from the RockYou hack a couple years back (https://techcrunch.com/2009/12/14/rockyou-hack-security-myspace-facebook-passwords/).  

## eHarmony Demo

In 2012 eHarmony was hacked and the hashed passwords were publicly published. As a CS166 student you can now hack like the pros and recover some eHarmony passwords using hashcat.

Unlike the previous examples, this takes a while to recover all the passwords:

http://www.adeptus-mechanicus.com/codex/hcateasy/eharmony.hash

Weird things about this set:
For some reason eHarmony decided to store all the passwords uppercase. So this eliminates a lot of variety 
eHarmony uses MD5: so try -m 0

Recover passwords of length 6:
./hashcat-cli64.bin -m 0 -a 3 -1 ?u?d --remove eHarmony.hash ?1?1?1?1?1?1?1

-m 0: This is an md5 hash

?u?d: Upper case character or number

?1?1?1?1?1?1: 6 letter (Min length required)

Dictonary Attack:
./hashcat-cli64.bin -m 0 eHarmony.hash rockyou.txt 
