<small>Written by GitHub Copilot</small>
# Build Aseprite

This repository builds Aseprite for Windows using GitHub Actions.

## Overview

It automates the process of:
- installing the required build tools
- downloading the Skia dependency
- cloning the Aseprite source
- configuring CMake with MSVC
- compiling the project
- uploading the resulting executable as a GitHub Actions artifact

## Workflow

The workflow is defined in `.github/workflows/build.yml`.

It runs on:
- push
- workflow_dispatch

## Build steps

1. Install Ninja
2. Download and extract the Skia release
3. Clone Aseprite recursively
4. Configure MSVC
5. Run CMake and build the `aseprite` target
6. Upload the built binary artifact

## Output

The workflow uploads an artifact named:
- `aseprite-windows`

The compiled binaries are expected under:
- `aseprite/build/bin/`

## Requirements

- GitHub Actions
- Windows runner
- Access to the Aseprite and Skia upstream sources

## Troubleshooting

Common issues:
- invalid or removed Skia download URL
- CMake configuration errors
- build failures caused by dependency changes

## License

This repository is a build automation project. Please check upstream project licenses for Aseprite and Skia.
The Aseprite EULA prohibits the distribution of binaries.
