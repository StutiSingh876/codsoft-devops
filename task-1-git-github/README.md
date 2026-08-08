# Task 1 – Git & GitHub Version Control

## Objective

The objective of this task is to learn and demonstrate the complete Git and GitHub workflow used in professional software development. This includes repository management, branching strategies, pull requests, merge conflict resolution, and collaboration best practices.

---

## Technologies Used

* Git
* GitHub
* HTML5
* CSS3
* JavaScript

---

## Repository Structure

```text
task-1-git-github/
│
├── website/
│   ├── index.html
│   ├── style.css
│   └── script.js
│
└── README.md
```

---

## Features Implemented

* Created a Git repository and connected it to GitHub.
* Practiced version control using commits.
* Created and managed feature branches.
* Used the Git Flow branching strategy (`main`, `develop`, `feature/*`).
* Pushed branches to GitHub.
* Created Pull Requests.
* Merged feature branches into the `develop` branch.
* Resolved a real merge conflict.
* Maintained meaningful commit messages.
* Configured branch protection rules (Bonus).

---

## Git Workflow Followed

```text
main
│
└── develop
      │
      ├── feature/landing-page
      │
      ├── feature/header-update
      │
      └── feature/team-a
```

Workflow:

1. Create a feature branch from `develop`.
2. Implement the required changes.
3. Commit the changes with meaningful commit messages.
4. Push the feature branch to GitHub.
5. Create a Pull Request.
6. Review and merge into `develop`.
7. Delete the feature branch after merging.

---

## Commands Used

### Clone Repository

```bash
git clone https://github.com/StutiSingh876/codsoft-devops.git
```

### Create Branch

```bash
git checkout -b feature/landing-page
```

### Check Status

```bash
git status
```

### Stage Changes

```bash
git add .
```

### Commit Changes

```bash
git commit -m "Add initial landing page"
```

### Push Branch

```bash
git push -u origin feature/landing-page
```

### Pull Latest Changes

```bash
git pull origin develop
```

### Merge Branch

```bash
git merge feature/team-a
```

### Delete Branch

```bash
git branch -d feature/team-a
```

---

## Merge Conflict Resolution

A merge conflict was intentionally created by modifying the same line of code in two different feature branches.

Conflict resolution steps:

1. Attempted to merge the second branch.
2. Git detected conflicting changes.
3. Opened the conflicted file.
4. Removed Git conflict markers.
5. Chose the final version of the code.
6. Staged the resolved file.
7. Completed the merge with a merge commit.

This demonstrated practical knowledge of resolving merge conflicts.

---

## Screenshots

Include screenshots of:

* Repository homepage
* Branch list
* Pull Request
* Merge commit
* Merge conflict resolution
* Commit history
* Branch protection rules (Bonus)

---

## Learning Outcomes

Through this task, I learned:

* Git repository management
* Local and remote repositories
* Branching strategies
* Pull Requests
* Merge operations
* Merge conflict resolution
* Best practices for commit history
* GitHub collaboration workflow

---

## Author

**Stuti Singh**


