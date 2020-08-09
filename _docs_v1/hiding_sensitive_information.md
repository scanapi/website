---
layout: docs
title: Hiding Sensitive Information - Configuration
name: Hiding Sensitive Information
active_page: hiding_sensitive_information
section: Configuration
---

# Hiding Sensitive Information

If you want to omit sensitive information in the report, you can configure it in the `.scanapi.yaml`
file.

```yaml
report:
  hide_request:
    headers:
      - Authorization
```

The following configuration will print all the headers values for the `Authorization` key for all
the request as `SENSITIVE_INFORMATION` in the report.

In the same way you can omit sensitive information from response.

```yaml
report:
  hide_response:
    headers:
      - Authorization
```

Available attributes to hide: `headers`, `body` and `url`.