# Crack the Hash Challenge

[Room Link](https://tryhackme.com/room/crackthehash)

### Task 1: Level 1

Your mission is to break the provided hashes in Level 1. Let's get started!

Don't forget https://crackstation.net/ This can aid the process in level 1! 

1. **Hash:** 48bb6e862e54f2a795ffc4e541caed4d  
   The hint indicates this is an MD5 hash. You can use the following command to crack it:  
   `hashcat -m 0 hash1_1.txt /usr/share/wordlists/rockyou.txt --show`  
   > **easy**

2. **Hash:** CBFDAC6008F9CAB4083784CBD1874F76618D2A97  
   The hint suggests this is a SHA hash. After testing various options, I determined it’s a SHA1 hash.  
   Command: `hashcat -m 100 hash1_2.txt /usr/share/wordlists/rockyou.txt --show`  
   > **password123**

3. **Hash:** 1C8BFE8F801D79745C4631D09FFF36C82AA37FC4CCE4FC946683D7B336B63032  
   This one seems to be a SHA256 hash. Command used to crack the hash:  
   `hashcat -m 1400 hash1_3.txt /usr/share/wordlists/rockyou.txt --show`  
   > **letmein**

4. **Hash:** $2y$12$Dwt1BZj6pcyc3Dy1FWZ5ieeUznr71EeNkJkUlypTsgbX1H68wsRom  
   The hint confirms this is a bcrypt hash.  
   Command: `hashcat -m 3200 hash1_4.txt /usr/share/wordlists/rockyou.txt`  
   > **bleh**

5. **Hash:** 279412f945939ba78ce0758d3fd83daa  
   The hint indicates this is an MD4 hash. While hashcat couldn’t crack it, I used an online tool for this one: [MD4 Decrypt](https://md5decrypt.net/en/Md4/).  
   > **Eternity22**

### Task 2: Level 2

The difficulty increases here. All answers can be found in the classic [rockyou](https://github.com/brannondorsey/naive-hashcat/releases/download/data/rockyou.txt) password list.

You’ll likely need to use hashcat for this task. For additional reference, the [hashcat example page](https://hashcat.net/wiki/doku.php?id=example_hashes) can be helpful.

1. **Hash:** F09EDCB1FCEFC6DFB23DC3505A882655FF77375ED8AA2D1C13F640FCCC2D0C85  
   The hash appears to be a SHA256 hash.  
   Command: `hashcat -m 1400 hash2_1.txt /usr/share/wordlists/rockyou.txt`  
   > **paule**

2. **Hash:** $6$aReallyHardSalt$6WKUTqzq.UQQmrm0p/T7MPpMbGNnzXPMAXi4bJMl9be.cfi3/qxIf.hsGpS41BqMhSrHVXgMpdjS6xeKZAs02.  
   **Salt:** aReallyHardSalt  
   **Rounds:** 5  
   The hint indicates this is an NTLM hash.  
   Command: `hashcat -m 1000 hash2_2.txt /usr/share/wordlists/rockyou.txt`  
   > **n63umy8lkf4i**

3. **Hash:** e5d8870e5bdd26602cab8dbe07a942c8669e56d6  
   **Salt:** tryhackme  
   This appears to be a SHA-512 (Unix) hash.  
   Command: `hashcat -m 1800 hash2_3.txt /usr/share/wordlists/rockyou.txt`  
   > **waka99**

4. **Hash:** e5d8870e5bdd26602cab8dbe07a942c8669e56d6  
   **Salt:** tryhackme  
   The hint suggests this is an HMAC-SHA1 hash.  
   Command: `hashcat -m 160 hash2_4.txt /usr/share/wordlists/rockyou.txt`  
   > **481616481616**

We have now become hash crackers -_-
