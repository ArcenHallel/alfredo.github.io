# Bandit lvl 7 → lvl 8

Tags: 
Date:

# Goal
The password for the next level is stored in the file data.txt next to the word millionth

# Approach
this file is really big and has a lot of passwords.
we are only looking for the password next to "millionth".

for this we can use `cat` in combination with `grep`

## Output / Result
```bash
bandit7@bandit:~$ cat data.txt  | grep 'millionth'
millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
bandit7@bandit:~$ 

```

# Commands user
* cat 
* grep
* pipe ( the line next to grep in between the cat data.txt is called pipe, allowing us to use multiple commands.)