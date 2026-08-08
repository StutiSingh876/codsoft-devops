# CodSoft DevOps Internship Tasks

A practical DevOps repository containing three internship tasks completed as part of the **CodSoft DevOps Internship**.

The repository demonstrates Git and GitHub version control, Nginx web-server deployment, and CI/CD automation using GitHub Actions.

---

## Tasks

| Task   | Project                             | Status            |
| ------ | ----------------------------------- | ----------------- |
| Task 1 | Git & GitHub Version Control        | Completed         |
| Task 2 | Nginx Web Server Deployment         | Completed locally |
| Task 3 | CI/CD Pipeline using GitHub Actions | CI completed      |
| Bonus  | Automatic Cloud Deployment          | Planned           |

---

# Repository Architecture

```text
                         CODSOFT DEVOPS
                              │
                              ▼
                    ┌───────────────────┐
                    │ GitHub Repository  │
                    └─────────┬─────────┘
                              │
             ┌────────────────┼────────────────┐
             │                │                │
             ▼                ▼                ▼
      ┌─────────────┐  ┌─────────────┐  ┌──────────────┐
      │   Task 1    │  │   Task 2    │  │    Task 3    │
      │ Git/GitHub  │  │    Nginx    │  │ GitHub       │
      │             │  │             │  │ Actions      │
      └─────────────┘  └─────────────┘  └──────┬───────┘
                                               │
                                               ▼
                                      ┌─────────────────┐
                                      │ CI/CD Workflow  │
                                      └────────┬────────┘
                                               │
                                  ┌────────────┼────────────┐
                                  ▼            ▼            ▼
                              Checkout     Validate      Artifact
                              Repository   Website       Upload
```

---

# Repository Structure

```text
codsoft-devops/
│
├── .github/
│   └── workflows/
│       └── ci-cd.yml
│
├── task-1-git-github/
│   ├── README.md
│   └── website/
│       ├── index.html
│       ├── style.css
│       └── script.js
│
├── task-2-nginx/
│   ├── README.md
│   └── screenshots/
│
├── task-3-github-actions/
│   ├── README.md
│   └── screenshots/
│
└── README.md
```

---

# Overall DevOps Workflow

```text
                 Developer
                     │
                     ▼
              Git Local Repository
                     │
                     │ git push
                     ▼
              GitHub Repository
                     │
             ┌───────┴────────┐
             │                │
             ▼                ▼
       Pull Request          Push
             │                │
             ▼                ▼
       Code Review      GitHub Actions
             │                │
             └───────┬────────┘
                     ▼
              CI Validation
                     │
                     ▼
              Build / Artifact
                     │
                     ▼
                Deployment
```

---

# Technologies Used

* Git
* GitHub
* GitHub Pull Requests
* GitHub Rulesets
* Linux / WSL
* Nginx
* HTML
* CSS
* JavaScript
* GitHub Actions
* YAML
* ApacheBench

---

# Task 1 — Git & GitHub

The first task demonstrates practical Git and GitHub version-control workflows.

### Implemented

* Git repository creation
* GitHub repository connection
* Commits
* Feature branches
* `develop` integration branch
* Pull Requests
* Merge operations
* Merge conflict resolution
* Clean commit history
* GitHub Ruleset for branch protection

### Workflow

```text
main
 │
 ▼
develop
 │
 ├── feature/landing-page
 │
 ├── feature/header-update
 │
 ├── feature/team-a
 │
 └── feature/team-b
       │
       ▼
 Pull Request
       │
       ▼
   develop
```

Detailed documentation:

```text
task-1-git-github/README.md
```

---

# Task 2 — Nginx Web Server Deployment

The second task demonstrates deploying a static website using Nginx on a local Linux environment.

### Implemented

* Nginx installation
* Static website hosting
* Nginx server configuration
* Virtual hosts / server blocks
* Custom error pages
* Nginx configuration testing
* Browser accessibility testing
* ApacheBench performance testing

### Architecture

```text
Browser
   │
   ▼
Local Hostname
   │
   ▼
  Nginx
   │
   ├── Virtual Host 1
   │       │
   │       ▼
   │   Website 1
   │
   └── Virtual Host 2
           │
           ▼
       Website 2
```

Detailed documentation:

```text
task-2-nginx/README.md
```

---

# Task 3 — CI/CD Pipeline using GitHub Actions

The third task demonstrates automated CI using GitHub Actions.

### Implemented

* GitHub Actions workflow
* Push triggers
* Pull Request triggers
* Ubuntu GitHub-hosted runner
* Repository checkout
* Website file validation
* Repository structure verification
* Artifact generation
* Workflow monitoring
* Pipeline failure debugging

### CI Architecture

```text
Developer
    │
    │ git push
    ▼
GitHub Repository
    │
    ▼
GitHub Actions
    │
    ▼
Ubuntu Runner
    │
    ├── Checkout Repository
    │
    ├── Verify Website Files
    │
    ├── Display Repository Structure
    │
    ├── Count Website Files
    │
    └── Upload Artifact
            │
            ▼
       static-website
```

Detailed documentation:

```text
task-3-github-actions/README.md
```

---

# Learning Outcomes

Through these tasks, I gained practical experience with:

* Version control using Git
* GitHub collaboration workflows
* Feature branching
* Pull Requests
* Merge conflict resolution
* Branch protection
* Linux server administration
* Nginx configuration
* Virtual hosting
* Static website deployment
* Performance testing
* GitHub Actions
* CI pipeline automation
* YAML workflow configuration
* CI failure debugging
* Build artifacts

---

## Author

**Stuti Singh**

CodSoft DevOps Internship
