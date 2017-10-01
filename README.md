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
node node_modules/widdershins/widdershins.js -y -n -s source/swagger/transaction.swagger.yaml -o source/includes/_transaction.swagger.md
node node_modules/widdershins/widdershins.js -y -n -s source/swagger/user.swagger.yaml -o source/includes/_user.swagger.md
```

Now remove the first section in the generated file(s).
