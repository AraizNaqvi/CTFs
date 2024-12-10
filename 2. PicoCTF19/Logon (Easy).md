
**Description**:
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/13594/` ([link](https://jupiter.challenges.picoctf.org/problem/13594/)) or http://jupiter.challenges.picoctf.org:13594

**Hint**:
Hmm it doesn't seem to check anyone's password, except for Joe's?

**Thought Process:**


**Steps**:

1. Entered the username as `joe` and password as `haha` and get:
![[joe_login_attempt.png]]

2. Go to Inspect mode using `ctrl+shift+i` then head to applications and check for cookies. You will notice that before the username and password were inserted, admin was set to False:
![[logon-false-admin.png]]

3. Setting `Admin` to `True`:
4. Refresh the page to get the flag.

So the answer is: 
```
picoCTF{th3_c0nsp1r4cy_l1v3s_d1c24fef}
```

