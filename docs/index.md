---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "json-formatter Provider"
subcategory: ""
description: This plugin will format / beautify a JSON string.
  
---

# json-formatter Provider

This plugin will format / beautify a JSON string.


## Usage

### Arguments

|Name    |Required    |Description|
|:---|:---|:---|
|json|Yes|A JSON string.|
|indent|No|The character(s) to use for an indent. Has a default value of two spaces.|

### Example

```hcl
data "json-formatter_format" "test" {
    json = "{\"a\":\"b\",\"myObj\":{\"prop1\":1}}"
    indent = "    "
}

output "test_output" {
    value = data.json-formatter_format.test.result
}
```

This will output:

```sh
Outputs:

test_output = <<EOT
{
    "a": "b",
    "myObj": {
        "prop1": 1
    }
}
EOT
```