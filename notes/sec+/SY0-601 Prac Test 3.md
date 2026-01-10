---
{}
---
#### Your Final Report

|                              |        |
| ---------------------------- | ------ |
| Total marks                  | 35     |
| Total Questions              | 25     |
| Questions correctly answered | 11     |
| Success ratio                | 44%    |
| Marks secured                | 22     |
| Percentage secured           | 62.86% |
need work on this one

 1) Which of the following facilitate(s) privilege escalation attacks? (Select all that apply)

-    ==System/application vulnerability ( Your answer)==
-    Principle of least authority ( Your answer) X
-    ==Social engineering techniques ( Your answer)==
-    Mandatory Access Control (MAC)
-    ==System/application misconfiguration ( Your answer)==

 Your answer to this question is incorrect or incomplete.


2)  Which of the following answers can be used to describe characteristics of a cross-site scripting attack? (Select 3 answers)

-    ==Exploits the trust a user's web browser has in a website ( Your answer)
-    ==A malicious script is injected into a trusted website ( Missed)
-   ==User's browser executes attacker's script ( Your answer)==
-    Exploits the trust a website has in the user's web browser 
-    A user is tricked by an attacker into submitting unauthorized web requests ( Your answer) X
-    Website executes attacker's requests

 Your answer to this question is incorrect or incomplete.

3)  Which of the following indicates an SQL injection attack attempt?

-    DELETE FROM itemDB WHERE itemID = '1'; ( Your answer) X
-    ==SELECT * FROM users WHERE userName = 'Alice' AND password = '' OR '1' = '1'; ( Missed)== this whole sentence is the format for SQL the others are just to confuse you
-    DROP TABLE itemDB;
-    SELECT * FROM users WHERE email = 'example@example.com' AND password = '';

4) ***was deleted because input was causing Versal to crash

5)  Which of the following fragments of input might indicate an XML injection attack attempt?

``-   [[... <script> malicious script code </script>]] ( Your answer) X
`-    search.aspx?name=userName)(zone=*)`
-    `[[... p@$$w0rd</password></user><user><name>attacker</name> ....]] ==( Missed)==administrator)(&))
`-   [[AND password = '' OR '1' = '1';]]```

6)  Which of the following terms describes an attempt to read a variable value from an invalid memory address?

-    Buffer overflow
-    ==Null-pointer dereference ( Missed)
-    Integer overflow ( Your answer) X
-    Memory leak 
- 
1)  A dot-dot-slash attack is also referred to as:

-    Disassociation attack ( Your answer) X
-    On-path attack
-    ==Directory traversal attack ( Missed)== cd ../ someone is moving out of directorys
-    Downgrade attack

Note: dot-dot-slash = how do you go back up dir in liux ? ../ 

8)  A malfunction in a preprogrammed sequential access to a shared resource is described as:

-   ==Race condition ( Missed)== when device or system attempts to perform two or more operations at the same time 
-    Buffer overflow data in buffer exeeds its storage capacity
-    Memory leak ( Your answer) X  occurs when a process allocates memory from the paged or non paged pools, but doesn't free the memory
-    Pointer dereference accessing the valuie stored at memory address pointed to by that pointer

9)  Which of the following terms refers to a vulnerability caused by race conditions?

-    Mean time to failure
-    Replay attack
-    Mean time between failures ( Your answer) 
-    ==Time-of-check to time-of-use ( Missed)==   TOCTOU attacks are a type of race condition, which happens when two or more operations that should be done in order are attempted at the same time

1)  Which of the programming aspects listed below are critical in secure application development process? (Select 2 answers)

-    Patch management ( Your answer) X
-    ==Input validation ( Missed) 
-    Password protection
-    ==Error and exception handling ( Your answer)
-    Application whitelisting

2)  Which of the following are the characteristic features of a session ID? (Select 3 answers)

-    Stored on a server
-    ==A unique identifier assigned by the website to a specific user ( Missed)
-    Contains user's authentication credentials, e.g. username and password ( Your answer) X
-   == ==A piece of data that can be stored in a cookie, or embedded as an URL parameter ( Your answer)
-    ==Stored in a visitor’s browser ( Your answer)
-    A unique identifier assigned to a server

3)  Which of the terms listed below describes a programming error where an application tries to store a numeric value in a variable that is too small to hold it?

-    Buffer overflow ( Your answer) X
-    Pointer dereference
-    Memory leak
-    ==Integer overflow ( Missed)

 1) Which type of exploit allows an attacker to take control over a server and use it as a proxy for unauthorized actions?

-    XSRF
-    CSRF
-    XSS ( Your answer) X
-    ==SSRF ( Missed)== **Server-side request forgery**

4)  Which of the following answers can be used to describe characteristics of a cross-site request forgery attack? (Select 3 answers)
since this is forgery, the attack is tricking someone into having 
-    ==Exploits the trust a website has in the user's web browser ( Your answer)== the wording here is stating the TRUST a website has in the USERS web browser; coming off as if the user has trust in the web browser instead of the machine 
-    ==A user is tricked by an attacker into submitting unauthorized web requests ( Your answer)
-    ==Website executes attacker's requests ( Missed)
-    Exploits the trust a user's web browser has in a website ( Your answer) X "this one is confusing me, whats the difference"
the TRUST a user's web browser has; is coming off that the computers trust the web browser instead of the user
-    A malicious script is injected into a trusted website
-    User's browser executes attacker's script