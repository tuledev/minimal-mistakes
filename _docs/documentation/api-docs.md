---
description: Summary for API Docs tool
---

# API Documentation

## Problem

Currently, I have an existing project. It's written in Go, and don't have any useful API Docs. So I tried to have a look.

## What are current world-wise tools for API docs?

* Swagger [http://swagger.io](http://swagger.io)
* APIDoc [http://apidocjs.com](http://apidocjs.com)
* Postman [https://www.getpostman.com](https://www.getpostman.com)

## Swagger

Tools for implementing the OpenAPI specification

#### Starting from scratch? 

* Use the [Swagger Editor](http://editor.swagger.io/) to create your OAS definition and then use [Swagger Codegen](https://swagger.io/swagger-codegen/) to generate server implementation. 
* Use the [Swagger UI](http://swagger.io/swagger-ui/) to visualize and document your OAS definition 
* Design, document and develop APIs as a team using [SwaggerHub](http://swaggerhub.com/) 

#### Creating the OAS file from an existing API? 

Finding an easy way to generate the OpenAPI definition from an existing API can be challenging. You have to reverse engineer the API and get acquainted with the process of generating the OAS from existing APIs.  The good news is that Swagger tools can help you do this with ease.  

* Use  [Swagger Core open source project](https://github.com/swagger-api/swagger-core)  to create the OAS from your existing Java APIs. Swagger Core supports frameworks like JAX-RS or node.js.  

Have a look at this example to see how Swagger Core can help your JAX-RS implemented API -  [https://github.com/swagger-api/swagger-core/wiki/Swagger-Core-JAX-RS-Project-Setup-1.5.X](https://github.com/swagger-api/swagger-core/wiki/Swagger-Core-JAX-RS-Project-Setup-1.5.X) 

* [Swagger Inspector](https://goo.gl/cjDSNg) allows you to easily and quickly auto-generate an OAS definition from any API endpoint right from your browser 

If on the other hand you're an API Consumer who wants to integrate with an API that has an OpenAPI definition you can use [Swagger Inspector](https://goo.gl/cjDSNg) or the online version of [Swagger UI](http://petstore.swagger.io/) to explore the API \(given that you have a URL to the APIs Swagger definition\) - and then use [Swagger Codegen](https://swagger.io/swagger-codegen) to generate the client library of your choice.  In either case - be sure to check out the long list of [open source projects](https://swagger.io/open-source-integrations/) and our commercial offering, [SwaggerHub](http://swaggerhub.com/).   

#### Pros

* Lots of documentation
* Large community
* Strong framework

#### Cons

* Require a lot of effort, especially for existing project

## APIDoc

Inline documentation for RESTful web APIs. Generate docs for annotations in source code

```javascript
/** 
 * @api {get} /user/:id Request User information
 * @apiName GetUser
 * @apiGroup User
 *
 * @apiParam {Number} id Users unique ID.
 *
 * @apiSuccess {String} firstname Firstname of the User.
 * @apiSuccess {String} lastname  Lastname of the User.
 */
```

#### Pros

* Simple to use
* Good documentation

#### Cons

* Can't run spec
* Docs can be out of date without testing

## Postman

Postman is a collaboration platform for API development.

Have 3 tires, focus on limiting team size.

#### Pros

* Simple to use
* Enviroment variable
* Example 
* Public document

#### Cons

* Input/Update API Docs manunally for each API
* Price is based on memebers in team. 

## Conclusion 

In my situation, I chose Postman, because it's simplest. I don't have enough resource to write a full docs with APIDocs, and it's hard with Swagger too.

In the next project, I will try Swagger, or at least APIDoc

