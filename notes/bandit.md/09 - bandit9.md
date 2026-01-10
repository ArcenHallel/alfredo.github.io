# Bandit lvl 9 → lvl 10

Tags: 
Date:

# Goal
The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

# Approach
this is a big file with only a few human-readable strings, so what we can do is use `strings` and `grep`  to search for === so we can locate the password.
## Output / Result
```bash
bandit9@bandit:~$ strings data.txt | grep ==
========== the
========== password
Q========== is%
>u`9J========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

```

# Commands user
* strings
* grep
