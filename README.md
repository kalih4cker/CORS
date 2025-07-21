# CORS (Cross-Origin Resource Sharing) Exploitation Guide

CORS is a browser security feature that restricts web pages from making requests to a different domain than the one that served the web page. Improper configuration can lead to data leakage or account takeover if exploited correctly.

---

## What is CORS?

**CORS (Cross-Origin Resource Sharing)** controls access to resources located outside a given domain.  
By default, browsers block cross-origin requests unless the server explicitly allows them through CORS headers.

---

## Vulnerability Indicators

When testing, look for the following headers in the **HTTP response**:

```http
Access-Control-Allow-Origin: https://example.com
Access-Control-Allow-Credentials: true

**## Exploition**
if it allowed the origin given by you then you can use the script given above to exploit
change the url in this part in script 
` xhttp.open("GET", " **Paste url here** ", true);`
