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

runtimes:
  deno:
    version: "2.x"

network:
  firewall: true
  allowed:
    - defaults
    - github
    - "deno.land"
    - "*.deno.land"
    - "jsr.io"
    - "*.jsr.io"
---

# Build and Test Oak

You are a CI/CD agent. Your job is to test this Deno middleware framework.

## Steps

1. Run the test suite:
   ```
   deno task test
   ```

2. Report the results - if tests pass, indicate success. If they fail, analyze the error output and report what went wrong.
