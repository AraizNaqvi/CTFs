
**Description**:
I wrote you another [song](https://jupiter.challenges.picoctf.org/static/b99c57e4274172bf3c93534b6d59632d/lyrics.txt). Put the flag in the picoCTF{} flag format

**Hint**:
None

**Note**:
The Rockstar language has changed since this problem was released! Use this Wayback Machine URL to use an older version of Rockstar, [here](https://web.archive.org/web/20190522020843/https://codewithrockstar.com/online).

**Thought Process:**
The input 42 is in decimal format, so simply convert that to binary. You can do it manually or online on any site like [this](https://www.rapidtables.com/convert/number/decimal-to-binary.html?x=42)

**Steps**:

1. Go to `Rockstar` language via the link provided and paste lyrics text there:
```
Rocknroll is right              
Silence is wrong                
A guitar is a six-string        
Tommy's been down               
Music is a billboard-burning razzmatazz!
Listen to the music             
If the music is a guitar                  
Say "Keep on rocking!"                
Listen to the rhythm
If the rhythm without Music is nothing
Tommy is rockin guitar
Shout Tommy!                    
Music is amazing sensation 
Jamming is awesome presence
Scream Music!                   
Scream Jamming!                 
Tommy is playing rock           
Scream Tommy!       
They are dazzled audiences                  
Shout it!
Rock is electric heaven                     
Scream it!
Tommy is jukebox god            
Say it!                                     
Break it down
Shout "Bring on the rock!"
Else Whisper "That ain't it, Chief"                 
Break it down
```

2. Now clear out all elements containing `If` and `Else` as:
```
Rocknroll is right              
Silence is wrong                
A guitar is a six-string        
Tommy's been down               
Music is a billboard-burning razzmatazz!
Listen to the music                               
Say "Keep on rocking!"                
Listen to the rhythm
Tommy is rockin guitar
Shout Tommy!                    
Music is amazing sensation 
Jamming is awesome presence
Scream Music!                   
Scream Jamming!                 
Tommy is playing rock           
Scream Tommy!       
They are dazzled audiences                  
Shout it!
Rock is electric heaven                     
Scream it!
Tommy is jukebox god            
Say it!                                     
Break it down
Shout "Bring on the rock!"
Break it down
```

3. When asked for input, type anything:
```
$ 2
Keep on rocking!
66
79
78
74
79
86
73
```
This clearly looks like `decimal`.

4. Go to `Cyberchef.com` and convert from `decimal`:
```
BONJOVI
```

Solution is: `picoCTF{BONJOVI}`