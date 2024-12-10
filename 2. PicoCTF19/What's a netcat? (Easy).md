
**Description**:
Using netcat (nc) is going to be pretty important. Can you connect to `jupiter.challenges.picoctf.org` at port `64287` to get the flag?

**Hint**:
nc [tutorial](https://linux.die.net/man/1/nc)

**Thought Process:**
Learnt how to use `nc` for scanning purposes.

**Steps**:

1. Use netcat's `nc` command with the host and the host's port:
```
$ nc jupiter.challenges.picoctf.org 64287
You're on your way to becoming the net cat master
picoCTF{nEtCat_Mast3ry_284be8f7}

```
