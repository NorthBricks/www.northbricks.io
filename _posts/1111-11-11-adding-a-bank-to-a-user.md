---
layout: post
title: "Adding a bank to a user"
date: 2019-09-25 17:32:47 +0200
categories: guides
---

Learn how to add a bank to a user and let the user authenticate with the bank.
<!--more-->

First add the bank to the user with [POST /me/banks](/#post-me-banks).

The user needs to give Northbricks permissions to access their assets. Open [/me/banks/{bankId}/auth](/#get-me-banks-bankid-auth) in a browser and let the user login and give permissions to Northbricks.