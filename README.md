# ![GA Logo](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Auth Research Lab

---

Authentication is a complex and exciting topic that involves using many of the concepts we've already studied as well as several new ideas. 

An authentication system allows the registration / signup of new users and allows those users to sign in. It has to be able to identify each user and keep their information private and secure.

Being able to develop secure user login systems is in fact a whole career and life path in and of itself, but understanding the broad concepts of **Auth** is critically import for all developers. 

Describing auth flow and understanding key terms are very common **interview questions** for junior developers, so lets take some time to research and understand auth and the related concepts.

## Setup

Fork and clone this repository and answer the questions as you research directly in the README. You do not have to pull request and submit this lab, but you will want to have it on hand for reference in the future. 

## Auth Concepts Worksheet

#### Define the following

1. *Authentication*

    A process for identifying users before allowing them through a firewall. Authentication comprises both digital and physical identification methods, such as knowledge factors (usernames, passwords, PINS, etc), possession factors (tokens, ID cards, key fobs) inherence factors (face/voice recognition, fingerprint/retina scans, etc), location and time factors. They can also be single-factor or multifactor depending on desired level of security clearance.

2. *Authorization*

    A process for giving select users secuirty clearance/permission to perform certain functions or access certain resources. It is more-or-less synonymous with access control/client privilege. 

3. Explain how *authentication* and *authorization* are related but distinct concepts.

    Authentication comes first, and means verifying a user's identity. Authorization follows after, and means allowing users specific privileges or permissions based on their identity.

5. *Sessions vs Token based auth*

    In session-based authentication, a user's state is stored in two places: in session data in the server's memory, and in a session ID cookie on the user's browser. The user-side ID is compared to the data in the server's memory on every server request; if the two match, the user is allowed to continue with their requests.

    Token-based authentication is similar, except instead of storing client-side ID data in a browser cookie, it stores it in a JWT (pronounced 'jot), or JSON Web Token, which is stored in localStorage and sent as a header on each request. 

    The latter is preferred for RESTful APIs because it places the burden of data storage on the client's side rather than the server's, minimizing server issues when many users are accessing a system simultaneously.

6. *json web token (also know as a jwt)*

    An object storing client-side user authentication data that may be signed using a JSON Web Signature and/or encrypted with JSON Web Encryption. It is stored in localStorage, which has no expiration time, as opposed to browser cookies and other user-auth data types that are stored in sessionStorage, which is cleared whenever a session ends. There is some contention as to which is better/more secure.

7. *Encoding, encryption and hashing* along with the uses for and differences between the three

    Encoding: transforming data into a type that can be properly understood by another system using publically available data. Priority is on clarity, not security.

    Encryption: transforming data into a type that cannot be understood by others. Uses ciphertexts, algorithms, keys, and other methods to make sure that only select users can access data.

    Hashing: transforming data of various types and lengths into a uniform type and length, generally a short string of seemingly random characters. This is a one-way process, and is a popular method for storing and securing data in a compact format.

8. *oAuth* (pronounced oh-Auth)

    OAuth (or Open Authentication) is an authorization standard in which a third-party identity provider acts as an intermediary between a user and a server. The user provides basic authentication info to the OAuth framework, which then brings that data to the server for authentication. This allows users to access servers without having to directly supply their passwords or other authentication factors. 

    On the plus side, this streamlines the user experience, allowing a user to access multiple APIs without having to remember every password or username. 

    On the downside, anybody who does gain access to your OAuth framework can now access your data on any site it's connected to. It's a sort of 'all your eggs in one basket' approach to user authentication/authorization.

#### Explore and then describe the following npm packages:

1. [bcrypt](https://www.npmjs.com/package/bcrypt)

    A module based on the Blowfish cipher that allows a user to generate their own password hashes. It uses both salting (adding random data to a hash) and adaptive iteration counts (increases size of hash over time) to provide security to users. 

2. [jsonwebtoken](https://www.npmjs.com/package/jsonwebtoken)

    A module for allowing users to generate their own JWTs, or write apps that require/generate them.

3. [passport](https://www.npmjs.com/package/passport)

    A flexible, express-compatible middleware module for authenticating requests using plugins called strategies. 

    * also describe what a *strategy* is in the context of this npm package

    A strategy in the context of Passport is any method for authenticating the user's identity. Passport is compatible with numerous strategies, including OAuth and OpenID, and only has to be told which strategy is being used by which applicaiton.

---

## Licensing
1. All content is licensed under a CC-BY-NC-SA 4.0 license.
2. All software code is licensed under GNU GPLv3. For commercial use or alternative licensing, please contact legal@ga.co.