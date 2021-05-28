---
layout: tutorial
title: Getting Started
name: Setup
next_page_title: TODO
---

# Getting Started

Welcome to ScanAPI's tutorial! This tutorial will guide you on how to test and document an API using
ScanAPI. We will use our demo API for that.

## Get to know the Snippets API - the ScanAPI Demo API

Snippets API was built based on the [Django REST Framework's tutorial][drf-tutorial]. You can access
it at [https://demo.scanapi.dev/](https://demo.scanapi.dev/).

The main goal of this API is to manage code snippets. Each code snippet have the corresponding
syntax highlight for it, based on the language, linenos and style.

This is an example of a code snippet:
[https://demo.scanapi.dev/api/v1/snippets/2/](https://demo.scanapi.dev/api/v1/snippets/2/)

```json
{
  "url": "http://demo.scanapi.dev/api/v1/snippets/2/",
  "id": 2,
  "highlight": "http://demo.scanapi.dev/api/v1/snippets/2/highlight/",
  "owner": "admin",
  "title": "Calculator",
  "code": "def add(x, y):\r\n    return x + y\r\n\r\ndef subtract(x, y):\r\n    return x - y\r\n\r\ndef multiply(x, y):\r\n    return x * y\r\n\r\ndef divide(x, y):\r\n    return x / y",
  "linenos": true,
  "language": "python",
  "style": "vs"
}
```

and this is its highlighted version: [https://demo.scanapi.dev/api/v1/snippets/2/highlight/](https://demo.scanapi.dev/api/v1/snippets/2/highlight/)

<p>
  <img
    src="/assets/images/tutorial/page1/calculator-highlight.png"
    width="200"
    alt="An overview screenshot of the report."
  >
</p>

### Documentation

You can access the Snippets API [swagger][swagger] documentation at:
[https://demo.scanapi.dev/api/v1/swagger-ui/](https://demo.scanapi.dev/api/v1/swagger-ui/)

## Register on Snippets API

Visit the [registration page][demo-api-registration] and create a new user:

<p align="center">
  <img
    src="/assets/images/tutorial/page1/registration.png"
    width="700"
    alt="An overview screenshot of the report."
  >
</p>

<p align="center">
  <img
    src="/assets/images/tutorial/page1/registration-complete.png"
    width="700"
    alt="An overview screenshot of the report."
  >
</p>

## Install ScanAPI

### Requirements

- [python][python] version 3.6 or higher
- [pip][pip-installation]

### Install

```shell
$ pip install scanapi
```

[demo-api-registration]: https://demo.scanapi.dev/api/v1/rest-auth/registration/
[demo-api-swagger]: https://demo.scanapi.dev/api/v1/swagger-ui/
[demo-api]: https://demo.scanapi.dev/
[drf-tutorial]: https://www.django-rest-framework.org/tutorial/1-serialization/
[pip-installation]: https://pip.pypa.io/en/stable/installing/
[python]: https://www.python.org/
[swagger]: https://swagger.io/
