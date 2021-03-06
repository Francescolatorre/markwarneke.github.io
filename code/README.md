---
layout: page
use-site-title: true
bigimg:
  - "/img/EaB4Ml7C7fE.jpeg": "https://unsplash.com/photos/EaB4Ml7C7fE"
image: "/img/EaB4Ml7C7fE.jpeg"
share-img: "/img/EaB4Ml7C7fE.jpeg"
---

# Code

This site contains all the code displayed and described on this blog.

Get the [Code](https://github.com/MarkWarneke/markwarneke.github.io/tree/master/code).

## Table of Contents

- [Code](#code)
  - [Table of Contents](#table-of-contents)
  - [Test Infrastructure as Code](#test-infrastructure-as-code)
    - [Getting Started](#getting-started)
    - [Files](#files)
- [Code of Conduct](#code-of-conduct)
- [Contact](#contact)

## Test Infrastructure as Code

This code repositories contains an `azuredeploy.json` and different scripts to create, run and tests a deployment.

### Getting Started

Get the [Code](https://github.com/MarkWarneke/markwarneke.github.io/tree/master/code).
Run:

```powershell
# azuredeploy.ps1
$Name = "MyResourceGroup"
$Location = "WestEurope"

$TemplateFile = "$PSScriptRoot\azuredeploy.json"
$TemplateParameterFile = "$PSScriptRoot\azuredeploy.parameters.json"

New-ParameterFile | Out-File $TemplateParameterFile

# Change Parameter File Properties

New-AzResourceGroup -Name $Name -Location $Location -Confirm
New-AzResourceGroupDeployment -TemplateFile $TemplateFile -TemplateParameterFile $TemplateParameterFile -Verbose
```

### Files

- [adls.acceptance.spec.ps1](./adls.acceptance.spec.ps1)
- [adls.acceptance.Tests.ps1](./adls.acceptance.Tests.ps1)
- [azure-pipelines.yml](./azure-pipelines.yml)
- [azuredeploy.adls.spec.ps1](./azuredeploy.adls.spec.ps1)
- [azuredeploy.json](./azuredeploy.json)
- [azuredeploy.ps1](./azuredeploy.ps1)
- [azuredeploy.spec.ps1](./azuredeploy.spec.ps1)
- [azuredeploy.Tests.ps1](./azuredeploy.Tests.ps1)
- [Get-Acl.ps1](./Get-Acl.ps1)
- [Get-Acl.Tests.ps1](./Get-Acl.Tests.ps1)
- [Integration.Tests.ps1](./Integration.Tests.ps1)
- [LICENSE](./LICENSE)
- [New-ParameterFile.ps1](./New-ParameterFile.ps1)
- [New-ParameterFile.Tests.ps1](./New-ParameterFile.Tests.ps1)
- [New-Readme.ps1](./New-Readme.ps1)
- [README.md](./README.md)

# Code of Conduct

This is a personal repository by [markwarneke](https://github.com/markwarneke).
Microsoft is **NOT** maintaining this repository.
The project sticks to the [code of conduct](https://microsoft.github.io/codeofconduct/)

# Contact

- [twitter MarkWarneke](https://twitter.com/MarkWarneke)
- [mail](mailto:mark.warneke@microsoft.com)

# Generate File Inventory

```powershell
Get-ChildItem -Recurse | % { Write-Host ("- [{0}](./{0})" -f $_.Name)  }
```
