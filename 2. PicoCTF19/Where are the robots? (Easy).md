
**Description**:
Can you find the robots? `https://jupiter.challenges.picoctf.org/problem/36474/` ([link](https://jupiter.challenges.picoctf.org/problem/36474/)) or http://jupiter.challenges.picoctf.org:36474

**Hint**:
What part of the website could tell you where the creator doesn't want you to look?

**Thought Process:**
After getting the first hint through the html by inspecting page, it said 1/3 which cleary is html/css/js, so I just need to look at the css and js to get to the flag now.

**Steps**:

1. Add the extension `/robots.txt` in the url as `https://jupiter.challenges.picoctf.org/problem/36474/robots.txt`:
```
User-agent: *
Disallow: /477ce.html
```
Clearly, no users are allowed to be able to find this url extension.

2. Add the extension `/477ce.html` in the url as `https://jupiter.challenges.picoctf.org/problem/36474/477ce.html`:
```
picoCTF{ca1cu1at1ng_Mach1n3s_477ce}
```

Solution: `picoCTF{ca1cu1at1ng_Mach1n3s_477ce}`