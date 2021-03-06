# AlertsManagement

> see https://aka.ms/autorest

This is the AutoRest configuration file for AlertManagement.

---

## Getting Started

To build the SDK for AlertManagement, simply [Install AutoRest](https://aka.ms/autorest/install) and in this folder, run:

> `autorest`

To see additional help and options, run:

> `autorest --help`

---

## Configuration

### Basic Information

These are the global settings for the AlertManagement API.

## Suppression
``` yaml
directive:
  - suppress: R3025
    reason: The rule applied incorrectly to base class.
    where:
      - $.definitions.ManagedResource
  - suppress: R3026
    reason: The rule applied incorrectly to base class.
    where:
      - $.definitions.ManagedResource
```

``` yaml
title: AlertsManagementClient
description: AlertsManagement Client
openapi-type: arm
tag: package-2019-06-preview
```

### Tag: package-2019-06-preview

These settings apply only when `--tag=package-2019-06-preview` is specified on the command line.

```yaml $(tag) == 'package-2019-06-preview'
input-file:
  - Microsoft.AlertsManagement/preview/2019-05-05-preview/AlertsManagement.json
  - Microsoft.AlertsManagement/stable/2019-06-01/SmartDetectorAlertRulesApi.json
```


### Tag: package-2019-06

These settings apply only when `--tag=package-2019-06` is specified on the command line.

```yaml $(tag) == 'package-2019-06'
input-file:
  - Microsoft.AlertsManagement/stable/2019-06-01/SmartDetectorAlertRulesApi.json
```

### Tag: package-2019-03

These settings apply only when `--tag=package-2019-03` is specified on the command line.

```yaml $(tag) == 'package-2019-03'
input-file:
  - Microsoft.AlertsManagement/stable/2019-03-01/AlertsManagement.json
  - Microsoft.AlertsManagement/stable/2019-03-01/SmartDetectorAlertRulesApi.json
```

### Tag: package-preview-2019-05

These settings apply only when `--tag=package-preview-2019-05` is specified on the command line.

``` yaml $(tag) == 'package-preview-2019-05'
input-file:
  - Microsoft.AlertsManagement/preview/2019-05-05-preview/AlertsManagement.json
```

### Tag: package-2018-05

These settings apply only when `--tag=package-2018-05` is specified on the command line.

``` yaml $(tag) == 'package-2018-05'
input-file:
- Microsoft.AlertsManagement/stable/2018-05-05/AlertsManagement.json
```

### Tag: package-2018-05-preview

These settings apply only when `--tag=package-2018-05` is specified on the command line.

``` yaml $(tag) == 'package-2018-05-preview'
input-file:
- Microsoft.AlertsManagement/preview/2018-05-05-preview/AlertsManagement.json
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
  - repo: azure-libraries-for-java
  - repo: azure-sdk-for-go
  - repo: azure-resource-manager-schemas
    after_scripts:
      - node sdkauto_afterscript.js alertsmanagement/resource-manager
```

## C#

These settings apply only when `--csharp` is specified on the command line.
Please also specify `--csharp-sdks-folder=<path to "SDKs" directory of your azure-sdk-for-net clone>`.

``` yaml $(csharp)
csharp:
  azure-arm: true
  license-header: MICROSOFT_MIT_NO_VERSION
  namespace: Microsoft.Azure.Management.AlertsManagement
  output-folder: $(csharp-sdks-folder)/alertsmanagement/Microsoft.Azure.Management.AlertsManagement/src/Generated
  clear-output-folder: true
```

## Python

These settings apply only when `--python` is specified on the command line.
Please also specify `--python-sdks-folder=<path to the root directory of your azure-sdk-for-python clone>`.
Use `--python-mode=update` if you already have a setup.py and just want to update the code itself.

``` yaml $(python)
python-mode: create
python:
  azure-arm: true
  license-header: MICROSOFT_MIT_NO_VERSION
  payload-flattening-threshold: 2
  namespace: azure.mgmt.alertsmanagement
  package-name: azure-mgmt-alertsmanagement
  clear-output-folder: true
```

``` yaml $(python) && $(python-mode) == 'update'
python:
  no-namespace-folders: true
  output-folder: $(python-sdks-folder)/alertsmanagement/azure-mgmt-alertsmanagement/azure/mgmt/alertsmanagement
```

``` yaml $(python) && $(python-mode) == 'create'
python:
  basic-setup-py: true
  output-folder: $(python-sdks-folder)/alertsmanagement/azure-mgmt-alertsmanagement
```

## Go

See configuration in [readme.go.md](./readme.go.md)

## Java

See configuration in [readme.java.md](./readme.java.md)

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
  - $(this-folder)/Microsoft.AlertsManagement/preview/2019-05-05-preview/AlertsManagement.json
  - $(this-folder)/Microsoft.AlertsManagement/stable/2019-06-01/SmartDetectorAlertRulesApi.json
  - $(this-folder)/Microsoft.AlertsManagement/stable/2019-03-01/AlertsManagement.json
  - $(this-folder)/Microsoft.AlertsManagement/stable/2019-03-01/SmartDetectorAlertRulesApi.json
  - $(this-folder)/Microsoft.AlertsManagement/stable/2018-05-05/AlertsManagement.json
  - $(this-folder)/Microsoft.AlertsManagement/preview/2018-05-05-preview/AlertsManagement.json

```

If there are files that should not be in the `all-api-versions` set, 
uncomment the  `exclude-file` section below and add the file paths.

``` yaml $(tag) == 'all-api-versions'
#exclude-file: 
#  - $(this-folder)/Microsoft.Example/stable/2010-01-01/somefile.json
```

