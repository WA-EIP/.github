# Contributing to WA-EIP

Welcome! This document outlines how members of the **Washington - Emerging Infections Program** GitHub organization can contribute to existing projects **and** create new repositories.

Thank you for your interest in contributing! We're excited to work with you to improve this project. 

## 📌 Before You Begin

- Please read our [Code of Conduct](CODE_OF_CONDUCT.md)
- If you are new to GitHub, please review this introduction to [Collaborating on GitHub](https://nw-page.github.io/standards/gh/gh_collab_tutorial.html)
- Make sure to check for existing issues or pull requests before creating new ones
- For questions or ideas, feel free to open a discussion or reach out directly via our communication channels or reach out at [respnet@doh.wa.gov](mailto:respnet@doh.wa.gov)
- Follow the organization’s [Security Policy](SECURITY.md)

---

## 📋 Table of Contents
- [How to Contribute](#-how-to-contribute)
- [Creating a New Repository](#-creating-a-new-repository)
- [Contributing to Existing Repositories](#-contributing-to-existing-repositories)

---

## 🚀 How to Contribute

We welcome contributions! You can contribute in many ways:

- By creating your own repos
- By opening issues to provide feedback and share ideas in existing repos
- By fixing typos in documentation
- By submitting Pull Request (PR) to fix opened issues
- By submitting Pull Request (PR) to suggest new features (it is considered good practice to open an issue for discussion before working on a pull request for a new feature)


---

## 🧱 Creating a New Repository

1. **Get approval** from an org maintainer or core team (if required)

2. Review our [Security Policy](SECURITY.md) to **install [pre-commit hooks](https://github.com/WA-EIP/hooks)**

3. **Create the repository**:
   
   - [ ] Follow **naming convention**:

      <details open>
      <summary><b>Repository Naming Convention</b><br></summary>
      When creating a new repository within this org, please follow this naming convention to ensure clarity, consistency, and ease of navigation:  

      `<organization>-<team>-<project>-<sub-project>-<optional:platform>`  

      | Segment                  | Description                                                                  |  
      |--------------------------|------------------------------------------------------------------------------|  
      | `<organization>`         | The organization or partner name (e.g., `wadoh`, `phskc`)                |  
      | `<team>`                 | Team or department responsible (e.g., `diqa`, `rhino`, `phskc`, etc.)                   |  
      | `<project>`              | Main project or domain (e.g., `respnet`, `mpox`)                     |  
      | `<sub-project>`          | Specific component or module (e.g., `reporting`, `etl`)                      |  
      | `<platform>` _(optional)_| Platform or environment used (e.g., `dbx`)                     |  

      > **Examples:**  
      > - `wadoh-diqa-respnet-reporting-dbx` (Washington DOH DIQA team working on RESP-NET reporting pipeline in Databricks)  
      > - `wadoh-rhino-respnet-casefinding` (Washington DOH RHINO team working on RESP-NET case finding scripts)  
      > - `phskc-team-respnet-caseascertainment` (Public Health Seattle King County team working on RESP-NET case ascertainment scripts)
      </details> <br>
   - [ ] Add a **detailed description** of your repository <br>
   - [ ] Choose **[visibility](https://github.com/WA-EIP/.github/blob/main/SECURITY.md#protect-sensitive-information)**: Internal or Private <br>
   - [ ] Turn on <b>Add README</b> to add `README.md` <br>
   - [ ] <b>Add .gitignore</b> by choosing the `R template` <br>
   - [ ] <b>Add license</b> by selecting `⚖️ MIT License` <br>
   - [ ] Initiate **[Release Cycle workflow](https://github.com/WA-EIP/.github/blob/main/VERSIONING_STANDARDS.md#-release-cycle-process)**

5. **Set repository settings:**
   - Default branch to `main`
   - Enable branch protection rules (if needed)
   - Add teams or collaborators
6. **Share your new repo** in the org’s communication channel so others can follow or contribute


---

## 🛠 Contributing to Existing Repositories

To contribute to an existing project within the organization:

1. **Find appropriate repository** 
2. **Fork or clone the repo**
3. **Create a branch** for your changes
4. **Make your updates** (code, docs, or other)
5. **Open a pull request** and describe your changes clearly
6. Follow any **repository-specific guidelines** in that repo's `CONTRIBUTING.md`

Each repo may have its own workflow or requirements. Check the `README` or open an issue if you’re unsure.

[↑ Back to Top](#-table-of-contents)
