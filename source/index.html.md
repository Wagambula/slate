---
title: SCM API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell: cURL
  - ruby: Ruby
  - php: PHP
  - csharp: C#
  - javascript: NodeJS

includes:
  - accounts # includes activities
  - bill
  - branch # including case
  - cash_bank # including comments and configuration
  - country # including currency
  - customer # including customer type
  - documents
  - goodsReceivedNote
  - installments
  - invoice
  - loans
  - payments
  - products
  - purchase
  - ratings_role
  - sales
  - shipment # including sessions
  - tenant_tokenAuth # includes unit of measure
  - user
  - vendor # includes warehouse
  - errors   

search: true
---

# Introduction

Welcome to the SCM API! You can use our API to access SCM API endpoints, which can get information on various details such as Invoice, products, among others in our database.

We have language bindings in Shell, Ruby, PHP, and JavaScript! You can read this for proper usage of our Supply Chain Management System.

Thi API documentation page was created with [Nmicros](https://nmicros.com/). Feel free to check out other services that we offer.
First things first we have to [Sign in](https://nmicrosscmweb.azurewebsites.net/Account/Login?ReturnUrl=%2F) to the SCM website in order to use our API Endpoints. The API endpoint for SCM can be found by clicking the link [here](https://nmicrosscmapi.azurewebsites.net/)

In order to access the api, from the api endpoint, click authorize and login with your details. Note that you've to be registered for the supply chain application.
