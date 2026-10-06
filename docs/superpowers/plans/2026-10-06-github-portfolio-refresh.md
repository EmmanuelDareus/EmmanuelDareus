# GitHub Portfolio Refresh Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Refresh Emmanuel Dareus’s GitHub profile and all six repositories into an accurate, polished portfolio, correct only verified low-risk issues, and leave a genuine, prioritized contribution path.

**Architecture:** Make changes one repository at a time in isolated local clones under session storage; commit and push only reviewed files to each repository’s existing `main` branch. Keep the profile README repository as the canonical portfolio, keep repositories independent, and apply only focused README/metadata/config changes supported by repository evidence.

**Tech Stack:** GitHub profile and repository metadata, Markdown, Git, Python/Flask, Python/FastAPI, Next.js 16.3.8, React 19.2.8, TypeScript 5, Supabase.

## Global Constraints

- Preserve all repository names, visibility settings, and commit history. Do not delete or archive repositories.
- Do not rewrite public Git history or remove prior commits.
- Do not manufacture contribution activity or attempt to game achievements.
- Do not add private keys, passwords, service credentials, or other secrets to GitHub.
- Use truthful language about AI-assisted/vibe-coded work without claiming employment, credentials, production maturity, or technology use not verified in the repositories.
- Avoid broad application redesigns, feature work, framework/dependency migrations, unrelated refactors, and dependency upgrades.
- Before committing, verify only intended files are staged, preserve any existing user changes, and ensure no local settings, generated caches, credentials, or environment files were added.
- For a public hard-coded signing secret that may have been deployed, instruct the owner to rotate it and invalidate existing sessions; never expose replacement secret values.
- Stop and ask before changing deployed behavior, credentials/account security settings, project identity, or metadata in a way that could misrepresent a project.

---

## File Structure

Use a separate clone for each repository, stored beneath:

`C:\Users\gamin\.copilot\session-state\2b611c4c-d498-40ce-a029-10e59d80e74d\files\repos\<repository>`

Do not put these clones inside the ChurchGrow worktree.

Files expected to be reviewed or changed:

- `EmmanuelDareus/EmmanuelDareus/README.md` — canonical GitHub profile portfolio.
- `EmmanuelDareus/emanthesoftwareengineer0403-art/README.md` — approved legacy signpost.
- `EmmanuelDareus/ChurchGrow/README.md` — existing setup, features, and deployment guide; edit only if the audit finds a concrete inaccuracy.
- `EmmanuelDareus/dd-recovery-os/README.md` — empty/incomplete project documentation to replace with verified setup and test instructions.
- `EmmanuelDareus/OmniLogiq/README.md` — new focused project guide; the root currently has no README.
- `EmmanuelDareus/School_OS/README.md` — mark this Flask project clearly as the V1 predecessor to OmniLogiq.
- `EmmanuelDareus/School_OS/app.py` — public hard-coded Flask session secret; change only after the deployment-impact checkpoint in Task 6.
- Each repository’s `.gitignore`, workflow, dependency manifest, and other source/config files — inspect first; change only where tracked state proves a specific defect.
- GitHub profile/repository settings — update headline/bio, pins, descriptions, and limited topics through GitHub settings after content is verified.

## Task 1: Audit account and record profile baseline

**Files:**
- Review: `EmmanuelDareus/README.md`
- GitHub settings: account bio/profile fields and public pins

**Interfaces:**
- Consumes: the approved headline “AI-assisted software developer building websites and apps that solve real problems” and current public profile.
- Produces: a baseline of bio/profile fields, pins, open issues, and current README problems for use in Task 7.

- [ ] **Step 1: Capture the current profile and repository metadata**

Record the current profile bio, location, website/social links, pinned repositories, repository descriptions, visibility, and default branches. Do not change visibility or account contact/privacy settings.

Expected: a baseline list exists so changes can be compared and nothing is silently removed.

- [ ] **Step 2: Review the reported open profile-repository issue**

Open the profile repository’s Issues tab directly and inspect every open issue’s title/body. Do not close or edit it as part of profile cleanup.

Expected: issue intent is understood; if the listing still reports an issue but no issue can be found, record the mismatch and do not alter it.

