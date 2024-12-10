
**Description**:
Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/37821/` ([link](https://jupiter.challenges.picoctf.org/problem/37821/)) or http://jupiter.challenges.picoctf.org:37821

**Hint**:
Never trust the client.

**Thought Process:**
Let's have a look at what the source code looks like and possibly search for any verification js or something, and voila! Did find it. Now, I worked towards decoding it as follows:
The largest size of the password can be `split*8 = 32`. 

Let's create some gaps:
```
_ _ _ _ _ _ _ _ _ _  _  _  _  _  _  _  _  _  _  _  _  _  _  _  _  _  _  _ 
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27
 _  _  _  _
28 29 30 31 
```
The reason why i've left 31 gaps is cause in binary 0-31 is 32.

According to `if (checkpass.substring(0, split) == 'pico')`, position `0 to 3` (substrings consider first number to last number -1 and split=4 so 0-3) should be `pico`
Let's fill the gaps:
```
p i c o _ _ _ _ _ _  _  _  _  _  _  _  _  _  _  _  _  _  _  _  _  _  _  _ 
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27
 _  _  _  _
28 29 30 31 
```

According to `if (checkpass.substring(split*6, split*7) == 'a3c8')`, position `24 to 27` should be `a3c8`
Let's fill the gaps:
```
p i c o _ _ _ _ _ _  _  _  _  _  _  _  _  _  _  _  _  _  _  _  a  3  c  8 
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27
 _  _  _  _
28 29 30 31 
```

According to `if (checkpass.substring(split, split*2) == 'CTF{')`, position `4 to 7` should be `CTF{`
Let's fill the gaps:
```
p i c o C T F { _ _  _  _  _  _  _  _  _  _  _  _  _  _  _  _  a  3  c  8 
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27
 _  _  _  _
28 29 30 31 
```

According to `if (checkpass.substring(split*4, split*5) == 'ts_p')`, position `16 to 19` should be `ts_p`
Let's fill the gaps:
```
p i c o C T F { _ _  _  _  _  _  _  _  t  s  _  p  _  _  _  _  a  3  c  8 
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27
 _  _  _  _
28 29 30 31 
```

According to `if (checkpass.substring(split*3, split*4) == 'lien')`, position `12 to 15` should be `lien`
Let's fill the gaps:
```
p i c o C T F { _ _  _  _  l  i  e  n  t  s  _  p  _  _  _  _  a  3  c  8 
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27
 _  _  _  _
28 29 30 31 
```

According to `if (checkpass.substring(split*5, split*6) == 'lz_1')`, position `20 to 23` should be `lz_1`
Let's fill the gaps:
```
p i c o C T F { _ _  _  _  l  i  e  n  t  s  _  p  l  z  _  1  a  3  c  8 
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27
 _  _  _  _
28 29 30 31 
```

According to `if (checkpass.substring(split*2, split*3) == 'no_c')`, position `8 to 11` should be `no_c`
Let's fill the gaps:
```
p i c o C T F { n o  __  c  l  i  e  n  t  s  _  p  l  z  _  1  a  3  c  8 
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27
 _  _  _  _
28 29 30 31 
```

According to `if (checkpass.substring(split*7, split*8) == '9}')`, position `28 to 31` should be `9}`
Let's fill the gaps:
```
p i c o C T F { n o  _  c  l  i  e  n  t  s  _  p  l  z  _  1  a  3  c  8 
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27
 9  }  _  _
28 29 30 31 
```

Clearly comes out to be `picoCTF{no_clients_plz_1a3c89}`

**Steps**:

1. Check the source code using inspect `ctrl+shift+i`.
2. Look for something that verifies, the password which upon looking at the source code came to be:
```
function verify() {
    checkpass = document.getElementById(pass).value;
    split = 4;
    if (checkpass.substring(0, split) == 'pico') {
      if (checkpass.substring(split*6, split*7) == 'a3c8') {
        if (checkpass.substring(split, split*2) == 'CTF{') {
         if (checkpass.substring(split*4, split*5) == 'ts_p') {
          if (checkpass.substring(split*3, split*4) == 'lien') {
            if (checkpass.substring(split*5, split*6) == 'lz_1') {
              if (checkpass.substring(split*2, split*3) == 'no_c') {
                if (checkpass.substring(split*7, split*8) == '9}') {
                  alert(Password Verified)
                  }
                }
              }
      
            }
          }
        }
      }
    }
    else {
      alert(Incorrect password);
    } 
  }
```

3. Now upon breaking down as talked about in the `thought process` section we get:
```
picoCTF{no_clients_plz_1a3c89}
```

Upon verifying, comes out to be correct both on website and picoCTF portal.