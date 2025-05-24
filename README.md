# Release Manifest

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
[![Schema](https://img.shields.io/badge/Schema-JSON-green.svg)](spec/release-manifest.json)
[![Documentation](https://img.shields.io/badge/Docs-Available-brightgreen.svg)](docs/schema-documentation.md)
[![Best Practices](https://img.shields.io/badge/Best%20Practices-Guide-orange.svg)](docs/best-practices.md)
[![Code of Conduct](https://img.shields.io/badge/Contributor%20Covenant-2.0-4baaaa.svg)](CODE_OF_CONDUCT.md)
[![YAML](https://img.shields.io/badge/Format-YAML-yellow.svg)](examples/product_with_issues.yaml)
[![QuickStart](https://img.shields.io/badge/Quick-Start-ff69b4.svg)](docs/quickstart.md)
[![Status](https://img.shields.io/badge/Status-Active-success.svg)]()

## Table of Contents
- [Release Manifest](#release-manifest)
  - [Table of Contents](#table-of-contents)
  - [Overview](#overview)
  - [Motivation](#motivation)
  - [Project Structure](#project-structure)
  - [Use Case](#use-case)
  - [Goals](#goals)
  - [Getting Started](#getting-started)
  - [Using the Tools](#using-the-tools)
    - [Generating a Release Manifest](#generating-a-release-manifest)
    - [Validating a Release Manifest](#validating-a-release-manifest)
    - [Running Tests](#running-tests)
  - [Contributing](#contributing)
  - [Code of Conduct](#code-of-conduct)
  - [License](#license)

## Overview
This project defines a YAML specification for a **release manifest** to be used in CI/CD pipelines. The manifest helps companies manage and control the release of a product and the microservices that compose it.

## Motivation
Modern products are often composed of multiple microservices, each with its own lifecycle and versioning. Coordinating releases across these services is challenging. A standardized release manifest enables:
- Clear visibility of all microservices in a product
- Version control for each microservice
- Traceability and reproducibility of releases
- Automation in CI/CD pipelines

## Project Structure
```
release-manifest/
├── spec/       # YAML schema(s) and documentation for the release manifest
├── examples/   # Example YAML manifests for different scenarios
├── docs/       # Extended documentation, guides, and diagrams
├── tools/      # Scripts or utilities for validating or generating manifests
├── tests/      # Tests for schema validation and tools
├── README.md   # Project overview and documentation
├── LICENSE     # License file
```
- **spec/**: YAML schema definition and related documentation for the release manifest.
- **examples/**: Example YAML files demonstrating different use cases and scenarios.
- **docs/**: Extended documentation, guides, and diagrams.
- **tools/**: Scripts/utilities to validate, generate, or manipulate release manifests.
- **tests/**: Tests to ensure the schema and tools work as expected.

## Use Case
A company has many products made up of several microservices. For each release, the company needs to specify:
- The product name and version
- The list of microservices included in the release
- The version of each microservice
- Optional metadata (e.g., environment, release date, notes)

## Goals
- Define a clear and extensible YAML schema for release manifests
- Provide documentation and examples
- Enable integration with CI/CD tools

## Getting Started
1. Clone the repository:
   ```sh
   git clone <repo-url>
   cd release-manifest
   ```
2. Read the [Schema Documentation](docs/schema-documentation.md) to understand the structure.
3. Review the [Best Practices Guide](docs/best-practices.md) for recommendations.
4. Examine [examples](examples/) for sample manifests.
5. Use tools in [tools](tools/) to validate or generate manifests.

For more detailed information, see the [documentation](docs/) directory.

## Using the Tools

### Generating a Release Manifest

Use the `generate-manifest.sh` script to create a new release manifest template:

```sh
cd tools
./generate-manifest.sh ../my-release-manifest.yaml
```

This will create a basic manifest template that you can customize for your project.

### Validating a Release Manifest

To validate your release manifest against the schema:

```sh
cd tools
./validate-manifest.sh ../path/to/your-manifest.yaml
```

### Running Tests

To run tests on all example manifests:

```sh
cd tests
./run-tests.sh
```

## Contributing
Contributions are welcome! Please open issues or pull requests to discuss improvements or new features.

## Code of Conduct
This project adheres to a [Code of Conduct](CODE_OF_CONDUCT.md). By participating in this project, you agree to abide by its terms.

## License
[Apache 2.0](LICENSE)
