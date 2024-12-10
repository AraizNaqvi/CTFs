
**Description**:
This [garden](https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg) contains more than it seems.

**Hint**:
What is a hex editor?

**Thought Process:**
The hint said that it had something to with the hex code, so obviously i'm going to run to xxd or hexedit to look at the hex code, and just scrolling through the entire mess, just as I reached the end, voila! There it is!

**Steps**:

1. Using a hexeditor like xxd to view the hex code of the jpeg as:
```
xxd garden.jpg
```

2. Scrolled through and found the flag in the binaries:
```
picoCTF{more_than_m33ts_the_3y33dd2eEF5}
```