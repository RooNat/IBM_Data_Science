---
module:1
typora-copy-images-to: ./attachments
---

# REST API1 & HTTP Requests - Part1

[toc]

The HTTP protocol can be thought of as a general protocol of transferring information through the web. This includes many types of REST APIs. Recall that REST API’s function by sending a request, and the request is communicated via HTTP message. The HTTP message usually **contains a JSON file**. 

When you, **the client**, use a web page your browser sends an  **HTTP request** to the server where the page is hosted. The server tries to find the desired resource by default "index.html".

If your request is successful, the server will send the object to the client in an HTTP response; this includes information like **the type of the resource**, **the length of the resource**, and **other information**. 

## Uniform Resource Locator: URL

The table under the Web server represents a list of resources stored in the web server. In this case, **an HTML file**, a **png image**, and **a txt file**. When the request is made for the information, the web servers send the requested information, i.e., one of the files.



![image-20230628192317308](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/06/upgit_20230628_1687976598.png)

**Uniform Resource Locator: URL Uniform resource locator (URL) is the most popular way to find resources on the web.** 

We can break the URL into three parts:

- **The scheme**: this is the protocol, for this lab it will always be "http://"
- **The Internet address or Base URL**: this URL will be used to find the location, for example: www.ibm.com and www.gitlab.com
- **Route**: this is the location on the web server, for example: "/images/IDSNlogo.png".

## Request

The following is an example of the request message for the get request method. There are other HTTP methods we can use.

In the start line, we have the GET method. This is an HTTP method. 



![image-20230628233954733](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/06/upgit_20230628_1687991996.png)



In this case, it's requesting the file "index.html". The Request header passes additional information with an HTTP request. In the GET method, the **Request header** is empty. 

Some Requests have a body.

## Response

The following table represents the response. The response start line contains the version number followed by a descriptive phrase. 

![image-20230628234321137](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/06/upgit_20230628_1687992202.png)

In this case, **HTTP/1.0 has a status code (200) meaning success**, and **the descriptive phrase**, OK.  

The response header contains information. Finally, we have the response body containing the requested file, in this case an HTML document. 



### Status Code

![image-20230628234445272](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/06/upgit_20230628_1687992287.png)

Let's look at other status codes. Some status code examples are shown in the table below. The prefix indicates the class; 

- For example, the 100s are informational responses; 100 indicates that everything is OK so far. 
- The 200s are Successful responses: For example,
  200 The request has succeeded. 
- Anything in the 400s is bad news. 401 means the request is unauthorized. 
- 500’s stands for server errors, like 501 for not Implemented. 



When an HTTP request is made, an  HTTP method
is sent. This tells the server what action to perform. A list of several HTTP methods is shown here. 

![image-20230628234713664](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/06/upgit_20230628_1687992435.png)