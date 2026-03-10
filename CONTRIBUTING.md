# Contributing to WA-EIP

Welcome! This document outlines how members of the **Washington - Emerging Infections Program** GitHub organization can contribute to existing projects **and** create new repositories.

Thank you for your interest in contributing! We're excited to work with you to improve this project. 

## 📌 Before You Begin

- Please read our [Code of Conduct](CODE_OF_CONDUCT.md).
- If you are new to GitHub, please review this introduction to [Collaborating on GitHub](https://nw-page.github.io/standards/gh/gh_collab_tutorial.html#steps-for-collaborating-on-github-using-the-command-line).
- Make sure to check for existing issues or pull requests before creating new ones.
- For questions or ideas, feel free to open a discussion or reach out directly via our communication channels or reach out at [respnet@doh.wa.gov](mailto:respnet@doh.wa.gov).
- Follow the organization’s [Security Policy](SECURITY.md) 

---

## 📋 Table of Contents
1. [How to Contribute](#-how-to-contribute)
- [Creating a New Repository](#-creating-a-new-repository)
- [Contributing to Existing Repositories](#-contributing-to-existing-repositories)
2. [Documentation](#documentation)
- [Release Cycle Process](#release-cycle-process)
- [Branch Strategy](#branch-strategy)
- [Commit Guidelines](#commit-guidelines)
- [Step-by-Step Process](#step-by-step-process)
3. [Best Practices Checklist](#-best-practices-checklist)

---

## 🚀 How to Contribute

We welcome contributions! You can contribute in many ways:

- By creating your own repos
- By opening issues to provide feedback and share ideas in existing repos.
- By fixing typos in documentation
- By submitting Pull Request (PR) to fix opened issues
- By submitting Pull Request (PR) to suggest new features (it is considered good practice to open an issue for discussion before working on a pull request for a new feature).

---

### 🧱 Creating a New Repository

1. **Get approval** from an org maintainer or core team (if required).
2. **Create the repository** using the org’s [starter template](https://github.com/your-org/repo-template) (or clone an existing one).

 > **Repository Naming Convention:**  
   > When creating a new repository within this org, please follow this naming convention to ensure clarity, consistency, and ease of navigation:  
   >  
   > `<organization>-<team>-<project>-<sub-project>-<optional:platform>`  
   >  
   > | Segment                  | Description                                                                  |  
   > |--------------------------|------------------------------------------------------------------------------|  
   > | `<organization>`         | The organization or partner name (e.g., `wadoh`, `phskc`)                |  
   > | `<team>`                 | Team or department responsible (e.g., `diqa`, `rhino`, `phskc`, etc.)                   |  
   > | `<project>`              | Main project or domain (e.g., `respnet`, `mpox`)                     |  
   > | `<sub-project>`          | Specific component or module (e.g., `reporting`, `etl`)                      |  
   > | `<platform>` _(optional)_| Platform or environment used (e.g., `dbx`)                     |  

   > **Examples:**  
   > - `wadoh-diqa-respnet-reporting-dbx` (Washington DOH DIQA team working on RESP-NET reporting pipeline in Databricks)  
   > - `wadoh-rhino-respnet-casefinding` (Washington DOH RHINO team working on RESP-NET case finding scripts)  
   > - `phskc-team-respnet-caseascertainment` (Public Health Seattle King County team working on RESP-NET case ascertainment scripts)  


3. **Set up pre-commit secrets hook**
   - Review our [security policy]([url](https://github.com/WA-EIP/.github/blob/main/SECURITY.md)) to correctly set up `.gitignore` and install a pre-commit hook for increased security
4. **Add the following required files:**
   - `README.md`
5. **Set repository settings:**
   - Default branch to `main`
   - Enable branch protection rules (if needed)
   - Add teams or collaborators
6. **Share your new repo** in the org’s communication channel so others can follow or contribute.

---

### 🛠 Contributing to Existing Repositories

To contribute to an existing project within the organization:

1. **Find appropriate repository.** 
2. **Fork or clone the repo.**
3. **Create a branch** for your changes.
4. **Make your updates** (code, docs, or other).
5. **Open a pull request** and describe your changes clearly.
6. Follow any **repository-specific guidelines** in that repo's `CONTRIBUTING.md`.

> Each repo may have its own workflow or requirements. Check the README or open an issue if you’re unsure.

---

## Documentation

This section will outline our Release Cycle Process and detail commit guidelines.

---

### Release Cycle Process
This repository uses an automated release workflow that manages versioning and releases through GitHub Actions. The process follows a structured branching strategy and automated releases through pull requests. If you would like to read more information about release cycles, please [click here].

To initiate releases on the repo you created, please select the [NAME] workflow by following the steps below. 


[insert template picture here when "Create a new repository"] OR [instructions for how to create release cycle process]

[click here]: https://nw-page.github.io/standards/gh/release.html
---

### Branch Strategy
The table below lists naming conventions you may use for your branches based off your main branch. Utilizing a branch strategy can help identify what work is being done in the branch.

| Branch         | Purpose                                      |
|----------------|----------------------------------------------|
| `main`         | Production-ready code                        |
| `release/*`    | Release preparation (e.g., `release/0.1.0`)  |
| `feature/*`    | New feature development                      |
| `fix/*`        | Bug fixes                                    |
| `docs/*`       | Documentation changes                        |
| `refactor/*`   | Code refactoring                             |
| `chore/*`      | Maintenance tasks                            |

---

### Commit Guidelines

All commits must follow the conventional commits format listed below. Conventional commit formatting allows the automated release workflow to update the Release Cycle. 

- ✅ `feat:` - Use when adding a new feature.
- 🐞 `fix:` - Use when fixing a bug.
- 🧹 `chore:` - Use for updates that don't affect functionality: updates to dependencies or cleanup.
- 📚 `docs:` - Documentation changes only (updating README or other docs).
- 🎨 `style:` - Code style changes (formatting, indentation, spacing, etc.) without changing logic.
- 🧼 `refactor:` - Code refactoring (renaming variables, objects, splitting functions) without changing logic.
- ⚡ `perf:` - Code that improves performance without changing logic.
- 🧪 `test:` - Test updates
- 🛠️ `build:` - Build system changes
- 🔁 `ci:` - CI configuration changes (GitHub actions, etc.)
- ⏪ `revert:` - Reverting/undoing commits or previous changes


Example:
```bash
git commit -m "feat: add data validation"
git commit -m "fix: correct calculation bug"
git commit -m "chore: update dependencies"
```

### Step-by-Step Process

#### 1. Start New Feature Development

```bash
# Create new feature branch from main
git checkout main
git pull
git checkout -b feature/your-feature-name
# Work on your feature
# Commit using conventional commits:
git add .
git commit -m "feat: add new functionality"
git push origin feature/your-feature-name
```

#### 2. Create a release branch 

```bash
# Create release branch from main for the release cycle
git checkout main
git pull
git checkout -b release/0.1.0
git push origin release/0.1.0
```

#### 3. Create Feature Pull Request

1. Go to GitHub repository
2. Click "Pull requests"
3. Click "New pull request"
4. Set branches:
    - base: release/0.1.0
    - compare: feature/your-feature-name
5. Add descriptive title following commit convention (e.g., "feat: implement user authentication")
6. Add description detailing the changes
7. Request reviews
8. Tests will run automatically

#### 4. Merge Features to Release Branch

- Review and approve feature pull request
- Merge approved features into release branch
- Continue until release is ready

#### 5. Create Release Pull Request

1. Once release branch contains all intended features:
2. Create PR from release branch to main
3. Title must follow commit convention (e.g., "release: v0.1.0")
4. Description should include:
    - Summary of changes
    - Notable features
    - Breaking changes (if any)
    - Updated dependencies (if any)
5.  Request reviews

#### 6. Final Release Process

When release pull request is approved and merged to main, the workflow automatically:
  - Creates a version tag (e.g., v0.1.0)
  - Generates GitHub Release with release notes
  - Closes the release cycle
    
### Version Numbering

Follow semantic versioning (MAJOR.MINOR.PATCH):
  - MAJOR (1.0.0) - Breaking changes
  - MINOR (0.1.0) - New features (backwards compatible)
  - PATCH (0.0.1) - Bug fixes

### Important Notes

- All changes must go through pull requests
- Pull request titles must follow conventional commit format
- Release pull requests require approval before merging to main
- Tests must pass before merges are allowed
- Each release should have clear documentation of changes


## ✅ Best Practices Checklist

Before publishing or contributing to a repository:

- [ ] Contributions follow the org’s [Code of Conduct](CODE_OF_CONDUCT.md).
- [ ] Repository includes standard files (`README`, `LICENSE`, etc.).
- [ ] Code follows [Security Policy](SECURITY.md) and is sanitized of sensitive information.
- [ ] Documentation is updated.
   - [ ] **Optional**: Code/commits follow [Commit Guidelines](CODE_OF_CONDUCT.md).



