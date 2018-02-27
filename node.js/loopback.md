<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [LoopBack](#loopback)
  - [Install LoopBack](#install-loopback)
  - [Create an application](#create-an-application)
  - [Datasources](#datasources)
    - [MongoDB](#mongodb)
  - [Remote methods](#remote-methods)
  - [User creation and authentication](#user-creation-and-authentication)
  - [Filtering data](#filtering-data)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# [LoopBack](http://loopback.io)

## Install LoopBack

    npm install -g loopback-cli

## Create an application

* Create application with _lb app_
* Create a datasource with _lb datasource_
* Create model with _lb model_ (properties can be added during the creation process)
* Create model properties (after creation) with _lb property_
* Create relations between models with _lb relation_
* Create new API methods with _lb remote-method_
* Create ACL with _lb acl_
* Create a boot script with _lb boot-script_ (generated script example: server/boo/create-access-token.js)

## Datasources

To create a test datasources, create _server/datasources.test.json_ and set the environment variable _NODE_ENV=test_

### MongoDB

Add MongoDB connector:

    yarn add loopback-connector-mongodb

Ceate datasource:

    lb datasource

## Remote methods

    lb remote-method

This function is used to extend functionality of models by defining new methods.

If we add a _buy_ method on product:

* A new endpoint _/Products/{id}/buy_ is automatically created on the API
* We have to declare and implement the _buy_ method on the prototype of the Product model

During the remote method creation, the generator asks for:

* The request arguments (request fields)
* The response arguments (response fields)

## User creation and authentication

Create user by posting on "/Users":

    {
      "email": "<email>",
      "password": "<password>"
    }

Get an authentication token by posting on "/Users/login":

    {
      "email": "<email>",
      "password": "<password>"
    }


## Filtering data

See [Querying data](http://loopback.io/doc/en/lb3/Querying-data.html)
