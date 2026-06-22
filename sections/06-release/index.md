---
title: Release
has_children: false
nav_order: 7
---

# Release

The project release is managed through GitHub Releases. After the revised version of the project was completed and merged into the `main` branch, a release was created to mark a stable version of the repository.

The release includes the project source code, documentation, tests, and the updated GitHub Actions workflow. This makes it possible to identify a specific stable version of the project and distinguish it from ongoing development changes.

In this project, the first structured release was published as:

```text
v1.0.0 - Sentimazon Refactored Version
```

This release represents the version of the project after the repository was reorganized, automated tests were added, the CI workflow was updated, and the pull request was merged into the main branch.

## Release Strategy

The project follows Semantic Versioning as a simple and widely used versioning strategy in software development. Semantic Versioning uses three main version numbers:

```text
MAJOR.MINOR.PATCH
```

The meaning of each part is:

- **MAJOR:** used for significant changes that may break compatibility with previous versions.
- **MINOR:** used for new features or important improvements that do not break the existing workflow.
- **PATCH:** used for small bug fixes, documentation corrections, or minor improvements.

For this project, version `v1.0.0` was selected because it represents the first stable and structured version of Sentimazon after the Software Engineering revision.

Future releases could follow this strategy. For example, adding a new sentiment model could be released as a minor version, while fixing a small documentation error could be released as a patch version.

## Licensing

The Sentimazon project is released under the MIT License. This license is simple, permissive, and commonly used in open-source software projects.

The MIT License allows users to use, modify, and distribute the project with limited restrictions, as long as the original license and copyright notice are preserved.

This license was selected because it is suitable for an educational software project and allows future users or developers to reuse and improve the project.