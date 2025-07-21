# CORS (Cross-Origin Resource Sharing) Exploitation Guide

CORS is a browser security feature that restricts web pages from making requests to a different domain than the one that served the web page. Improper configuration can lead to data leakage or account takeover if exploited correctly.

---

## What is CORS?

**CORS (Cross-Origin Resource Sharing)** controls access to resources located outside a given domain.  
By default, browsers block cross-origin requests unless the server explicitly allows them through CORS headers.

---

## Vulnerability Indicators

When testing, look for the following headers in the **HTTP response**:

```Access-Control-Allow-Origin: https://example.com```
```Access-Control-Allow-Credentials: true```

---

## Testing for CORS Misconfiguration

1. Intercept a request using **Burp Suite**, **curl**, or any HTTP proxy tool.
2. Modify the request to include a **custom `Origin` header**:
   ```Origin: https://evil.com```
3.Send the request and observe the response headers.

##  Vulnerable If:
The response reflects your custom origin:

```Access-Control-Allow-Origin: https://evil.com```
And the following is also present:

```Access-Control-Allow-Credentials: true```
If both are true, the application is likely vulnerable to CORS exploitatio

## Exploitation
If vulnerable, you can exploit it using a script like this hosted on repo as **cors.html** :
add url in this part ``` xhttp.open("GET", **"https:example.com"**, true);```
