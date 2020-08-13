---
layout: docs
title: ScanAPI - Documentation

page_name: Configuration File
active_page: config_file

section: Configuration
index: 1
---

# Configuration File

If you want to configure the ScanAPI with a file, you can create a `.scanapi.yaml` file in the root of your project

```yaml
project_name: DemoAPI # This will be rendered in the Report Title.
spec_path: my_path/scanapi.yaml # API specification file path
output_path: my_path/my-report.html # Report output path.
template: my_template.jinja # Custom report template path.
```
