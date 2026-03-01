---
on: pull_request labeled architecture-review-needed
description: Review a pull request for public API design issues when the architecture-review-needed label is added
permissions:
  contents: read
  issues: read
  pull-requests: read
tools:
  github:
    toolsets: [default]
safe-outputs:
  add-comment:
    max: 10

---

# Architecture Review

Review pull request #${{ github.event.pull_request.number }}.

Follow the guidelines in [architecture-review-guidelines.md](https://github.com/Azure/azure-sdk-for-js/blob/main/.github/prompts/architecture-review-guidelines.md).

Post your findings as a review comment on the pull request.