- [ ] **Step 3: Record current bio, links, pins, and project descriptions**

Record the current wording and pin order without editing it. Note that the profile README repository is also the profile’s special README source and is public.

Expected: Task 7 can update only the approved presentation details after the repository audits produce verified summaries.

## Task 2: Refresh ChurchGrow presentation without disturbing the live app

**Files:**
- Review: `ChurchGrow/README.md`, `package.json`, `.gitignore`, `src/app/*`, and `.env.example`
- GitHub settings: ChurchGrow description/topics

**Interfaces:**
- Consumes: live URL `https://church-grow.vercel.app`, existing `main` branch, and the current product documentation.
- Produces: accurate README metadata and, only if needed, focused documentation/metadata edits.

- [ ] **Step 1: Clone and confirm repository state**

Clone `https://github.com/EmmanuelDareus/ChurchGrow.git` into the session `files\repos\ChurchGrow` directory. Run `git status --short --branch`, inspect recent commits, and ensure `.env.local` is absent from tracked and staged files. Never print environment file values.

Expected: clean `main` clone; the Vercel-connected repository is not changed by local profile work.

- [ ] **Step 2: Compare README claims to actual app surface**

Compare documented routes/features with `src/app`, migrations with `supabase/migrations`, and useful commands with `package.json` scripts (`lint`, `test`, `build`). Check live demo URL.

Expected: identify only provable mismatches; do not rewrite the working setup guide or add credentials.

- [ ] **Step 3: Update GitHub description and topics**

Set the description to: `Church social-media planning, weekly goals, and performance tracking.` Add only relevant topics verified by the stack and app, such as `nextjs`, `react`, `typescript`, `supabase`, and `church`.

Expected: repository description is concise and matches the live app; source repository remains private.

- [ ] **Step 4: If and only if a README defect was found, make a narrow documentation correction**

Edit only the affected README statements. Run the documented checks:

```powershell
npm.cmd run lint
npm.cmd test
npm.cmd run build
```

Expected: all checks pass and no Vercel/Supabase production settings or app runtime behavior changed.

- [ ] **Step 5: Commit and push any README correction independently**

Stage only `README.md`, review `git diff --cached --check` and `git diff --cached`, then commit as `docs: align ChurchGrow project guide` and push `main`. If no README correction is needed, make no file commit.

Expected: focused documentation commit or explicitly no code change required.

## Task 3: Document and de-noise dd-recovery-os

**Files:**
- Modify: `dd-recovery-os/README.md`
- Review: `.github/workflows/pytest.yml`, `requirements.txt`, `tests/`, `.gitignore`, tracked `__pycache__/` and `logs/` contents
- GitHub settings: description/topics

**Interfaces:**
- Consumes: verified FastAPI source layout, requirements, CI workflow, test suite, and current branch.
- Produces: project-specific README, correct CI links, and verified ignore/metadata corrections if needed.

- [ ] **Step 1: Clone and inventory tracked files**

Clone `https://github.com/EmmanuelDareus/dd-recovery-os.git` into session storage. Review its root tree, tracked files under `__pycache__` and `logs`, `.gitignore`, dependency manifest, workflow, tests, and actual FastAPI entry point. Record the actual Python support range from project metadata rather than the existing badge.

Expected: know which files are generated, runtime data, source, and tests; do not delete persistent runtime logs or data without proof they are disposable.

- [ ] **Step 2: Confirm CI and package facts**

Read `.github/workflows/pytest.yml`, `requirements.txt`, and test files. Run the repo’s current documented/test command in a clean local environment only if its dependency installation is safe; do not upgrade dependencies as part of this task.

Expected: exact test command, supported Python versions, app entry point, license status, and CI badge URL are established.

- [ ] **Step 3: Replace the empty/incomplete README**

Write `README.md` with: concise project purpose; actual status/limitations; verified Python/FastAPI architecture; prerequisites; exact setup and run commands supported by its manifest; exact test command; actual CI badge URL; configuration/log behavior; and license only if a license file actually exists. Remove personal bio and “scalable/robust” claims not supported by source.

Expected: a new reader can install, run, and test the project without invented features or requirements.

