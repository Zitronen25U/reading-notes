# Class 11 Reading Notes

## What is OAuth? How the open authorization framework works?

### Seameless, single sign

- one of the most difficult security practices to implement has been SSO.

- unrelated websites can now login using SSO

- you can use password, phone, certs, bio, or two factor

### Definition

- open standard authorization protocol or framework that describes how unrelated servers and services can safely allow authenticated access to their assets

### OAuth History

- Twitter, google, and other companies

- released in 2010 as open standard.

### Examples

- offers more than 1 way to login

- sending cloud stored files to another user via email. 

### Explained

- almost always represent two unrelated sites or services

- OAuth is about authorization in particular, and not directly about authentication. 

- It's about ownership of someting, not proving who you are

- does not allow holder full, unlimited access like a regular key.

- allows the user access via an authentication provider that they have previously successful authenticated with

### How OAuth works

1. First website connects to the second on behalf of user

2. Second generates a one-time token
3. First site gives his token and secret to the user software
4. The clients software presents the request token to the user
5. Claient may be asked to authenticate
6. The user approves a transaction type at the first websire
7. The user is given an approved token
8. The user gives the approved access token to the first website
9. The first website gives the access token to the second site
10. The second web lets the first web access their site on behalk of the user
11. The user sees a successful transation occur
12. Similar to Kerberos!

### OAuth vs. OpenID

- open ID is really about ID'ing someone, not just about authorizing you

- began in 2005

- SSO vouching for a users identity

### OAuth vs SAML

- XML variant language.

- allows one computer to perform both authentication and authorization

## Authentication and Authorizatoin Flows

- AuthO uses the OIDC Protocol to authenticate users and get their authorization to access protected resources.

### Authorization Code Flow

- exchanges an Authorization Code for a token.

### Authorization Code Flow with Proof Key for Code Exchange 

- OAuth 2.0 provides the Implicit Flow, which is intended for Public Clients, or applications which are unable to securely store Client Secrets

### Hybrid Flow

- allow your application to have immediate access to an ID token while still providing for secure and safe retrieval of access and refresh tokens.

### Client Credentials Flow

- Machine to Machine (M2M) apps use the Client Credentials Flow

[Return!](./class301main.md);