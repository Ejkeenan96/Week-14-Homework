## Week 14 Homework: Web Development

### Overview

In this homework, we will review the many of the concepts and tools covered in the Web Development unit. If needed, refer to the  reference sheets provided to you.

* [HTTP Reference Sheet](HTTPRefernce/HTTP_Reference.md)
* [curl Reference Sheet](CURLReference/cURL_References.md)

---

### Questions 

Before you work through the questions below, please create a new file and record your answers there. This will be your homework deliverable.

#### HTTP Requests and Responses

Answer the following questions about the HTTP request and response process.

1. What type of architecture does the HTTP request and response process occur in?
  ```
  - Client-Server Architecure is the type of architecture HTTP request and repsonse process occur in.
  ``` 
2. What are the different parts of an HTTP request? 
  ```
  - Request Headers, Request Lines, Request Body
  ```
3. Which part of an HTTP request is optional?
  ``` 
  - Request Body
  ```
4. What are the three parts of an HTTP response?
  ```
  - Header, Status Line, Body
  ```
5. Which number class of status codes represents errors?
  ``` 
  - The number class of status codes represent errors is in the 400's range
  ```
6. What are the two most common request methods that a security professional will encounter?
  ```
  - The two most common request methods that a security professional will encounter are GET & POST
  ```
7. Which type of HTTP request method is used for sending data?
  ``` 
  - POST request is the HTTP request method used to send data
  ```
8. Which part of an HTTP request contains the data being sent to the server?
  ```
  - You would look at the Request body to see that the data is being sent to the server
  ```
9. In which part of an HTTP response does the browser receive the web code to generate and style a web page?
  ```
  - The Response body is where the browser receives the web code to generate and style a web page
  ```
#### Using curl

Answer the following questions about `curl`:

10. What are the advantages of using `curl` over the browser?
  ```
  - Ability to make adjustments as the security professional works
  - Ability to support various different protocols even if the UI is not present
  - Ability to manage HTTP HTTP Request/Responses in a Repeatable, Programmatic way
  - Ability to quickly test HTTP Request in a way that can be automated
  ```
11. Which `curl` option is used to change the request method?
  ```
  -X
  ```
12. Which `curl` option is used to set request headers?
  ```
  -H
  ```
13. Which `curl` option is used to view the response header?
  ```
  -I
  ```
14. Which request method might an attacker use to figure out which HTTP requests an HTTP server will accept?
  ```
  - Options
  ```
#### Sessions and Cookies

Recall that HTTP servers need to be able to recognize clients from one another. They do this through sessions and cookies.

Answer the following questions about sessions and cookies:

15. Which response header sends a cookie to the client?

    ```HTTP
    HTTP/1.1 200 OK
    Content-type: text/html
    `Set-Cookie: cart=Bob`
    ```
    - `Set-Cookie:` is the header that sends a cookie to the client
16. Which request header will continue the client's session?

    ```HTTP
    GET /cart HTTP/1.1
    Host: www.example.org
    `Cookie: cart=Bob`
    ```
    - `Cookie:` is the header that will continue the client's session
    
#### Example HTTP Requests and Responses

Look through the following example HTTP request and response and answer the following questions:

**HTTP Request**

```HTTP
POST /login.php HTTP/1.1
Host: example.com
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 34
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Linux; Android 6.0; Nexus 5 Build/MRA58N) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.132 Mobile Safari/537.36

username=Barbara&password=password
```

17. What is the request method?
  - `POST` is the request method
18. Which header expresses the client's preference for an encrypted response?
  - `Accept-Encoding` is the header that expresses the client's preferences for an encrypted response
19. Does the request have a user session associated with it?
  - No this request does not have a user session associated with it
20. What kind of data is being sent from this request body?
  - `Login credetials` is the kind of data that is being sent from this request body
  
**HTTP Response**

```HTTP
HTTP/1.1 200 OK
Date: Mon, 16 Mar 2020 17:05:43 GMT
Last-Modified: Sat, 01 Feb 2020 00:00:00 GMT
Content-Encoding: gzip
Expires: Fri, 01 May 2020 00:00:00 GMT
Server: Apache
Set-Cookie: SessionID=5
Content-Type: text/html; charset=UTF-8
Strict-Transport-Security: max-age=31536000; includeSubDomains
X-Content-Type: NoSniff
X-Frame-Options: DENY
X-XSS-Protection: 1; mode=block

[page content]
```

21. What is the response status code?
  - The repsonse status code is `200 OK`
22. What web server is handling this HTTP response?
  - `Apache` is the web server that is handling this HTTP response
23. Does this response have a user session associated to it?
  - Yes, this reponse does have a user session associated to it `SessionID=5`
24. What kind of content is likely to be in the [page content] response body?
  - The [page content] is likely to have `Text` or `HTML` in the content.
25. If your class covered security headers, what security request headers have been included?
  - The `Strict-Transport-Security` header has been included
  
#### Monoliths and Microservices

Answer the following questions about monoliths and microservices:

26. What are the individual components of microservices called?
  - The individual components of microservices are called `Front-end`, `Back-end`, `Database`
27. What is a service that writes to a database and communicates to other services?
  - The Back-end service writes to a database and communicates to other services
28. What type of underlying technology allows for microservices to become scalable and have redundancy?
  - The type of underlying technology that allows fro microsevices to become scalable and have redundancy is `containerization`.
  
#### Deploying and Testing a Container Set

Answer the following questions about multi-container deployment:

29. What tool can be used to deploy multiple containers at once?
  - The tool that can be used to deploy mutiple containers at once is Docker. That being said there are other tools out there that you can also use. 
30. What kind of file format is required for us to deploy a container set?
  - `.yml` is `Yaml` format that is required to deploy a container set
#### Databases

31. Which type of SQL query would we use to see all of the information within a table called `customers`?
  ```
  - SELECT * FROM 'customers';
  ```
32. Which type of SQL query would we use to enter new data into a table? (You don't need a full query, just the first part of the statement.)
  - `INSERT INTO` 
33. Why would we never run `DELETE FROM <table-name>;` by itself?
  - If you run that command then it will delete the enitre table itself.
---
