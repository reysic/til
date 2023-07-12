# Basic vs Bearer Authentication

## Basic

* client sends base64 encoded username and password with every request
* server decodes credentials and checks validity
* lacks token expiration and scope limitation
* encoded, _not_ encrypted, should be paired with HTTPS/TLS
* easy to implement, suitable for low-risk scenarios
* sample header: `Authorization: Basic dGVzdDpwYXNzd29yZA==`

## Bearer

* client obtains token from authorization server
* server validates token to grant access to protected resource
* client does not have to store or send credentials
* tokens have expiration and scope limitation
* suitable for high-risk scenarios (production, public APIs)
* sample header: `Authorization: Bearer <token>`

## References

* [LinkedIn](https://portswigger.net/burp/documentation/desktop/settings/sessions)
* [StackOverflow](https://stackoverflow.com/questions/34013299/web-api-authentication-basic-vs-bearer)