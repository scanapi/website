---
layout: docs
title: ScanAPI - Documentation
name: Basic Structure
active_page: basic_structure
section: Specification
---

# Basic Structure

You can write ScanAPI specifications in YAML or JSON. In this guide, we use only YAML examples but JSON works equally well.

A sample ScanAPI specification written in YAML looks like:

```yaml
api:
  endpoints:
    - name: sample-api
      path: http://api.example.com/v1
      requests:
        - name: users
          path: /users
          method: get
          tests:
            - name: status_code_is_200
              assert: {% raw %} ${{ response.status_code == 200 }} {% endraw %}
```

This specification follows a tree structure.

One value defined in a node will propagate to it's children, concatenating the values.

In the example above, for instance, the final path of the request will be:
```
http://api.example.com/v1/users
```
Which is a result of the concatenation of the **sample-api** endpoint path `http://api.example.com/v1` with the **users** request path `/users`.

```
http://api.example.com/v1 (sample-api endpoint path) + /users (users request path)
```

## API Section

The `api` key is the main key of the specification. It is a reserved word that marks the root of the specification and must not appear in any other place	Everything should be under this section. Anything outside the `api` key will be ignored.

Inside the `api` key you will define the endpoints that you want to scan.

### Available keys

- \- endpoints

## Endpoints Section

The `endpoints` key represents a new tree branch, in the form of a list. The purpose of an endpoint is to aggregate common properties of requests. You can append as many endpoints as you like.

```
endpoint = non-leaf node
request = leaf
```

### Available keys

Each item of the endpoints list has the following keys available:

- \- endpoints
- \- headers
- \- name
- \- params
- \- path
- \- requests
- \- vars

## Requests Section

The requests section represents a list of HTTP requests. Inside a request it will also be defined the expected behavior of its response.

Requests can only be defined under an endpoint.

### Available keys

Each item of the requests list has the following keys available:

- \- body
- \- headers
- \- method
- \- name
- \- params
- \- path
- \- tests
- \- vars


## Tests Section

The tests section is where it will be defined the tests for a request.

### Available keys

Each item of the tests list has the following keys available:

- \- assert
- \- name


# Specification keys

## api

It is a reserved word that marks the root of the specification and must not appear in any other place	.

type: dict

## assert

Is the actual test statement. It describes the expected behavior for a response.

type: string
syntax: python code

## body

The content that will be sent as the HTTP request body.

type: dict

## endpoints

It is the key word for the [endpoints section](#endpoints-section).

type: list

## headers

The content that will be sent as the HTTP request header.

type: dict

## method

The HTTP method for the request. Currently the supported methods are GET, POST, PUT, PATCH and DELETE.

type: string

## name

A identifier for the current resource (endpoint, request or test).

type: string

## params

The HTTP query parameters.

type: dict

## path

The request URL.

type: string

## requests

It is the key word for the [requests section](#requests-section).

type: list

## tests

It is the key word for the [tests section](#tests-section).

type: list

## vars

Key used to define your custom variables to be used along the specification.

Read more about [custom variables](#todo).

type: dict


# Specification Keys Summary

| KEY              | Description                                                                                         | Type   | Scopes                            |
| ---------------- | --------------------------------------------------------------------------------------------------- | ------ | --------------------------------- |
| api              | It is reserver word that marks the root of the specification and must not appear in any other place | dict   | root                              |
| assert           | The test assertion                                                                                  | dict   | tests                             |
| body             | The HTTP body of the request                                                                        | dict   | request                           |
| endpoints        | It represents a list of API endpoints                                                               | list   | endpoint                          |
| headers          | The HTTP headers                                                                                    | dict   | endpoint, request                 |
| method           | The HTTP method of the request (GET, POST, PUT, PATCH or DELETE). If not set, GET will be used      | string | request                           |
| name             | An identifier                                                                                       | string | endpoint, request, test           |
| params           | The HTTP query parameters                                                                           | dict   | endpoint, request                 |
| path             | A part of the URL path that will be concatenated with possible other paths                          | string | endpoint, request                 |
| requests         | It represents a list of HTTP requests                                                               | list   | endpoint                          |
| tests            | It represents a list of tests to run against a HTTP response of a request                           | list   | request                           |
| vars             | Key used to define your custom variables to be used along the specification                         | dict   | endpoint, request                 |
| ${custom var}    | A syntax to get the value of the custom variables defined at key `vars`                             | string | request - after `vars` definition |
| ${ENV_VAR}       | A syntax to get the value of an environment variable                                                | string | endpoint, request                 |
| $\{\{python_code\}\} | A syntax to get the value of a Python code expression                                               | string | request                           |
