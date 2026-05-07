# HTTP Status Codes: A Beginner’s Guide for New Testers & SDETs  
  
As a new software tester, understanding HTTP status codes is crucial for debugging, testing APIs, and verifying how web applications respond to different scenarios. These codes are the language of the web, telling us whether a request was successful, redirected, or failed. Here’s a breakdown to get you started:  
  
## 2xx: Success  
  
This is what you want to see! It means the request was successful.  
- 200 OK: Everything worked perfectly, and the resource is returned.  
- 201 Created: A new resource was successfully created (e.g., after a POST request).  
- 202 Accepted: The request was accepted but hasn’t been processed yet.  
- 204 No Content: The server processed the request but doesn’t have any content to return.  
  
## 3xx: Redirection  
  
Sometimes, your request gets redirected to another location.  
- 301 Moved Permanently: The resource has a new permanent URL.  
- 302 Found: Temporarily redirected to a different URL.  
- 304 Not Modified: The resource hasn’t changed since the last time you requested it.  
- 307 Temporary Redirect: Similar to 302 but ensures the same HTTP method is used.  
  
## 4xx: Client Errors  
  
These codes mean something went wrong with your request.  
- 400 Bad Request: The server couldn’t understand your request (e.g., invalid JSON).  
- 401 Unauthorised: You need to log in or provide valid credentials.  
- 403 Forbidden: You don’t have permission to access the resource.  
- 404 Not Found: The resource doesn’t exist (time to check the URL!).  
- 429 Too Many Requests: Slow down! You’re sending too many requests.  
  
## 5xx: Server Errors  
  
These codes indicate a problem on the server’s side.  
- 500 Internal Server Error: Something went wrong on the server.  
- 501 Not Implemented: The server doesn’t support the functionality you requested.  
- 502 Bad Gateway: The server got an invalid response from an upstream server.  
- 503 Service Unavailable: The server is overloaded or under maintenance.  
- 504 Gateway Timeout: The server didn’t receive a timely response.  
  
## Why It Matters for Testers?  
  
For new testers, knowing HTTP status codes can help you:  
- Validate API Responses: Ensure requests return the expected status codes.  
- Debug Issues: Pinpoint whether a problem is with the client, server, or network.  
- Write Better Test Cases: Cover scenarios like redirects, errors, or edge cases.
