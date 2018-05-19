# Northbricks API Documentation website
[![Build Status](https://travis-ci.org/NorthBricks/www.northbricks.com.svg)](https://travis-ci.org/NorthBricks/www.northbricks.com)

This is [Northbricks website for developers](http://www.northbricks.io).

The website contains both static content and content generated from the Swagger specifications of the REST API. See [update swagger spec](#update-swagger-spec) to see how to update the generated content.

## Run local server

Start local server.
```sh
bundle exec middleman server
```

## Deploy

Deploy to production.
```sh
./deploy.sh
```

## Update swagger spec

Install widdershins.
```sh
npm install -g widdershins
npm install widdershins
```

Copy latest swagger files to `source/swagger/` and name them `[service-name].swagger.yaml`.

Generate documentation from swagger files with `widdershins`.
```sh
node node_modules/widdershins/widdershins.js -y -n -s source/swagger/user.swagger.yaml -o source/includes/_user.swagger.md
node node_modules/widdershins/widdershins.js -y -n -s source/swagger/bank-auth.swagger.yaml -o source/includes/_bank-auth.swagger.md
node node_modules/widdershins/widdershins.js -y -n -s source/swagger/banks.swagger.yaml -o source/includes/_banks.swagger.md
node node_modules/widdershins/widdershins.js -y -n -s source/swagger/accounts.swagger.yaml -o source/includes/_accounts.swagger.md
node node_modules/widdershins/widdershins.js -y -n -s source/swagger/transactions.swagger.yaml -o source/includes/_transactions.swagger.md
```

Now remove the first section in the generated file(s).

## Prerequisites Ubuntu

These dependencies need to be installed to build and run on Ubuntu.
```sh
sudo apt-get install nodejs npm zlib1g-dev ruby-full
```