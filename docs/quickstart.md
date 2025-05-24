# Quick Start Guide

This guide will help you start using the Release Manifest for your projects.

## Overview

The Release Manifest is a YAML-based specification for tracking and managing product releases, especially for products composed of multiple microservices.

## Prerequisites

- Basic understanding of YAML
- Git for version control
- A text editor or IDE

## Creating Your First Release Manifest

1. **Start with the basic structure**:

```yaml
company: YourCompany
product: YourProduct
version: 1.0.0
release_date: 2025-05-24
release_type: production
```

2. **Add epics and their issues**:

```yaml
epics:
  - epic:
    epic_key: EPIC-001
    short_desc: "Feature Set A"
    url: "https://your-issue-tracker.com/browse/EPIC-001"
    issues:
      - issue:
        issue_key: ISSUE-101
        issue_type: story
        short_desc: "Implement feature X"
        url: "https://your-issue-tracker.com/browse/ISSUE-101"
      - issue:
        issue_key: BUG-102
        issue_type: bug
        short_desc: "Fix issue with feature Y"
        url: "https://your-issue-tracker.com/browse/BUG-102"
```

3. **Include components**:

```yaml
components:
  - component:
    name: service-a
    version: 0.5.0
    description: "Handles core functionality"
    repository: "https://github.com/your-org/service-a"
    type: microservice
    language: Java
    issues:
      - issue:
        issue_key: ISSUE-101
        issue_type: story
        short_desc: "Implement feature X"
        url: "https://your-issue-tracker.com/browse/ISSUE-101"
```

4. **Save the file** as `release-manifest.yaml` in your project root.

## Validating Your Manifest

Use the validation script from the tools directory:

```sh
cd tools
./validate-manifest.sh ../path/to/your-manifest.yaml
```

## Integration with CI/CD Pipelines

For CI/CD integration, add a validation step to your pipeline configuration file:

```yaml
validate_manifest:
  script:
    - ./tools/validate-manifest.sh release-manifest.yaml
  stage: validate
```

## Next Steps

- Read the [full schema documentation](schema-documentation.md)
- See the [best practices guide](best-practices.md)
- Explore the [example manifests](../examples/)
- Contribute to the project
