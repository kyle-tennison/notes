
### Session Authentication
Session gets created:
- Stored in the back end DB
- Stored in the browser cookie jar
- Passed in each request

### Token based authentication

A JWT is created using a private key, and then it is sent to the browser. The server does **not** keep track of all of the JWTs it creates.

The JWT, from the client perspective, is the same; it is stored in local memory. 

On each request, the JWT is added in the header under `Authorization: Bearer <token>`


## JWT with Auth0

![[Pasted image 20240528215154.png]]

First, call `/authenticate`, which will redirect and do all of the inner Auth0 stuff.

Then, using the `OAuth2` method with Auth0, then call POST `/oauth/token` (https://auth0.com/docs/api/authentication?http#-post-oauth-token-) to get your token.




