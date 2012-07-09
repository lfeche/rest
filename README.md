Rest Wrapper
-------------

HTTP/REST client wrapper that provides a standard interface for making http requests using different http clients.
If no client is specified it will choose the best one you have installed.

Getting Started
==============

Install the gem:

    gem install rest

Create an Rest client:

    @rest = Rest::Client.new()

To choose a specific underlying http client lib:

    @rest = Rest::Client.new(:gem=>:typhoeus)

Supported http libraries are:

* rest-client
* net-http-persistent
* typhoeus

Then use it:

GET
------

    @rest.get(url, options...)

options:

- :params => query params for url
- :headers => headers

POST
-----

    @rest.post(url, options...)

options:

- :body => POST body
- :headers => headers

PUT
------

    @rest.put(url, options...)

options:

- :body => POST body
- :headers => headers

DELETE
-------- 

    @rest.delete(url, options...)

Responses
=========

The response object you get back will always be consistent and will have the following functions:

    response.code
    response.body


Errors
======

If it didn't get a response, you will get a Rest::ClientError

If status code is 40X or 50X, you will get a Rest::HttpError.

