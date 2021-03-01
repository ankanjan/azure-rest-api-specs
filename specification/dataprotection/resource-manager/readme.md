# DataProtection

> see https://aka.ms/autorest

This is the AutoRest configuration file for DataProtection.



---
## Getting Started
To build the SDK for DataProtection, simply [Install AutoRest](https://aka.ms/autorest/install) and in this folder, run:

> `autorest`

To see additional help and options, run:

> `autorest --help`
---

## Configuration



### Basic Information
These are the global settings for the DataProtection API.

``` yaml
title: Data Protection Client
description: Open API 2.0 Specs for Azure Data Protection service
openapi-type: arm
tag: package-2021-02-preview
csharp-sdks-folder: ./Generated/CSharp
python-sdks-folder: ./Generated/Python
go-sdk-folder: ./Generated/Golang

license-header: MICROSOFT_MIT
```

### Validations
Run validations when `--validate` is specified on command line

``` yaml $(validate)
azure-validator: true
model-validator: true
semantic-validator: true
message-format: json
```

### Tag: package-2021-02-preview

These settings apply only when `--tag=package-2021-02-preview` is specified on the command line.

``` yaml $(tag) == 'package-2021-02-preview'
input-file:
- Microsoft.DataProtection/preview/2021-02-01-preview/dataprotection.json
```
---
# Code Generation


## Swagger to SDK

This section describes what SDK should be generated by the automatic system.
This is not used by Autorest itself.

``` yaml $(swagger-to-sdk)
swagger-to-sdk:
  - repo: azure-sdk-for-net
  - repo: azure-sdk-for-python
  - repo: azure-sdk-for-java
  - repo: azure-sdk-for-go
  - repo: azure-sdk-for-js
  - repo: azure-sdk-for-node
  - repo: azure-sdk-for-ruby
    after_scripts:
      - bundle install && rake arm:regen_all_profiles['azure_mgmt_data_protection']
```


## C#

These settings apply only when `--csharp` is specified on the command line.
Please also specify `--csharp-sdks-folder=<path to "SDKs" directory of your azure-sdk-for-net clone>`.

```yaml $(csharp)
csharp:
  azure-arm: true
  payload-flattening-threshold: 1
  license-header: MICROSOFT_MIT_NO_VERSION
  namespace: Microsoft.Azure.Management.DataProtection
  output-folder: $(csharp-sdks-folder)/dataprotection/Microsoft.Azure.Management.DataProtection/src/Generated
  clear-output-folder: true
```

## Go

See configuration in [readme.go.md](./readme.go.md)

## Java

See configuration in [readme.java.md](./readme.java.md)

## Multi-API/Profile support for AutoRest v3 generators

AutoRest V3 generators require the use of `--tag=all-api-versions` to select api files.

This block is updated by an automatic script. Edits may be lost!

``` yaml $(tag) == 'all-api-versions' /* autogenerated */
# include the azure profile definitions from the standard location
require: $(this-folder)/../../../profiles/readme.md

# all the input files across all versions
input-file:
  - Microsoft.DataProtection/preview/2021-02-01-preview/dataprotection.json  
```

If there are files that should not be in the `all-api-versions` set,
uncomment the  `exclude-file` section below and add the file paths.

``` yaml $(tag) == 'all-api-versions'
#exclude-file:
#  - $(this-folder)/Microsoft.Example/2010-01-01/somefile.json
```