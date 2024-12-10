
**Description**:
Kishor Balan tipped us off that the following code may need inspection: `https://jupiter.challenges.picoctf.org/problem/9670/` ([link](https://jupiter.challenges.picoctf.org/problem/9670/)) or http://jupiter.challenges.picoctf.org:9670

**Hint**:
How do you inspect web code on a browser? There's three parts.

**Thought Process:**
After getting the first hint through the html by inspecting page, it said 1/3 which cleary is html/css/js, so I just need to look at the css and js to get to the flag now.

**Steps**:

1. Type `ctrl+shift+i` to get html, searching through you shall find:
```
<!-- Html is neat. Anyways have 1/3 of the flag: picoCTF{tru3_d3 -->
```

2. Using the file name in css link given in `head` part that is https://jupiter.challenges.picoctf.org/problem/9670/mycss.css, you shall find:
```
/* You need CSS to make pretty pages. Here's part 2/3 of the flag: t3ct1ve_0r_ju5t */
```

3. Using the file name in js link given in `head` part that is https://jupiter.challenges.picoctf.org/problem/9670/myjs.js, you shall find:
```
/* Javascript sure is neat. Anyways part 3/3 of the flag: _lucky?2e7b23e3} */
```

Solution: `picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?2e7b23e3}`