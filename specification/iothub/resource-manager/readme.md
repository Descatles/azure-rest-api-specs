# IotHub

> see https://aka.ms/autorest

This is the AutoRest configuration file for IotHub.

---

## Getting Started

To build the SDK for IotHub, simply [Install AutoRest](https://aka.ms/autorest/install) and in this folder, run:

> `autorest`

To see additional help and options, run:

> `autorest --help`

---

## Configuration

### Basic Information

These are the global settings for the IotHub API.

``` yaml
openapi-type: arm
tag: package-2020-04
```


### Tag: package-2020-04

These settings apply only when `--tag=package-2020-04` is specified on the command line.

```yaml $(tag) == 'package-2020-04'
input-file:
  - Microsoft.Devices/stable/2020-04-01/iothub.json
```
### Tag: package-2020-03

These settings apply only when `--tag=package-2020-03` is specified on the command line.

``` yaml $(tag) == 'package-2020-03'
input-file:
  - Microsoft.Devices/stable/2020-03-01/iothub.json
```

### Tag: package-2019-11

These settings apply only when `--tag=package-2019-11` is specified on the command line.

``` yaml $(tag) == 'package-2019-11'
input-file:
  - Microsoft.Devices/stable/2019-11-04/iothub.json
```

### Tag: package-preview-2019-07

These settings apply only when `--tag=package-preview-2019-07` is specified on the command line.

``` yaml $(tag) == 'package-preview-2019-07'
input-file:
  - Microsoft.Devices/preview/2019-07-01-preview/iothub.json
```

### Tag: package-2019-03

These settings apply only when `--tag=package-2019-03` is specified on the command line.

``` yaml $(tag) == 'package-2019-03'
input-file:
  - Microsoft.Devices/stable/2019-03-22/iothub.json
```

### Tag: package-preview-2019-03

These settings apply only when `--tag=package-preview-2019-03` is specified on the command line.

``` yaml $(tag) == 'package-preview-2019-03'
input-file:
  - Microsoft.Devices/preview/2019-03-22-preview/iothub.json
```

### Tag: package-2018-12-preview

These settings apply only when `--tag=package-2018-12-preview` is specified on the command line.

``` yaml $(tag) == 'package-2018-12-preview'
input-file:
- Microsoft.Devices/preview/2018-12-01-preview/iothub.json
```

### Tag: package-2018-04

These settings apply only when `--tag=package-2018-04` is specified on the command line.

``` yaml $(tag) == 'package-2018-04'
input-file:
- Microsoft.Devices/stable/2018-04-01/iothub.json
```

### Tag: package-2018-01

These settings apply only when `--tag=package-2018-01` is specified on the command line.

``` yaml $(tag) == 'package-2018-01'
input-file:
- Microsoft.Devices/stable/2018-01-22/iothub.json
```

### Tag: package-2017-07

These settings apply only when `--tag=package-2017-07` is specified on the command line.

``` yaml $(tag) == 'package-2017-07'
input-file:
- Microsoft.Devices/stable/2017-07-01/iothub.json
```

### Tag: package-2017-01

These settings apply only when `--tag=package-2017-01` is specified on the command line.

``` yaml $(tag) == 'package-2017-01'
input-file:
- Microsoft.Devices/stable/2017-01-19/iothub.json
```

### Tag: package-2016-02

These settings apply only when `--tag=package-2016-02` is specified on the command line.

``` yaml $(tag) == 'package-2016-02'
input-file:
- Microsoft.Devices/stable/2016-02-03/iothub.json
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
    after_scripts:
      - python ./scripts/multiapi_init_gen.py azure-mgmt-iothub
  - repo: azure-sdk-for-java
  - repo: azure-sdk-for-go
  - repo: azure-sdk-for-js
  - repo: azure-sdk-for-node
  - repo: azure-sdk-for-ruby
    after_scripts:
      - bundle install && rake arm:regen_all_profiles['azure_mgmt_iot_hub']
  - repo: azure-resource-manager-schemas
    after_scripts:
      - npm install --prefix generator && npm run postprocessor iothub/resource-manager --prefix generator && npm install --prefix tools && npm run test --prefix tools
```

## C#

These settings apply only when `--csharp` is specified on the command line.
Please also specify `--csharp-sdks-folder=<path to "SDKs" directory of your azure-sdk-for-net clone>`.

``` yaml $(csharp)
csharp:
  azure-arm: true
  license-header: MICROSOFT_MIT_NO_VERSION
  namespace: Microsoft.Azure.Management.IotHub
  output-folder: $(csharp-sdks-folder)/iothub/Microsoft.Azure.Management.IotHub/src/Generated
  clear-output-folder: true
```

## Go

See configuration in [readme.go.md](./readme.go.md)

## Java

See configuration in [readme.java.md](./readme.go.md)

## AzureResourceSchema

See configuration in [readme.azureresourceschema.md](./readme.azureresourceschema.md)

## Multi-API/Profile support for AutoRest v3 generators

AutoRest V3 generators require the use of `--tag=all-api-versions` to select api files.

This block is updated by an automatic script. Edits may be lost!

``` yaml $(tag) == 'all-api-versions' /* autogenerated */
# include the azure profile definitions from the standard location
require: $(this-folder)/../../../profiles/readme.md

# all the input files across all versions
input-file:
  - $(this-folder)/Microsoft.Devices/stable/2020-03-01/iothub.json
  - $(this-folder)/Microsoft.Devices/stable/2019-11-04/iothub.json
  - $(this-folder)/Microsoft.Devices/preview/2019-07-01-preview/iothub.json
  - $(this-folder)/Microsoft.Devices/stable/2019-03-22/iothub.json
  - $(this-folder)/Microsoft.Devices/preview/2019-03-22-preview/iothub.json
  - $(this-folder)/Microsoft.Devices/preview/2018-12-01-preview/iothub.json
  - $(this-folder)/Microsoft.Devices/stable/2018-04-01/iothub.json
  - $(this-folder)/Microsoft.Devices/stable/2018-01-22/iothub.json
  - $(this-folder)/Microsoft.Devices/stable/2017-07-01/iothub.json
  - $(this-folder)/Microsoft.Devices/stable/2017-01-19/iothub.json
  - $(this-folder)/Microsoft.Devices/stable/2016-02-03/iothub.json

```

If there are files that should not be in the `all-api-versions` set,
uncomment the  `exclude-file` section below and add the file paths.

``` yaml $(tag) == 'all-api-versions'
#exclude-file: 
#  - $(this-folder)/Microsoft.Example/stable/2010-01-01/somefile.json
```
