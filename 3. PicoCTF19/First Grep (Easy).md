
**Description**:
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file)? This would be really tedious to look through manually, something tells me there is a better way.

**Hint**:
grep [tutorial](https://ryanstutorials.net/linuxtutorial/grep.php)

**Thought Process:**
I see a long string, which is impossible to be read through to find the flag. So, I need to look for the picoCTF prefix. This can easily be done using grep.

**Steps**:

1. Let's `cat` the file to see what it's got:
```
~/Downloads/TEMP/pico$ cat file
yQE:Z:y?9U@Z	Pl6lA%KO0TGr@9#mc`O;zWQePqFFyrZ+dzqMx`I*33T_gNm7[P|_)y8P9=EM8kn$4r/9M$~mG,UD=p2L /-$$mAdfN+:1YGP(A5&!,ry 6 i^0mA*xKVJ`s[3R]a5!r3wlgT>hR$7@V1BLg[MH^	q		,fH>*ib~bkV`E+74%pCB6%DP~#J[QU]qnrSFg?%<!T*ZJGoK>w8^n*|QwcyX;~W9hHmYEj514ECw	rMj84c[;plncW+Zus	PN,3DJJ	!U=9W,e8:Ia BdkN0S+N:.t(fB@O.YWT3[u(Qo4UCy6xS2L,4$Yg-1J-TQ-%~_Ot$QV=~x 
( and more, good luck reading through that :) )
```

2. Using `grep` command to find the flag which should begin with `picoCTF` as:
```
~/Downloads/TEMP/pico$ cat file | grep "picoCTF"
picoCTF{grep_is_good_to_find_things_dba08a45}
```

