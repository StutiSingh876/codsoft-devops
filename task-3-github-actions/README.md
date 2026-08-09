# Task 3 — CI/CD Pipeline using GitHub Actions

## Objective

The objective of this task is to create an automated CI/CD pipeline using GitHub Actions and configure workflows to run on pushes and Pull Requests, validate the application, generate an artifact, monitor workflow execution, and troubleshoot pipeline failures.

---

# CI/CD Architecture

```text
                         Developer
                             │
                             │ git push
                             ▼
                    ┌──────────────────┐
                    │ GitHub Repository │
                    └────────┬─────────┘
                             │
                     Push / Pull Request
                             │
                             ▼
                    ┌──────────────────┐
                    │ GitHub Actions   │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Ubuntu Runner    │
                    └────────┬─────────┘
                             │
              ┌──────────────┼──────────────┐
              │              │              │
              ▼              ▼              ▼
         Checkout       Validation      File Check
         Repository      / Testing
              │              │              │
              └──────────────┼──────────────┘
                             │
                             ▼
                    Upload Artifact
                             │
                             ▼
                     static-website
```

---

# Workflow Location

GitHub Actions workflows must be placed inside:

```text
.github/workflows/
```

The workflow for this project is:

```text
.github/workflows/ci-cd.yml
```

---

# Pipeline Triggers

The workflow runs automatically when:

### Push

```yaml
push:
  branches:
    - develop
    - main
```

### Pull Request

```yaml
pull_request:
  branches:
    - develop
    - main
```

Therefore, the pipeline runs whenever code is pushed to `develop` or `main`, or when a Pull Request targets either branch.

---

# CI Pipeline

The current pipeline performs the following operations:

```text
Push / Pull Request
        │
        ▼
Checkout Repository
        │
        ▼
Show Repository Structure
        │
        ▼
Verify Website Files
        │
        ▼
Count Website Files
        │
        ▼
Upload Static Website Artifact
```

---

# Workflow Configuration

The workflow is defined in:

```text
.github/workflows/ci-cd.yml
```

```yaml
name: CodSoft CI/CD Pipeline

on:
  push:
    branches:
      - develop
      - main

  pull_request:
    branches:
      - develop
      - main

jobs:
  build-test:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Repository
        uses: actions/checkout@v4

      - name: Show Repository Structure
        run: ls -R

      - name: Verify Website Files
        run: |
          test -f task-1-git-github/website/index.html
          test -f task-1-git-github/website/style.css
          test -f task-1-git-github/website/script.js

      - name: Count Website Files
        run: |
          echo "Website contains:"
          find task-1-git-github/website -type f

      - name: Upload Website Artifact
        uses: actions/upload-artifact@v4
        with:
          name: static-website
          path: task-1-git-github/website
```

---

# Pipeline Components

## 1. GitHub Actions

GitHub Actions provides the automation platform that executes the workflow.

---

## 2. Runner

```yaml
runs-on: ubuntu-latest
```

GitHub provides a temporary Ubuntu environment to execute the workflow.

The runner performs the required operations and is discarded after the workflow finishes.

---

## 3. Checkout

```yaml
uses: actions/checkout@v4
```

This downloads the repository contents onto the runner so that subsequent commands can access the project files.

---

## 4. Repository Validation

The workflow checks whether the required website files exist:

```text
task-1-git-github/website/index.html
task-1-git-github/website/style.css
task-1-git-github/website/script.js
```

If a required file is missing, the workflow fails.

This provides an automated validation step.

---

## 5. Artifact

The workflow uploads the website as:

```text
static-website
```

Artifacts allow files generated or validated by a workflow to be stored with the workflow run.

---

# Failure Debugging

During implementation, the initial GitHub Actions workflow failed because of incorrect YAML indentation.

The debugging process was:

```text
Workflow Failure
      │
      ▼
Open GitHub Actions
      │
      ▼
Inspect Workflow
      │
      ▼
Identify YAML Formatting Problem
      │
      ▼
Correct Indentation
      │
      ▼
Commit Changes
      │
      ▼
Push to GitHub
      │
      ▼
Workflow Successful
```

This demonstrated practical pipeline troubleshooting rather than only creating a successful workflow.

---

# Monitoring Workflow Execution

Workflow runs can be monitored from:

```text
GitHub Repository
       │
       ▼
     Actions
       │
       ▼
CodSoft CI/CD Pipeline
       │
       ▼
Workflow Run
       │
       ▼
build-test
       │
       ├── Logs
       ├── Status
       └── Artifacts
```

The GitHub Actions interface provides logs for each individual workflow step.

---

# CI vs CD

## Continuous Integration

The current implementation provides CI through:

```text
Code Push / Pull Request
          │
          ▼
     GitHub Actions
          │
          ▼
      Validation
          │
          ▼
       Artifact
```

## Continuous Deployment

The deployment stage can be added after successful CI:

```text
             CI
              │
              ▼
        Build / Test
              │
              ▼
      needs: build-test
              │
              ▼
           Deploy
              │
              ▼
       Live Application
```

Automatic deployment is therefore the next extension/bonus stage of this project.

---

# Evidence

For the final demonstration, capture:

* `.github/workflows/ci-cd.yml`
* GitHub Actions workflow
* Successful workflow run
* Workflow logs
* Uploaded artifact
* Failed workflow run
* Corrected workflow run
* Push-triggered execution
* Pull Request-triggered execution

---

# Result

The task demonstrates practical CI automation using GitHub Actions, including event-based workflow triggers, GitHub-hosted runners, repository validation, artifact generation, workflow monitoring, and troubleshooting of pipeline failures.
