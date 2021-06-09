---
layout: tutorial
title: Tests
name: Tests
previous_page_title: Run
next_page_title: Env Vars
---

# Writing Tests

It is time to test the response you received. Change your specification file `scanapi.yaml` to have
the following content:

```yaml
endpoints:
  - name: snippets-api
    path: http://demo.scanapi.dev/api/v1/
    headers:
      Content-Type: application/json
    requests:
      - name: health
        method: get
        path: /health/
        tests: # this is new
          - name: status_code_is_200 # this is new
            assert: {% raw %} ${{ response.status_code == 200 }} {% endraw %} # this is new
          - name: body_equals_ok # this is new
            assert: {% raw %} ${{ response.json() == "OK!" }} {% endraw %} # this is new
```

Run ScanAPI again:

```shell
$ scanapi run
```

Reload your browser and check the `TESTS` now:

<p align="center">
  <img
    src="/assets/images/tutorial/page4/report-tests.png"
    width="900"
    alt="Test details"
  >
</p>

Inside the {% raw %} `${{ }}` {% endraw %} notation, you can write pure [Python Code][python-code].
`response` is a [requests.Response][requests-response] object containing the response information
of the request.

Note that the `Tests Summary` now brings some useful information about the tests. If anything goes
wrong or if any test fails, `scanapi` command will return an error with the corresponding exit code.

[python-code]: http://127.0.0.1:4000/docs_v1/specification/python_code.html
[requests-response]: https://docs.python-requests.org/en/latest/api/#requests.Response
