# Banner Grabbing Techniques

1. Using Telnet
    - change the port accordingly
    ```
    telnet target.com 80
    ```
    or
    ```
    telnet <target ip> 80
    ```
    then type
    ```
    GET / HTTP/1.1
    Host: target.com
    ```
    or
    ```
    GET / HTTP/1.1
    Host: target-ip
    ```
    output on failure:
    ```
    HTTP/1.0 400 Bad Request
    Server: AkamaiGHost
    Mime-Version: 1.0
    Content-Type: text/html
    Content-Length: 312
    Expires: Wed, 02 Oct 2024 14:09:28 GMT
    Date: Wed, 02 Oct 2024 14:09:28 GMT
    Connection: close

    <HTML><HEAD>
    <TITLE>Invalid URL</TITLE>
    </HEAD><BODY>
    <H1>Invalid URL</H1>
    The requested URL "&#91;no&#32;URL&#93;", is invalid.<p>
    Reference&#32;&#35;9&#46;876e3f17&#46;1727878168&#46;1a6be58f
    <P>https&#58;&#47;&#47;errors&#46;edgesuite&#46;net&#47;9&#46;876e3f17&#46;1727878168&#46;1a6be58f</P>
    </BODY></HTML>
    Connection closed by foreign host.
    ```
    output on success:
    ```
    HTTP/1.1 200 OK
    Date: Mon, 02 Oct 2024 10:00:00 GMT
    Server: Apache/2.4.29 (Ubuntu)
    Content-Type: text/html
    ```

2. Using netcat 
   use any port of your choice
   ```
   nc <target ip> <target port>
   ```
   ```
   nc 127.0.0.1 80
   ```
   or
   ```
   nc target.com 80
   ```
   then type
    ```
    GET / HTTP/1.1
    Host: target.com
    ```
    or
    ```
    GET / HTTP/1.1
    Host: targetIP
    ```

3. Using curl
   ```
   curl -I 127.0.0.1
   ```
   or 
   ```
   curl -I https://target.com
   ```
   if the output is like this 
   ```
    HTTP/1.0 301 Moved Permanently
    Location: https://www.dell.com/
    Server: BigIP
    Connection: Keep-Alive
    Content-Length: 0
   ```

   use -L flag to follow redirect
    ```
    curl -I -L https://target.com
    ```

    For only header info and no data use the -l flag
    ```
    curl -I -L -l https://target.com
    ```
    output:
    ```
    HTTP/2 302
    content-type: text/html; charset=UTF-8
    location: https://target.com
    x-ua-compatible: IE=edge
    .................
    ```
4. Using wget 
    ```
    wget --server-response --spider https://target.com
    ```
    other:
    ```
    whatweb target.com
    ```