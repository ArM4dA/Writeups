# Write-Up
## Challenge : Take It Easy
  Difficulty : Easy

### Step - I : 
  Unzip the challenge file to get getkey.txt and a password protected zip TRYME.zip.<br>
  To get the password of the zip you solve a simple RSA problem by this [exploit](https://github.com/ArM4dA/Writeups/blob/main/Key/exploit.py).<br>
  This is also known as **low exponent attack**.
### Step - II :
  With the password you can unzip TRYME.zip and find the chall file.<br>
  The **flag** is divided into chunks of four and each chunk is XORed with next of the next chunk `(chunk + 2)th chunk`.<br>
  As flag is in usual format, you already know first 2 chunks `dark` and `CON{` and the XORed ciphertext chunks are also given.
  By XOR property, if `chunk1 ^ chunk3 = ct1` then `chunk3 = ct1 ^ chunk1`. In this way all chunks can be recovered.<br>
  The [exploit](https://github.com/ArM4dA/Writeups/blob/main/Challenge/exploit.py) is provided here.
  
## Flag : 
  darkCON{n0T_Th@t_haRd_r1Ght}
