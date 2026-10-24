# HTTP observations (Lab 4, Task 1)

| Question | My answer |
|----------|-----------|
| Request method for index.html | GET |
| Status code with Disable cache ticked | 200 OK|
| Status code on a normal reload | 304 Not Modified|
| Status code for /nothing-here.html | 404|
| Value of the Content-Type response header | text/html |
| Remote Address (IP and port) | [::1]:80 |
| Protocol in the address bar (http or https) | http |

## Why is this address http and not https?
HTTPS protect that traffic  that travels on a network. But this adress is on localhost it is on my own machine not on other machine,it does not go on any other network so 
## Live site observations (Lab 4, Task 7)

1. Compare localhost (Task 1) with the live site: protocol, server header, and Remote Address. What changed and why?

On localhost the protocol was http, the server was my own XAMPP Apache, and the Remote Address was [::1]:80. On the live site the protocol is https, the server header says GitHub.com, and the Remote Address is 185.199.111.153:443. It changed because the live site is hosted on GitHub's computers, which are reached over the internet, so the connection uses HTTPS on port 443.

2. What does the padlock and certificate tell the visitor, and what could an attacker on the same Wi-Fi do if the site were plain http?

The padlock tells the visitor that the connection is encrypted and that the certificate, issued by YR1 and valid from [Thursday 1 October 2026 at 04:44:46] to [Wednesday 30 December 2026 at 04:44:45], proves the site really belongs to github.io. If the site were plain http, an attacker on the same Wi-Fi could read the traffic or even change the page on its way to the visitor.

3. Why was the Saved orders table empty on the live site, even though you saved orders on localhost?

localStorage belongs to one origin, which means a combination of protocol, host and port. localhost and kanizfatima69.github.io are different origins, so the live site could not see the orders saved on localhost and started with empty storage.

4. Which HTTP status code did the missing page return, and who sent it?

The missing page returned status code 404 Not Found. It was sent by GitHub's server, not by my own files, which is why it showed GitHub's own error page 404.