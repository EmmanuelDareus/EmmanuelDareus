# GitHub Portfolio Refresh Design

## Goal

Present Emmanuel Dareus’s GitHub account as a polished, accurate portfolio of AI-assisted software development and practical problem-solving projects, while improving repository clarity and creating a sustainable path for genuine contributions.

## Current context

- The account has six repositories: private `ChurchGrow` and five public repositories: `EmmanuelDareus` (the profile README), `dd-recovery-os`, `emanthesoftwareengineer0403-art`, `OmniLogiq`, and `School_OS`.
- The owner describes himself as a vibe coder and AI software developer who designs and builds websites, apps, and web apps to solve problems.
- The selected public headline is: “AI-assisted software developer building websites and apps that solve real problems.”
- The owner clarified that `OmniLogiq` is the improved/newer school portal and `School_OS` is its V1; both must remain.
- The `emanthesoftwareengineer0403-art` repository has no application source in its root and its README duplicates old `dd-recovery-os`/profile content. The owner approved keeping it public and replacing that duplicate content with a legacy signpost.
- The profile README currently mixes a personal introduction with an old project README, describes the owner as an engineer, and says OmniLogiq is AI-powered; these claims and duplicated sections need to be checked and aligned with verified project facts.
- Current repository listing suggests generated Python cache directories are tracked in `dd-recovery-os` and `OmniLogiq`; verify before changing ignore rules.
- `School_OS` source contains a hard-coded Flask session key (`school_os_secret_key`). Because its repository is public, assess the exact use and replace it with environment-backed configuration if the audit confirms it is the application signing secret. Do not rewrite public Git history. If that value was used by a deployed instance, instruct the owner to rotate it and invalidate existing sessions.
- Repository metadata reports an open issue in the profile repository; verify it directly and inspect its purpose before changing or closing it.
- GitHub currently shows the YOLO and Quickdraw achievements. Achievements and contribution-calendar activity must be earned through genuine qualifying platform activity; this work will not fabricate commits or promise badges.

## Approaches considered

1. **Thorough, conservative portfolio refresh (selected).** Improve profile and repo presentation, inspect all six repos for specific alignment/config problems, make only verified low-risk fixes, and propose useful small follow-up work. Preserve repo names, history, visibility, and application scope.
2. **Presentation-only refresh.** Polish the profile and READMEs without auditing or fixing code/config issues.
3. **Broad project rebuilds.** Restructure or substantially rewrite repositories that look rough. This has greater risk and is not needed to make the portfolio clearer.

## Design

### Profile and portfolio presentation

- Replace the duplicated profile README with a concise, standalone portfolio based on the approved headline.
- Use truthful language about AI-assisted/vibe-coded work without claiming employment, credentials, production maturity, or technology use not verified in the repositories.
- Feature current projects and link to the live ChurchGrow demo where appropriate; accurately distinguish the private source repository from its public deployed app.
- Keep `School_OS` as a clearly labeled V1 and `OmniLogiq` as the improved/current iteration.
- Replace the README in `emanthesoftwareengineer0403-art` with a short legacy notice pointing to the current profile and active projects. Keep the repository public and preserve its history.
- Select public profile pins based on current relevance and project completeness; do not pin the V1 over its successor unless needed to tell the version story.
- Update repository descriptions and a small, relevant set of topics only when the project purpose is verified.

### Repository-by-repository audit and cleanup

- Inspect tracked files, README claims, language/stack declarations, workflows, dependency manifests, ignore rules, deployment instructions, and obvious credential/config hazards in each repository.
- Add or revise a focused README for each project that explains its verified purpose, current status, stack, setup, run/test steps, configuration, and limitations. Do not invent screenshots, tests, hosted URLs, features, or badges.
- For ChurchGrow, retain its existing project guide and avoid copying private deployment secrets. Check its README claims against its actual routes and package scripts.
- For `dd-recovery-os`, replace the empty or incomplete project README with verified setup and testing guidance. Resolve its duplicated embedded personal content rather than carrying profile text into a project README.
- For `OmniLogiq` and `School_OS`, document their relationship clearly while keeping the codebases independent.
- For `emanthesoftwareengineer0403-art`, make only the approved legacy-signpost change unless inspection uncovers a concrete, owner-approved purpose for further work.
- Fix tracked generated artifacts, incorrect badges/links, inaccurate version/runtime requirements, and verified low-risk configuration problems. Avoid unrelated refactors and dependency upgrades.
- Treat a public hard-coded signing secret as compromised if it has ever been used outside a local demo. Replace source-code defaults with environment configuration, document secure generation/configuration, and instruct the owner to rotate any deployed secret; never expose replacement secret values.
- Preserve all repository names, visibility settings, and commit history. Do not delete or archive repositories.

### Genuine contributions and achievements

- Use concrete findings from the audit to create a short, prioritized set of meaningful follow-up tasks, such as correcting docs, adding a test for a verified behavior, fixing an ignored-file issue, or documenting deployment.
- Prefer normal, reviewed, testable changes in each repository. Do not create empty commits, automate meaningless daily changes, manipulate timestamps, or claim achievement eligibility without checking GitHub’s current rules.
- Explain that green contribution squares depend on GitHub’s contribution rules and account/email/default-branch setup, while profile achievements are awarded by GitHub for qualifying actions. Neither is directly configurable or guaranteed by this refresh.

## Workflow, boundaries, and verification

- Work one repository at a time, reviewing its current main-branch state before editing.
- Keep changes small and independently reviewable; do not stage or commit one repository’s changes as another repository’s changes.
- Before committing, verify only intended files are staged, preserve any existing user changes, and ensure no local settings, generated caches, credentials, or environment files were added.
- Run each repo’s existing documented lint/test/build checks where available. For projects without checks, verify commands from source/manifests and document the limitation rather than inventing a passing test result.
- Validate README links and badges against actual repository paths, workflows, and deployments.
- After profile changes, inspect the rendered profile and pin list. For any credential/config correction, explain rotation or deployment steps still requiring the owner.
- Surface unknowns and unsafe findings explicitly; pause for owner decisions before changing project identity, deployed behavior, account security settings, or repository metadata in a way that could misrepresent a project.

## Out of scope

- Renaming, deleting, archiving, or changing visibility of repositories.
- Rewriting repository history or removing prior commits.
- Broad application redesigns, feature work, or framework/dependency migrations.
- Manufacturing contribution activity or attempting to game achievements.
- Adding private keys, passwords, service credentials, or other secrets to GitHub.
- Claiming unverified professional qualifications, work history, project capabilities, or production status.

## Acceptance criteria

- The profile README is a concise and accurate standalone portfolio using the approved headline.
- Current projects are presented with verified descriptions; `OmniLogiq` is identified as the improved iteration and `School_OS` as V1.
- The old duplicate README repository remains public and has a clear legacy signpost to current work.
- Each of the six repositories has been inspected for presentation and concrete code/config mismatches; any claimed fixes are backed by repo-specific verification.
- READMEs, badges, links, and metadata do not claim unsupported features, test coverage, versions, or deployments.
- Any public signing-secret problem that is confirmed is removed from current source and accompanied by explicit owner rotation guidance if it may have been deployed; public history remains intact.
- No empty or artificial contributions are made, and achievement/contribution expectations are accurately explained.
- No repository is renamed, deleted, archived, or made public/private by this work.
