# Security Policy

This document defines the security expectations for using the Washington State - Emerging Infections Program GitHub organization. It focuses on preventing accidental disclosure of sensitive information and establishing guardrails for safe collaboration.

It covers:
* What information should not be committed or shared in GitHub (including in issues and pull requests)
* Required and recommended repository guardrails such as `.gitignore`, GitHub Secret Scanning and Push Protection, and local secret hooks
* What to do if sensitive information is accidentally committed or pushed
* How to report a suspected vulnerability

This policy applies to:
* All repositories in this GitHub organization (public and private)
* All contributors

This policy does not replace agency, legal, or data use requirements.
* Follow all applicable Washington State Department of Health policies and any data use agreements.
   * If guidance conflicts, follow the stricter requirement.
* Patient level or other restricted data should not be stored in GitHub. Use approved systems for storage and sharing.

## Protect sensitive information

> [!IMPORTANT]
> **Objectives**
> * Prevent sensitive information leaks to GitHub
> * Set up guardrails such as `.gitignore`, GitHub protections, and local hooks
> * Scrub private repositories before making them public
>
> If sensitive information is leaked and committed to a remote repository, it can remain in git history and may require significant effort to remove.

> [!CAUTION]
> If data is not already public, it likely should not be made public through a pull request or a commit.

**The following cannot be included in any repository or any local commit.**

| Type | Examples |
| --- | --- |
| File Paths | Network drives<br>Shared internal drives |
| Server Names | ODBC connections |
| Credentials | SSH keys<br>Tokens (REDCap, Azure, GitHub, etc.)<br>AWS paths<br>Usernames<br>Passwords<br>Blob or bucket keys<br>Connection strings |
| Identifiable Information | Case addresses<br>Case names<br>Any private health information (PHI)<br>Geographic location<br>|

## Security guardrails

We use layered controls to reduce the risk of accidentally exposing sensitive information in GitHub, including `.gitignore`, GitHub Push Protection, and local secret hooks. No single control is sufficient on its own.

### `.gitignore`

`.gitignore` helps prevent accidental commits of local files that may contain sensitive information.

Contributor expectations:
* Never hardcode credentials in scripts
* Store secrets in local configuration files (for example `.env`, `.json`, `.txt`, `rcreds`) that are excluded by `.gitignore`, or use environment variables
* If you include a configuration template in the repository, it must contain placeholders only and no real secrets
* Do not add sensitive files to the repo and rely on `.gitignore` later. If a secret is committed once, it may persist in git history even after removal

### GitHub push protections

We have enabled GitHub Secret Scanning and Push Protection for every repository where the feature is available.

What this does:
* Secret scanning helps detect secrets that were committed
* Push protection scans code pushes and blocks pushes containing supported secret types, and it can generate an alert when a contributor bypasses the block

Contributor expectations:
* If your push is blocked, assume a real exposure risk until proven otherwise
* Remove the secret from the change, rotate or revoke it if it was real, then push again
* If you are unsure whether the flagged content is a secret, pause and contact the maintainers before bypassing the block

### Secret hooks

In addition to GitHub’s push protection, we use pre-commit secret hooks as a local guardrail to reduce the chance of committing sensitive information in the first place.

What secret hooks are for:
* They run locally during git actions (for example, at commit time)
* They are intended to catch credentials and sensitive patterns before they ever reach GitHub
* It allows us to define custom secrets and sensitive patterns for our needs

How to install:
* Follow the installation and update instructions [here](https://github.com/DOH-EPI-Coders/secret-hooks)
* Contact maintainers at [respnet@doh.wa.gov](mailto:respnet@doh.wa.gov) for additional support

## If you accidentally commit or push sensitive information

Act immediately
1. Stop further pushes and notify the repository maintainers at [respnet@doh.wa.gov](mailto:respnet@doh.wa.gov)
2. Rotate or revoke the exposed credential or token immediately
3. Remove the secret from the working tree
4. If the secret was pushed, work with maintainers to remove it from git history using an approved history rewrite approach
5. Confirm the new secret is stored securely and that prevention controls are in place before continuing work

## Reporting a vulnerability

Please do not report security issues through public GitHub issues, discussions, or pull requests.

Preferred reporting method:
* Contact the repository maintainers at [respnet@doh.wa.gov](mailto:respnet@doh.wa.gov)
* Include a clear description of the issue, affected repository paths, steps to reproduce (if applicable), and potential impact

## References

Standards
* https://nw-page.github.io/standards/gh/security.html

Secret hooks
* https://github.com/DOH-EPI-Coders/secret-hooks

GitHub documentation
* https://docs.github.com/en/code-security/concepts/secret-security/about-push-protection
* https://docs.github.com/en/code-security/secret-scanning/about-secret-scanning
