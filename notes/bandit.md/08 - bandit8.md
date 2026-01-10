# Bandit lvl 8 → lvl 9

Tags: 
Date:

# Goal
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

# Approach
lets take the data.txt and use `sort`  and `uniq`

`sort` is going to 'sort' the data.txt and have them in alphabetical order. To make this easier to read we can use `uniq` command and its going to only show us the unique string, that being the password we are looking for.
## Output / Result
```bash
bandit8@bandit:~$ sort data.txt | uniq  -u
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

```

# Commands user
* ls 
* sort 
* uniq  