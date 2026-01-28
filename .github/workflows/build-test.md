---
name: Build and Test
on:
  push:
    branches: [main]
  pull_request:
    branches: [main]
  workflow_dispatch:

permissions:
  contents: read
  issues: read
  pull-requests: read

engine:
  id: copilot
  model: claude-sonnet-4

network:
  firewall: true
  allowed:
    - defaults
    - github
    - deno
---

# Build and Test Oak

You are a CI/CD agent. Your job is to build and test this Deno web framework.

## Steps

1. Check Deno version:
   ```
   deno --version
   ```

2. Run the test suite:
   ```
   deno task test
   ```

3. Report the results - if tests pass, indicate success. If they fail, analyze the error output and report what went wrong.