- [ ] **Step 4: Correct ignore rules only for files confirmed as generated**

If tracked Python bytecode is confirmed, add standard Python cache/bytecode patterns to `.gitignore`, remove only the enumerated generated cache paths from the Git index, and keep source and needed runtime data. Do not recursively remove directories from disk.

Expected: `git ls-files` no longer lists confirmed bytecode/cache artifacts; intended log/data files remain untouched unless separately approved.

- [ ] **Step 5: Verify and commit dd-recovery-os**

Run the verified test command and any existing workflow-equivalent check. Stage only the README and any verified ignore/index changes; inspect staged paths; run `git diff --cached --check`; commit `docs: document dd-recovery-os setup` (or a separate `chore: ignore tracked Python caches` if needed); push `main`.

Expected: tests pass or their pre-existing failure is recorded, links work, and commits contain only intended project files.

## Task 4: Present OmniLogiq as the current school portal

**Files:**
- Create: `OmniLogiq/README.md`
- Review: `requirements.txt`, `app.py`, `compliance.py`, `templates/`, `static/`, `.gitignore`, tracked `__pycache__/`, and deploy files
- GitHub settings: description/topics

**Interfaces:**
- Consumes: source-verified Flask features and the owner’s statement that this is the improved successor to School_OS V1.
- Produces: current-version project documentation and aligned metadata; no app behavior changes unless separately approved.

- [ ] **Step 1: Clone and inspect OmniLogiq**

Clone `https://github.com/EmmanuelDareus/OmniLogiq.git`. Confirm default branch and status. Inspect routes/templates, dependencies, deployment files, ignore rules, and tracked cache files. Do not assume feature claims from the repository description alone.

Expected: verified use cases, actual Flask run command, deployment configuration, any test commands, Python version evidence, and cache status are recorded.

- [ ] **Step 2: Create an accurate README**

Create `README.md` containing: concise purpose, relation to School_OS V1, verified capabilities, stack, setup/run steps using exact manifest/startup requirements, configuration/data persistence limitations, tests (or explicitly “no automated test suite currently present”), and deployment status only if confirmed from an actual deployment.

Expected: the project is clearly “current/improved iteration,” not falsely described as AI-powered or production-ready without code evidence.

- [ ] **Step 3: Correct only verified cache/metadata issues**

If `__pycache__` is tracked, add Python cache ignores and untrack only enumerated generated cache paths. Set the GitHub description to: `Flask school-operations portal for district administration workflows.` Add relevant verified topics, such as `flask`, `python`, `education`, and `school-management`.

Expected: no tracked cache remains if found; metadata matches inspected source.

- [ ] **Step 4: Validate and commit OmniLogiq**

Run existing tests if present. If no tests exist, run Python syntax validation on app modules using the project’s declared runtime, and verify the documented startup command from the manifest. Stage only the README/ignore corrections, inspect staged diff, run `git diff --cached --check`, commit `docs: document OmniLogiq portal`, and push `main`.

Expected: README instructions match executable project behavior and the commit is limited to docs/confirmed cleanup.

## Task 5: Mark School_OS as V1 and audit its public configuration

**Files:**
- Modify: `School_OS/README.md`
- Review and conditionally modify: `School_OS/app.py`, `.gitignore`, `requirements.txt`, `procfile`, tracked generated/config files
- GitHub settings: description/topics

**Interfaces:**
- Consumes: owner’s confirmation that School_OS is V1, Flask source, and deployment configuration.
- Produces: clear V1 documentation and a safe session-signing configuration, only after deployment impact is understood.

- [ ] **Step 1: Clone and inspect before changing the deployed behavior**

Clone `https://github.com/EmmanuelDareus/School_OS.git`. Review `app.py`, README, requirements, Procfile casing/content, `.gitignore`, all tracked JSON/config files, and any deployment URL referenced in repository settings or documentation. Specifically trace whether `app.secret_key = 'school_os_secret_key'` signs Flask sessions and whether the app is deployed.

Expected: determine if the hard-coded key is active in a deployment, whether existing user sessions/data could be affected, and the exact startup command.

- [ ] **Step 2: Pause for owner confirmation if a deployment may be active**

