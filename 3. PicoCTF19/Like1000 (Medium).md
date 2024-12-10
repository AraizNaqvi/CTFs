
**Description**:
This [.tar file](https://jupiter.challenges.picoctf.org/static/52084b5ad360b25f9af83933114324e0/1000.tar) got tarred a lot.

**Hint**:
Try and script this, it'll save you a lot of time

**Thought Process:**
After looking at the file and extracting it manually twice I notice the file changes from 1000.tar to 999.tar to 998.tar, so looking at this I store a variable with the name of the initial untouched file i.e. 1000.tar and the while checks whether such a file exists or not and if it does it will go ahead and extract it then remove it. 

Count increases so that 1000-count keeps track of file as it is decremented. 

This decremented file is selected and then extracted again in loop until 0.tar which won't exist and hence loop stops, but by now we shall have the non-tar files.

**Steps**:

1. Wrote a `shell script` as follows to extract:
```
#!/bin/bash

echo "Beginning Extraction..."

count=0
current_tar="1000.tar"                      # Starting with the 1000.tar file

while [[ -f "$current_tar" ]]; do           # While current_tar exists do
        echo "Extracting $current_tar"
        tar -xf "$current_tar"              # Extracting current_tar
        rm "$current_tar"                   # Removing current_tar so that there's no clash
        count=$((count+1))                  # Increment count by 1

        next_number=$((1000 - count))       # Next Number becomes 1000-whatever the count
        current_tar="${next_number}.tar"    # Set current_tar to this.
done

echo "Extraction Completed!"
echo "Number of tar files processed: $count"
```

After extraction of the 1000 file completes, you get two files: `filler.txt` and `flag.png`

2. Open the image using `xdg-open` as:
```
~/Downloads/TEMP/pico$ xdg-open flag.png
```
This image holds the passcode.

Solution is: `picoCTF{l0t5_0f_TAR5}`