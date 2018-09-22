---
layout: default
title: "Basic Building Blocks"
date: 2018-09-19
---

# Basic Building Blocks
I thought this would be a great place to start. There is little to none
excitement to present the OAuth2 spec and the building blocks of that, and many
others has written a lot better than what I could do about it.  My thinking was
to run through that quickly, and then look in to the inner workings of the
Authorization Server, the interesting part and se what is needed for that to
work.

## OAuth2 RFC 6749
There is one RFC that outlines what we will talk about, [OAuth 2.0 Framework -
RFC 6749](https://tools.ietf.org/html/rfc6749)
The describe four different roles:

- **Resource owner**
      An entity capable of granting access to a protected resource.
      When the resource owner is a person, it is referred to as an
      end-user.

- **Resource server**
      The server hosting the protected resources, capable of accepting
      and responding to protected resource requests using access tokens.

- **Client**
      An application making protected resource requests on behalf of the
      resource owner and with its authorization.  The term "client" does
      not imply any particular implementation characteristics (e.g.,
      whether the application executes on a server, a desktop, or other
      devices).

- **Authorization server**
      The server issuing access tokens to the client after successfully
      authenticating the resource owner and obtaining authorization.

Out of these four roles, we will need to keep extra care for three of them.
The  **Authorization Server**, **Clients** and **Resource Owners**.  The
**Authorization Server** is the one that is of obvious interest, **Clients**
are the main integration points for the **Authorization Server** and we will
need to keep track of the representation and make sure to authenticate
different **Clients** and make sure to keep every **Client** needs. Lastly we
have the **Resource Owners** that is the users, Username and Passwords are
needed to be saved.

## The interesting part
What is an **Authorization Server** built by and what is actually needed on a more
"fine grained" level? 

Some sort of web component is needed (for API and login), and a component for
maintaining some sort of state is needed. Currently I've decided to split mine
in a single step further, but still keeping each part big enough to solve a
specific set of tasks.
### Web
For interaction between **Clients** a very special set of API's are needed
and defined in the RFC. 
#### Token Endpoint 
Endpoint for the **Clients** to retrieve tokens.
#### Authorization Endpoint 
Endpoint where the **Resource Owners** Authorize **Clients**.
#### Additional endpoints
The **Resource Owners** will have to log in somewhere. 
- Register page might be handy
- A couple of management pages might be needed to speed things up and be able
  to maintain stuff in a useful way. E.g. Register Clients, manage and maintain
  them in a decent way

### Internal components
Not only is communication and integration needed, some internal components are
needed in order to keep track of all the tokens, make sure validation is
correctly carried out and so on.
#### User management
There is need for a management of users, keeping track of who is logging in,
and their password.
#### Client management
The clients will also be handled with care. Each client will handed out tokens
to, it's users and we will need to keep track of settings such as scopes,
consent and also basic stuff such as authenticate the clients will be handled
by this part
#### General management
General management, the clients and users will have to be "created/started"
from somewhere, and have one single point for this management is this page.

## To be continued
That was all for this time, I'm thinking about going through the internal
components one and one in future posts with further details. 

Bye for now!

















