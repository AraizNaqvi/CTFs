
**Description**:
What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases.

**Hint**:
Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag.

**Thought Process:**
I had zero clue of what this is, but since it says bases it definitely has something to do with bases. So I searched up most comonly used base and it said `base64`. Then I tried to identify how to notice a base64 encoding. Here's what I learnt on how to recognise base64:
- Letters (A-z, a-z)
- Numbers (0-9)
- Special Characters (+, /)
- Can end with =, ==
- Usually has length multiples of 4
- Also is most commonly used in CTF's.

**Steps**:

1. Save the text `bDNhcm5fdGgzX3IwcDM1` in a file as:
```
echo "bDNhcm5fdGgzX3IwcDM1" >> file
```

2. Use `base64` with `-d` flag to decode the file's text as:
```
~/Documents/Github/CTFs/3. PicoCTF19$ base64 -d file
l3arn_th3_r0p35
```

So the answer is: 
```
picoCTF{l3arn_th3_r0p35}
```

