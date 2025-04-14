# JSON Web Tokens & Auth0

### Session Authentication
A session is created:
- Stored in the back end DB
- Stored in the browser's cookie jar
- Passed in each request

### Token-based Authentication

A JWT is created using a private key and then sent to the browser. The server does **not** keep track of all the JWTs it creates.

From the client's perspective, the JWT remains the same; it is stored in local memory.

On each request, the JWT is added to the header under `Authorization: Bearer <token>`


## JWT with Auth0

![[Pasted image 20240528215154.png]]

First, call `/authenticate`, which will redirect and handle all the inner Auth0 stuff.

Then, using the `OAuth2` method with Auth0, call POST `/oauth/token` (https://auth0.com/docs/api/authentication?http#-post-oauth-token-) to get your token.