If source or repository evidence indicates an active deployment, ask the owner to confirm the host and willingness to update its secret environment variable and accept session invalidation before changing `app.py`. If no deployment exists, document that finding and proceed with environment-based configuration. Do not expose any replacement key.

Expected: no production behavior changes without an explicit deployment-impact decision.

- [ ] **Step 3: Replace the hard-coded signing key**

Use an environment variable and fail clearly when it is missing:

```python
import os

secret_key = os.environ.get("FLASK_SECRET_KEY")
if not secret_key:
    raise RuntimeError("Set FLASK_SECRET_KEY before starting School_OS.")

app.secret_key = secret_key
```

Keep imports in standard-library order before third-party imports. Add `.env.example` containing a variable name and a non-secret placeholder only if the project already uses/ documents `.env` configuration; never add a real value. Document generating a secure key locally, setting it in the deployment provider’s secret settings, and restarting the service.

Expected: no default secret remains in current source; startup without the variable fails with a clear message; configured test secret is used for sessions.

- [ ] **Step 4: Add a focused test for required configuration**

If no test infrastructure exists, create `tests/test_secret_config.py` using Python’s standard `unittest` and subprocess:

```python
import os
import subprocess
import sys
import unittest
from pathlib import Path

ROOT = Path(__file__).resolve().parents[1]


class SecretConfigurationTests(unittest.TestCase):
    def run_import(self, secret):
        env = os.environ.copy()
        env.pop("FLASK_SECRET_KEY", None)
        if secret is not None:
            env["FLASK_SECRET_KEY"] = secret
        return subprocess.run(
            [sys.executable, "-c", "import app"],
            cwd=ROOT,
            env=env,
            capture_output=True,
            text=True,
        )

    def test_missing_secret_fails_clearly(self):
        result = self.run_import(None)
        self.assertNotEqual(result.returncode, 0)
        self.assertIn("Set FLASK_SECRET_KEY", result.stderr)

    def test_configured_secret_allows_app_import(self):
        result = self.run_import("test-only-not-a-production-secret")
        self.assertEqual(result.returncode, 0, result.stderr)


if __name__ == "__main__":
    unittest.main()
```

Run from repository root with `python -m unittest discover -s tests -v` using the selected project interpreter and installed declared dependencies.

Expected: missing-secret test fails with the explicit message; configured-secret import passes. If importing the application has unrelated required external side effects, adapt the test only after documenting the observed cause.

- [ ] **Step 5: Rewrite School_OS README as a V1**

Document it as the earlier Flask school-portal iteration, link to OmniLogiq as the current project, accurately describe only verified routes/workflows, use exact run and dependency commands, explain `FLASK_SECRET_KEY` setup, and state current tests/deployment limitations.

Expected: old “secure”/production claims are qualified unless verified; relationship to OmniLogiq is clear.

- [ ] **Step 6: Verify and commit School_OS safely**

Run the configuration tests, syntax check, and any existing test suite. Inspect staged file paths and diff, verify the new key itself is not staged, then commit the security/config change separately from README/metadata and push only after deployment steps in Step 2 are approved and completed.

Expected: current source has no hard-coded secret; if deployed, the owner has rotated the deployed secret and invalidated old sessions; repo history is unchanged.

## Task 6: Turn the old README repository into a signpost

**Files:**
- Modify: `emanthesoftwareengineer0403-art/README.md`
- GitHub settings: description/topics only if the repository has an owner-confirmed ongoing purpose

**Interfaces:**
- Consumes: owner approval to retain this repository publicly as a legacy placeholder.
- Produces: concise legacy signpost pointing to the canonical profile and active project repositories.

- [ ] **Step 1: Clone and confirm repository contents**

Clone `https://github.com/EmmanuelDareus/emanthesoftwareengineer0403-art.git`. Confirm it contains only the duplicate README or inspect any other files before editing.

Expected: no application code or separate project purpose is displaced.

- [ ] **Step 2: Replace duplicate content with a signpost**

Replace the README with a short note that this is an older profile README, link to `https://github.com/EmmanuelDareus`, and point to current projects `ChurchGrow`, `OmniLogiq`, and `dd-recovery-os`. Do not claim the old repository is the source for any of those projects.

