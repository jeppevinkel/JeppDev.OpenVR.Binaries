# JeppDev.OpenVR.Binaries

[![NuGet](https://img.shields.io/nuget/v/JeppDev.OpenVR.Binaries)](https://www.nuget.org/packages/JeppDev.OpenVR.Binaries)
[![NuGet Downloads](https://img.shields.io/nuget/dt/JeppDev.OpenVR.Binaries)](https://www.nuget.org/packages/JeppDev.OpenVR.Binaries)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE.txt)

A NuGet package that provides the native [OpenVR](https://github.com/ValveSoftware/openvr) 
binaries by Valve Corporation for use in .NET projects.

Versions of this package mirror OpenVR releases directly and are updated automatically 
via a GitHub Actions workflow.

## Supported Platforms

| Platform | Architecture | Binary | Since |
|---|---|---|---|
| Windows | x64 | `openvr_api.dll` | All versions |
| Windows | x86 | `openvr_api.dll` | All versions |
| Linux | x64 | `libopenvr_api.so` | All versions |
| Linux | ARM64 | `libopenvr_api.so` | v1.11.11 |

## Installation

### NuGet.org
```shell
dotnet add package JeppDev.OpenVR.Binaries
```

### GitHub Packages
Add the source to your `nuget.config`:
```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <packageSources>
    <add key="github" 
         value="https://nuget.pkg.github.com/jeppevinkel/index.json" />
  </packageSources>
</configuration>
```
Then install:
```shell
dotnet add package JeppDev.OpenVR.Binaries
```

## Usage

Once added to your project the appropriate native binaries will be automatically 
copied to your output directory at build time. No additional configuration is required.

The binaries will be resolved for your target platform:
- `win-x64` → `openvr_api.dll`
- `win-x86` → `openvr_api.dll`
- `linux-x64` → `libopenvr_api.so`
- `linux-arm64` → `libopenvr_api.so`

## Versioning

This package mirrors OpenVR release versions exactly.

| JeppDev.OpenVR.Binaries | OpenVR |
|---|---|
| 2.x.x | 2.x.x |

If a new OpenVR release is available but the package has not yet been updated, please create an issue.

## Why Does This Exist?

The OpenVR binaries need to be distributed alongside .NET projects that use the 
OpenVR API. This package automates that process and allows the binaries to be 
versioned and updated independently of any managed wrapper library.

## License

This package is licensed under the [MIT License](LICENSE).

The included OpenVR binaries are the property of Valve Corporation and are 
redistributed under the [BSD 3-Clause License](THIRD_PARTY_NOTICES).

See [THIRD_PARTY_NOTICES](THIRD_PARTY_NOTICES) for the full license 
text and copyright notice as required by the BSD 3-Clause license terms.

## Acknowledgements

- [OpenVR](https://github.com/ValveSoftware/openvr) by Valve Corporation