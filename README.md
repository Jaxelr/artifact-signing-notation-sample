# Artifact Signing Notation plugin sample

This repository contains sample implementations of using the Notation plugin from artifact signing. For more information on the plugin, please see the [ Notation Plugin for Artifact Signing](https://github.com/Azure/artifact-signing-notation-plugin).

## Workflow examples

- How to build and sign a container image using the Notation plugin for artifact signing. See the [sign-container-image.yml](./.github/workflows/sign-container-image.yml) file.

- How to build and sign a dotnet project using the Notation plugin for artifact signing. This workflow uses the existing dotnet solution on this repository and builds and signs this solution, see the [sign-dotnet-image.yml](./.github/workflows/sign-dotnet-image.yml) file.