Expected: visitor can find the canonical profile and active work immediately.

- [ ] **Step 3: Commit and push only the README**

Run Markdown link checks by opening every link; stage only `README.md`; run `git diff --cached --check`; commit `docs: mark repository as legacy profile`; push `main`.

Expected: repository remains public and its history is preserved.

## Task 7: Finalize public profile metadata, pins, and real contribution roadmap

**Files:**
- Modify: `EmmanuelDareus/README.md`
- GitHub account profile fields and pins
- No additional repository source files unless a verified meaningful follow-up task is approved by the owner.

**Interfaces:**
- Consumes: completed verified READMEs and project metadata from Tasks 1–6.
- Produces: consistent account profile, relevant public pins, and a concrete list of authentic contribution opportunities.

- [ ] **Step 1: Update account bio**

Set the GitHub bio to: `AI-assisted software developer building websites and apps that solve real problems.` Keep existing location and contact details unchanged unless the owner explicitly requests otherwise.

Expected: bio matches the headline chosen during design and avoids implying unverified employment or credentials.

- [ ] **Step 2: Rewrite the profile README using the completed audits**

Use a concise standalone layout: a short greeting and the approved headline; a sentence that accurately describes AI as part of the development workflow; featured project links to ChurchGrow (including its live demo), OmniLogiq, dd-recovery-os, and School_OS V1; then a short tools list derived only from active manifests/source. Remove the old “software and AI engineer” statement, outdated mission/personal sections, and the embedded dd-recovery-os badge/architecture/readme copy. Do not add badges unless their repository workflow and URL were verified in Tasks 2–5.

Expected: the profile is distinct from project documentation and every claim/link is verified.

- [ ] **Step 3: Render and validate the profile README**

Review the rendered profile page. Open each project and live-demo link, confirm badges point to the correct owner/repository/workflow, and verify the page no longer contains duplicate dd-recovery-os project content or outdated owner paths.

Expected: all links work and the standalone portfolio renders cleanly.

- [ ] **Step 4: Commit and push only the profile README**

```powershell
git status --short
git add -- README.md
git diff --cached --check
git diff --cached --stat
git commit -m "docs: refresh GitHub portfolio profile"
git push origin main
```

Expected: only `README.md` is committed and pushed to the profile repository.

- [ ] **Step 5: Update public repository pins**

Pin only current public work with accurate READMEs, preferring `OmniLogiq` and `dd-recovery-os` plus the profile README repository if the UI permits and those projects pass the audit. Do not pin School_OS as the current product; include it only if the V1 story is useful. ChurchGrow is private: link its public demo from the README but do not change repository visibility.

Expected: pins represent current work accurately and do not expose the private source.

- [ ] **Step 6: Produce a prioritized authentic contribution list**

From verified audit findings, write a short ordered checklist in the final report: each item must name a real file/behavior, a specific improvement, and a feasible validation command. Prefer tests/docs/cache cleanup/config fixes. Do not create empty commits, fake daily work, or claim that a task awards a badge.

Expected: the owner has small tasks that improve real projects and can naturally create contribution activity when actually completed.

- [ ] **Step 7: Explain contribution squares and achievements**

Check GitHub’s official current contribution/achievement documentation. Explain the account/email/default-branch and contribution-type rules relevant to this account; list current achievements only if verified in the profile. Describe qualifying achievements as possibilities, never guarantees. Do not toggle unrelated settings or make activity changes to simulate squares.

Expected: owner understands why genuine work may or may not appear and that achievements are controlled by GitHub.

- [ ] **Step 8: Final cross-repository consistency check**

Open the rendered profile, all six repository pages, updated READMEs, project links, badges, and metadata. Run checks listed per task; verify GitHub Actions status where a workflow exists. Review repository visibility and pinned list to confirm no accidental changes.

Expected: portfolio is coherent, links resolve, repo names/visibility/history remain unchanged, tests are honestly reported, and all edits correspond to an approved task.

## Completion report

Report the profile URL, repositories updated, commits/links, checks actually run, any user action still needed (especially deployed School_OS secret rotation), the verified contribution backlog, and the fact that no achievement or daily-square count is guaranteed.
