
**Description**:
There is a website running at `https://jupiter.challenges.picoctf.org/problem/50009/` ([link](https://jupiter.challenges.picoctf.org/problem/50009/)) or http://jupiter.challenges.picoctf.org:50009. Do you think you can log us in? Try to see if you can login!

**Hint**:
There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database? Try to think about how the website verifies your login.

**Thought Process:**
Had to learn SQL Injection on the spot, check out [this](https://youtu.be/2OPVViV-GQk?si=sjI97iBXsNn14me1) video.
So, first I tried to add an extra `'` after the username i used i.e. `admin` which immediately upon submission returned an error, which means SQL injection is possible.

From here assuming the backend SQL query is like this:
`SELECT * FROM users WHERE username = 'input' AND password = 'input';`
whatever you type in the username and password field goes between these single inverted commas.

Now, if I used the most common SQL injection exploit:
`' OR '1'='1` which works in the manner that `' OR ` helps come out of the username input, then OR checks condition if 1 is equal to 1 which is always true. So, then condition is checked as:
is username='whatever you type' and password='' OR '1'='1' which is true, hence letting us login. This results in the following query:
`SELECT * FROM users WHERE username = 'admin' AND password = '' OR '1'='1';`

**Steps**:

1. Go to the Admin Login page and enter username:
```
admin
```

2. Enter Password using SQL Injection:
```
' OR '1'='1
```

Solution is: `picoCTF{s0m3_SQL_fb3fe2ad}`