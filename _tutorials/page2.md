---
layout: tutorial
title: API Sign Up
name: API Sign Up
previous_page_title: Setup
next_page_title: Run
---

# Snippets API Sign Up

This tutorial will use our demo API, Snippets API, to show how to use ScanAPI. Snippets API was
built based on the [Django REST Framework's tutorial][drf-tutorial]. You can access it at
[demo.scanapi.dev/](https://demo.scanapi.dev/).

The main goal of this API is to manage code snippets. Each code snippet have the corresponding
syntax highlight for it, based on the language, linenos and style.

This is an example of a code snippet:
[demo.scanapi.dev/api/v1/snippets/2/](https://demo.scanapi.dev/api/v1/snippets/2/)

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
  "style": "emacs"
}
```

and this is its highlighted version: [demo.scanapi.dev/api/v1/snippets/2/highlight/](https://demo.scanapi.dev/api/v1/snippets/2/highlight/)

<p align="center">
  <img
    src="/assets/images/tutorial/page2/calculator-highlight.png"
    width="500"
    alt="An overview screenshot of the report."
  >
</p>

### Documentation

You can access the Snippets API [swagger][swagger] documentation at:
[demo.scanapi.dev/api/v1/swagger-ui/](https://demo.scanapi.dev/api/v1/swagger-ui/)

## Sign Up

Visit the [registration page][demo-api-registration] and create a new user:

<p align="center">
  <img
    src="/assets/images/tutorial/page2/registration.png"
    width="900"
    alt="User registration form."
  >
</p>

<p align="center">
  <img
    src="/assets/images/tutorial/page2/registration-complete.png"
    width="900"
    alt="User registration complete, returning the user key."
  >
</p>

Great, now that you already have an user registered in the Snippets API, let's get started using
ScanAPI!

[demo-api-registration]: https://demo.scanapi.dev/api/v1/rest-auth/registration/
[demo-api-swagger]: https://demo.scanapi.dev/api/v1/swagger-ui/
[demo-api]: https://demo.scanapi.dev/
[drf-tutorial]: https://www.django-rest-framework.org/tutorial/1-serialization/
[swagger]: https://swagger.io/
