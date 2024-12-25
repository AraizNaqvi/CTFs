
**Title**: like1000

**Description**:
This [.tar file](https://jupiter.challenges.picoctf.org/static/52084b5ad360b25f9af83933114324e0/1000.tar) got tarred a lot.


**Steps Taken**:
Upon having first look at the `1000.tar` file, let's extract it once and see what we get:
```
$ tar -xf 1000.tar
```

The result will be a `999.tar`. So, clearly the result is decremented by 1.
Let's get on with the bash script:
![[Pasted image 20241225154808.png]]

Once completed, you get a `flag.png`.
This `png` will contain the flag. Open it using:
```
xdg-open flag.png
```
![[Pasted image 20241225155002.png]]


**Flag**: `picoCTF{l0t5_0f_TAR5}`
