# HTTP
Standard HTTP methods (e.g., GET, POST, PUT, PATCH and DELETE):
* GET 
* Request :  *method request-target http-version*
    * ```GET / HTTP/1.1
Host: www.example.com```
* Response : *http-version status*
    * ```HTTP/1.1 200 OK
Content-Type: text/html```
* POST
* Code :
    * 200 OK
    * 301 Moved Permanently. Automatic redirects built in browsers.
    * 302 Found. Page is now at a new location temporarily.
    * 304 Not Modified
    * 307 Temporary Redirect
    * 401 Unauthorized. Login required.
    * 403 Forbidden. Server will not allo this request.
    * 404 Not Found
    * 418 I'm a Teapot
    * 500 Internal Server Error. Geneal server failur to the otherwise-valid request.
    * 503 Service Unavailable
## TCP
Protocol that allows a single server, at the same IP adress, to provide multiple services through port number. Also provides a mechanism for resending packets if one is lost since there is multiple paths interconnected.
* port 80 : request for http pour le web
* port 443 : https
* FTP uses port 21
* SMTP uses port 25
* DNS uses port 53