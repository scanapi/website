---
layout: docs
title: ScanAPI - Documentation

page_name: API Specification Keys
active_page: api_specification_keys

section: Specification
index: 1
---

# API Specification Keys

| KEY              | Description                                                                                           | Type   | Scopes                            |
| ---------------- | ----------------------------------------------------------------------------------------------------- | ------ | --------------------------------- |
| assert           | The test assertion                                                                                    | dict   | tests                             |
| body             | The HTTP body of the request                                                                          | dict   | request                           |
| endpoints        | Represents a list of API endpoints                                                                    | list   | endpoint                          |
| headers          | The HTTP headers                                                                                      | dict   | endpoint, request                 |
| method           | The HTTP method of the request (GET, POST, PUT, PATCH or DELETE). If not set, GET will be used        | string | request                           |
| name             | An identifier                                                                                         | string | endpoint, request, test           |
| params           | The HTTP query parameters                                                                             | dict   | endpoint, request                 |
| path             | A part of the URL path that will be concatenated with possible other paths                            | string | endpoint, request                 |
| requests         | Represents a list of HTTP requests                                                                    | list   | endpoint                          |
| tests            | Represents a list of tests to run against a HTTP response of a request                                | list   | request                           |
| vars             | Key used to define your custom variables to be used along the specification                           | dict   | endpoint, request                 |
| ${custom var}    | Syntax to get the value of the custom variables defined at key `vars`                                 | string | request - after `vars` definition |
| ${ENV_VAR}       | Syntax to get the value of an environment variable                                                    | string | endpoint, request                 |
| $\{\{python_code\}\} | Syntax to get the value of a Python code expression                                               | string | request                           |
