# PyPi Increment Publish

---
### Prerequisites

To use this action successfully, ensure your target repository meets these criteria:
1. **Version Format** Your `pyproject.toml` project version must be an integer prefixed with 'v' (e.g., `version = "v1"`).
2. **PyPI Trusted Publishing**: Your PyPI project must be configured to accept trusted publishing from your GitHub organization and repository name.

---
### Setup
Copy this workflow into your repository at `.github/workflows/publish.yml`:

```yaml
name: Publish to PyPI
on:
  workflow_dispatch:
permissions:
  contents: write
jobs:
  build-and-publish:
    runs-on: ubuntu-latest
    environment: pypi
    permissions:
      id-token: write
      contents: write
    steps:
      - uses: actions/checkout@v4
      - uses: MineFartS/PyPi-Increment-Publish@v3
```

---
## Usage
This action is configured to run on demand via the workflow_dispatch event. This gives you full control over exactly when a new release is published.

1. Navigate to Actions: Click the Actions tab at the top of your GitHub repository page.

2. Select the Workflow: In the left sidebar under All workflows, click on Publish to PyPI.

3. Open Run Menu: Look for the floating gray banner on the right side and click the Run workflow dropdown button.

4. Choose Branch: Select the target branch you want to build and release from (usually main).

5. Execute: Click the green Run workflow button to launch the pipeline.

---
