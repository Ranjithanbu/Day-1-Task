### What is HTTP?  
HTTP stands for hypertext transfer protocol and it is used in `client-server communication`. By using HTTP user sends the request to the server & the server sends the response to the user.
#### HTTP/1.1:
 For better understanding, let’s assume the situation when you make a request to the server for the guvi.html page & server responds to you as a resource guvi.html page. before sending the request and the response there is a TCP connection established between client & server. again you make a request to the server for video vid.mp4 & the server gives a response as a video vid.mp4. the connection was not lost here after the first request because we add a keep-alive header which is the part of the request so there is an open connection between the server & client. there is a persistent connection which means several requests & responses are merged in a single connection. **_These are the drawbacks_** that lead to the creation of HTTP/2: **_The first problem is HTTP/1.1 transfer all the requests & responses in the plain text message form_**. The second one is head of line blocking in which TCP connection is blocked all other requests until the response does not receive. **_all the information related to the header file is repeated in every request_**.

 #### HTTP/2:
 HTTP/2 was developed over the *SPDY protocol*. HTTP/2 works on the `binary framing layer` instead of `textual` that converts all the messages in **_binary format_**. it works on fully *multiplexed* that is one TCP connection is used for multiple requests. *_HTTP/2 uses HPACK which is used to split data from header_*. it compresses the header. The server sends all the other files like CSS & JS without the request of the client using the PUSH frame.

#### Difference between HTTP/1.1 and HTTP/2: 
S.No | HTTP/1.1 | HTTP/2
--- | --- | ---
1 | It works on the textual format. | It works on the binary protocol.
2 | There is head of line blocking that blocks all the requests behind it until it doesn’t get its all resources. | It allows multiplexing so one TCP connection is required for multiple requests.
3|It uses requests resource Inlining for use getting multiple pages|It uses PUSH frame by server that collects all multiple pages 
4|It compresses data by itself.|It uses HPACK for data compression.
