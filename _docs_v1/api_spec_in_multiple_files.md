---
layout: docs
title: API Specification in Multiple Files - Specification
name: API Specification in Multiple Files
active_page: api_spec_in_multiple_files
section: Specification
---

# API Specification in Multiple Files

With `!include`, it is possible to build your API specification in multiple files.

For example, these two files

```yaml
# scanapi.yaml
endpoints:
  - name: scanapi-demo
    path: ${BASE_URL}
    requests: !include include.yaml
```

```yaml
# include.yaml
- name: health
  path: /health/
```

would generate:

```yaml
endpoints:
  - name: scanapi-demo
    path: ${BASE_URL}
    requests:
      - name: health
        path: /health/
```
