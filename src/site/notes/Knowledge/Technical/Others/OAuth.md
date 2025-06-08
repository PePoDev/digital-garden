---
{"dg-publish":true,"permalink":"/knowledge/technical/others/o-auth/","noteIcon":""}
---

## Grant types
- Authorization code flow
	- User authentication with auth server and consent for the permission to use the resource server
- Password
	- It has less security than the first grant type But is easy to use
- Client Credential
	- Best for service-to-service communication
-  Implicit
	- SPA application that can't hide the secret key So can use only Client ID with the correct redirect URL
- Device Code
	- For the device that has limited experience in typing like a TV
	- Example - Netflix on TV
- Refresh Token
	- Renew access token
## References
- https://www.youtube.com/watch?v=cfyz9p2xqIw
