
**Description**:
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings) without running it?

**Hint**:
[strings](https://linux.die.net/man/1/strings)

**Thought Process:**
Anytimes there's finding a certain flag in a shithole of text, use uncle `grep`.

**Steps**:

1. Checking file type:
```
$ file strings
strings: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=94ec6b5e9cef175e834e0f7fcaedeaa167603c90, not stripped

```

2. Let's use the old helpful `grep` command with `strings` command on this string file:
```
$ strings strings | grep "picoCTF"
picoCTF{5tRIng5_1T_d66c7bb7}
```