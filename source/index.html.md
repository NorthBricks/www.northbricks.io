---
title: Northbricks API Reference

language_tabs:
  - http: HTTP
  - shell: Shell
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
  - go: Go

includes:
  - user.swagger
  - bank-auth.swagger
  - banks.swagger
  - accounts.swagger
  - transactions.swagger
  - payments.swagger

search: true
---

# Introduction

Welcome to the Northbricks API! <a href="https://share.hsforms.com/1VMTAez9aTImjB25zLPieLg2p2p1" target="_blank">Contact us</a> if you are interested in our API.

# Postman collection

You can use out Postman test collection to test the Northbricks API. It includes HTTP requests with sample headers and test data.

Postman is a free REST test tool, you can download if from <a href="https://www.getpostman.com" target="_blank">here</a>. Save the content of the link below as a .json file and then import it in the tool as a test collection.

[Download postman collection](northbricks-api.postman_collection.json)

# Connecting to Northbricks API

To be able to connect to the API you need to get an access token. After that you create a request header with the name `Authorization` and value `Bearer [access token]`.

Get an access token with [Postman](https://www.getpostman.com/):  
1. Select authorization type `Oauth2`.  
2. Select add authorization data to `Request headers`.  
3. Click *Get New Access Token*.  
4. Set *Grant Type* `Authorization Code`.  
5. Set *Callback URL* `https://www.getpostman.com/oauth2/callback`.  
6. Set *Auth URL* `https://api.northbricks.io/oauth/authorize`.  
7. Set *Access Token URL* `https://api.northbricks.io/oauth/token`.  
8. Set *Client ID* to your Client ID.  
9. Set *Client Secret* to your Client Secret.  
10. Set *scope* to `read` (scopes are not fully implemented yet).  
11. Set *Client Authentication* `Send as Basic Auth header`.  
12. Click *Request token* and login with a user that you created with [https://api.northbricks.io/signup](https://api.northbricks.io/signup).  
13. You can now start using the api. Try to make a `GET` request to [https://api.northbricks.io/api/v1/banks](https://api.northbricks.io/api/v1/banks) with the aquired token in a request header.

# Adding a bank to a user

First add the bank to the user with [POST /me/banks](/#post-me-banks).

The user needs to give Northbricks permissions to access their assets. Open [/me/banks/{bankId}/auth](/#get-me-banks-bankid-auth) in a browser and let the user login and give permissions to Northbricks.

# Sandbox

The Northbricks API Sandbox can be used to develop and test your application. The banks in the Sandbox contains test users. You can find the credentials for these users on [Sandbox Bank Authentication](sandbox-bank-authentication.html).
