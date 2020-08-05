---
layout: docs
title: Python Code - Specification
name: Python Code
active_page: python_code
section: Specification
---

# Python Code

You can add Python code to the API specification by using the syntax:

```yaml
${{my_python_code}}
```

For example

```yaml
body:
  uuid: 5c5af4f2-2265-4e6c-94b4-d681c1648c38
  name: Tarik
  yearsOfExperience: ${{2 + 5}}
  languages:
    - ruby
      go
  newOpportunities: false
```

What I can use inside the `${{}}` syntax?
Any python code that **can run inside an `eval` python command**.
A short list of modules will be already available for you. They are all the imports of
[this file](https://github.com/scanapi/scanapi/blob/master/scanapi/evaluators/code_evaluator.py#L1).
