# Release Manifest Schema Documentation

## Overview

This document details the schema structure for the Release Manifest, a YAML specification used to control and track product releases with their associated microservices and components.

## Schema Structure

### Root Object

The release manifest is structured as a YAML document with the following top-level fields:

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| company | string | ✅ | The name of the company releasing the product. |
| product | string | ✅ | The name of the product being released. |
| version | string | ✅ | The version number of the product release (follows semantic versioning). |
| release_date | string (date) | ✅ | The date when the product is released. |
| release_type | string (enum) | ❌ | Type of release, can be: "snapshot", "beta", "alpha", "candidate", "production". |
| epics | array | ✅ | A list of epics included in this release. |
| components | array | ❌ | A list of components included in this release. |
| incidents | array | ❌ | A list of incidents addressed in this release. |
| problems | array | ❌ | A list of problems addressed in this release. |

### Epic Object

Each epic represents a major functionality or theme of development:

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| epic_key | string | ✅ | The unique identifier for the epic. |
| short_desc | string | ✅ | A short description of the epic. |
| url | string (uri) | ✅ | The URL of the epic in the issue tracking system. |
| issues | array | ✅ | List of issues belonging to this epic. |

### Issue Object

Issues appear in epics, incidents, problems, and component sections:

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| issue_key | string | ✅ | The issue key associated with this item. |
| issue_type | string (enum) | ✅ | Type of issue: "story", "bug", "hotfix", "tech_deb", "task", "incident", "problem". |
| short_desc | string | ✅ | A short description or subject of the issue. |
| url | string (uri) | ❌ | The URL of the issue in the issue tracking system. |

### Component Object

Components represent microservices or other deployable elements:

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| name | string | ✅ | The name of the component. |
| version | string | ✅ | The version of the component (follows semantic versioning). |
| description | string | ✅ | A brief description of the component. |
| repository | string (uri) | ✅ | The URL of the repository where the component is hosted. |
| type | string (enum) | ✅ | Type of component: "library", "microservice", "service", "tool", "framework", "plugin". |
| language | string (enum) | ❌ | The programming language used: "JavaScript", "TypeScript", "Python", "Java", etc. |
| issues | array | ❌ | Issues related to this component. |
| build | object | ❌ | Build configuration for the component. |
| deploy | object | ❌ | Deployment configuration for the component. |

#### Build Object

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| method | string (enum) | ❌ | The method used to build: "source", "binary", "docker". |
| context | string | ❌ | The context or directory where the build process is executed. |

#### Deploy Object

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| method | string (enum) | ❌ | The deployment method: "docker", "kubernetes", "serverless", "manual". |
| target | string | ❌ | The target environment or platform for deployment. |

## Examples

See the [examples](../examples) directory for complete YAML examples that demonstrate valid release manifests.

## Validation

You can validate your release manifest using tools in the [tools](../tools) directory.

## JSON Schema References

The full JSON schema definitions can be found in the [spec](../spec) directory:

- [release-manifest.json](../spec/release-manifest.json)
- [components.json](../spec/components.json)
- [epics.json](../spec/epics.json)
- [issue.json](../spec/issue.json)
- [incidents.json](../spec/incidents.json)
- [problems.json](../spec/problems.json)
