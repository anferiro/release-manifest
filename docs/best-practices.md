# Best Practices for Release Manifest

This document outlines the recommended best practices for creating and maintaining release manifests.

## General Guidelines

1. **Keep It Up to Date**: The release manifest should be updated as part of the release process, not as an afterthought.
   
2. **Automation First**: Automate the generation and validation of the manifest whenever possible.
   
3. **Single Source of Truth**: The release manifest should be the definitive reference for what's included in a release.

## Structure Guidelines

1. **Semantic Versioning**: Always follow [Semantic Versioning](https://semver.org/) for product and component versions.
   
2. **Consistent Naming**: Use consistent naming conventions for components and issue keys.
   
3. **Descriptive Short Descriptions**: Write short descriptions that are clear and informative.
   
4. **Complete URLs**: Always include URLs to your issue tracking system to enable traceability.

## Organization Recommendations

1. **Group by Epics**: Organize issues into epics to provide a hierarchical view of functionality.
   
2. **Link Components to Issues**: Ensure there's a clear connection between components and the issues they implement.
   
3. **Document Changes**: Use the manifest to document all changes, including features, bugs, and incidents.

## Process Integration

1. **CI/CD Integration**: Integrate manifest generation and validation into your CI/CD pipeline.
   
2. **Approval Process**: Use the release manifest as part of your release approval process.
   
3. **Artifact Association**: Associate the release manifest with built artifacts.
   
4. **Historical Records**: Maintain historical release manifests for audit and rollback purposes.

## Examples

### Good Example:

```yaml
company: ExampleCorp
product: Customer Portal
version: 2.4.0
release_date: 2025-05-24
release_type: production

epics:
  - epic:
    epic_key: AUTH-100
    short_desc: "Authentication Improvement Project"
    url: "https://jira.example.com/browse/AUTH-100"
    issues:
      - issue:
        issue_key: AUTH-101
        issue_type: feature
        short_desc: "Implement OAuth2 authentication"
        url: "https://jira.example.com/browse/AUTH-101"
```

### Poor Example:

```yaml
company: ExampleCorp
product: Portal
version: 2.4
issues:
  - Add login
  - Fix bugs
```

## Common Mistakes to Avoid

1. **Incomplete Information**: Missing required fields or important context.
2. **Inconsistent Structure**: Not following the schema consistently.
3. **Outdated Information**: Not updating the manifest to reflect late changes.
4. **Generic Descriptions**: Using vague or uninformative descriptions.
5. **Orphaned Issues**: Including issues that aren't linked to components or epics.

## Tools

Refer to the [tools](../tools) directory for utilities to help with manifest creation and validation.
