# Web techniques

## Vulnerabilities

* I have never used the Cloudflare services, but they might be useful for preventing DDoS attacks on websites and web APIs.
* I have never used captchas as far as I remember. They are useful for preventing mass account creations. Consider Google Captcha.

## Authentication and session validations

* Authentication may usually be done through a JWT (JSON Web Token) which, on log in, is encoded by a server and returned to the client in encoded form and generally stored as a cookie.

## Session validations

* Session validations in a server occur through middlewares which may interrupt a request execution by throwing a session error that is caught by the request cycle process, resulting into an error response.
