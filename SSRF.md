Server Side request forgery is an attack that causes the web server to make request to another server that is controlled by the attacker or the server itself can be used for access that sensitive information


Common Places and Identification and testing
- when full URL is provided `https://website.com/access?server=https://accounts.website.com/api/user/123`
- Hidden form field
- Partial URL such as hostname or routename ex- `https://website.com/access?server=api` here the api indicates something
- relative path `https://website.com/access?server=/api/users/data`


Tips
- using loop-back addresses such as `127.0.0.1 or localhost`
- applications calling a local private IP address in the request `stockAPI=http://192.168.1.5/admin`
  `POST /product/stock 
  `HTTP/1.0 
  `Content-Type: application/x-www-form-urlencoded
  `Content-Length: 118 
  `stockApi=http://192.168.0.68/admin`
- SSRF bypass with blacklisted and whitelisted input filters
- via Open Redirects

IP addresses to be blocked from access are
- localhost
- 127.0.0.1
- 0.0.0.0






Cases:
There was a path /private that cannot be accessed and gave the error `cannot start URL with /private` in order to bypass this payload used was `x/../private`. (THM SSRF LAB)
