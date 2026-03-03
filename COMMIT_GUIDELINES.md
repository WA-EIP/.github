# Commit Guidelines

## Overview
This section will outline our Release Cycle Process and detail commit guidelines.


# Release Cycle Process

## Overview

This repository uses an automated release workflow that manages versioning and releases through GitHub Actions. The process follows a structured branching strategy and automated releases through pull requests.

## Branch Strategy
| Branch         | Purpose                                      |
|----------------|----------------------------------------------|
| `main`         | Production-ready code                        |
| `release/*`    | Release preparation (e.g., `release/0.1.0`)  |
| `feature/*`    | New feature development                      |
| `fix/*`        | Bug fixes                                    |
| `docs/*`       | Documentation changes                        |
| `refactor/*`   | Code refactoring                             |
| `chore/*`      | Maintenance tasks                            |

## Commit Guidelines

All commits must follow the conventional commits format:

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

## Step-by-Step Process

### 1. Start New Feature Development

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

### 2. Create a release branch 

```bash
# Create release branch from main for the release cycle
git checkout main
git pull
git checkout -b release/0.1.0
git push origin release/0.1.0
```

### 3. Create Feature Pull Request

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

### 4. Merge Features to Release Branch

- Review and approve feature pull request
- Merge approved features into release branch
- Continue until release is ready

### 5. Create Release Pull Request

1. Once release branch contains all intended features:
2. Create PR from release branch to main
3. Title must follow commit convention (e.g., "release: v0.1.0")
4. Description should include:
    - Summary of changes
    - Notable features
    - Breaking changes (if any)
    - Updated dependencies (if any)
5.  Request reviews

### 6. Final Release Process

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