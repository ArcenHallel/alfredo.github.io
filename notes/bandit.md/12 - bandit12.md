# Bandit lvl 12 → lvl 13

Tags: 
Date:

# Goal
The password for the next level is stored in the file data.txt, which is a hexdump of a ==file that has been repeatedly compressed==. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)
# Approach
this challenge is going to be about filing out the file type and decompressing the file till we get the fully decompressed file with our password.
this one takes a bit but i did my best to walk you through the process.
## Output / Result

lets make a temp directory for us to work out of and copy our file to that dir
```bash
bandit12@bandit:~$ mktemp -d 
/tmp/tmp.SSMp5ERgNg
bandit12@bandit:~$ cd /tmp/tmp.SSMp5ERgNg

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ cp ~/data.txt . 
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ ls
data.txt
```


* xxd is a command line tool we can use to make hexdump files or streams ( human-readable hex + ASCII)
* -r (reverse) tales a hexdump and turns it back into the original binary
* afterwards we `file` the output to find out what type of file and we can see the it was  compressed using `gzip` and use to be called "*data2.bin*"
```bash
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ xxd -r data.txt > file
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ ls
data.txt  file

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ file file
file: gzip compressed data, was "data2.bin", last modified: Fri Aug 15 13:15:53 2025, max compression, from Unix, original size modulo 2^32 584

```


* here we are going to zip our `file`  with `mv` command 
* then we decompress using `gzip` 
* after we can see the file type has changed from `gzip` to `bzip2`
```bash
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ ls
data.txt  file

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ mv file file.gz
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ ls
data.txt  file.gz

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ gzip -d file.gz 
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ ls
data.txt  file

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ file file 
file: bzip2 compressed data, block size = 900k
```


 since we now have a bzip2 file we have to decompress again. 
 following the same pattern we:
 * convert to `.bz2`
 * decompress the file using bzip2 
 * determine file type 

the file used to be data4.bin and is compressed with `gzip`
```bash
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ mv file  file.bz2
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ ls
data.txt  file.bz2

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ bzip2 -d file.bz2 
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ ls
data.txt  file

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ file file 
file: gzip compressed data, was "data4.bin", last modified: Fri Aug 15 13:15:53 2025, max compression, from Unix, original size modulo 2^32 20480
```


again we are going to follow this trend
* convert file to `.gz`
* decompress file 
* determine file type
the file is now in `tar` format 
```bash
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ mv file file.gz
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ ls
data.txt  file.gz

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ gzip -d file.gz 
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ ls
data.txt  file

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ file file 
file: POSIX tar archive (GNU)
```


so we are still not done completely decompressing the file, lets keep moving.
and we can see its another tar file so lets decompress it again.
```bash
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ ls
data.txt  file

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ mv file file.tar
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ tar -xvf file.tar 
data5.bin

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ file data5.bin 
data5.bin: POSIX tar archive (GNU)

```


after decompression we can see the file is now a bzip2.
we have decompressed this file type before, lets run that back.
```bash
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ ls
data5.bin  data.txt  file.tar

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ mv data5.bin data.tar
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ tar -xvf data.tar 
data6.bin

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ file data6.bin 
data6.bin: bzip2 compressed data, block size = 900k

```


our file is back to being in `tar` format and once again we have decompressed a tar file before lets also give that another go.
```bash
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ ls
data6.bin  data.tar  data.txt  file.tar

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ bzip2 -d data6.bz2 

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ ls
data6  data.tar  data.txt  file.tar

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ file data6 
data6: POSIX tar archive (GNU)

```


the file is again compressed with gzip .......this one was a long one for me to but we are just about done!
```bash
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ mv data6 data6.tar
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ ls
data6.tar  data.tar  data.txt  file.tar

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ tar -xvf data6.tar
data8.bin

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ file data8.bin 
data8.bin: gzip compressed data, was "data9.bin", last modified: Fri Aug 15 13:15:53 2025, max compression, from Unix, original size modulo 2^32 49

```


FINALLY we can see the file is not compressed 
```bash
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ mv data8.bin data8.gz
bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ gzip -d data8.gz 

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ ls
data6.tar  data8  data.tar  data.txt  file.tar

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ file data8 
data8: ASCII text

bandit12@bandit:/tmp/tmp.SSMp5ERgNg$ cat data8 
The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

```


# Commands user
* mkdir
* cd
* cp
* ls
* xxd 
* file
* mv
* gzip
* bzip2
* tar
* cat