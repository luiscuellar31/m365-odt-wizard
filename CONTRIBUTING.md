# Contributing to m365-odt-wizard

Thanks for contributing. This guide is intentionally short and practical.

---

## Branch Structure

- `main`: stable releases only (maintainer-managed).
- `dev`: active integration branch.
- All PRs must target `dev`.

Use tags/releases for fixed snapshots:

- Latest tagged builds: https://github.com/luiscuellar31/m365-odt-wizard/releases

---

## How to Contribute

After your first fork/clone, your branch can drift quickly from `upstream/dev`.
To avoid conflicts and broken PRs, sync before starting any new change.

1. Fork the repository to your own GitHub account.
2. Clone your fork locally:

```bash
git clone https://github.com/<your-username>/m365-odt-wizard.git
cd m365-odt-wizard
```

3. Add `upstream` once:

```bash
git remote add upstream https://github.com/luiscuellar31/m365-odt-wizard.git
```

4. Before each new modification, sync `dev`:

```bash
git checkout dev
git fetch upstream
git rebase upstream/dev
git push origin dev
```

Why: if you do not sync regularly, your feature branch may diverge from `dev`, causing avoidable conflicts and delayed reviews.

5. Create your feature branch from updated `dev`:

```bash
git checkout dev
git checkout -b feature/your-feature-name
```

6. Make your changes and commit using Conventional Commits:

```bash
git add .
git commit -m "feat: add app selection step UI"
```

7. Push your branch:

```bash
git push origin feature/your-feature-name
```

8. Open a Pull Request (PR):

- Base: `dev`
- Compare: `feature/your-feature-name`

---

## Code Style and Standards

- Follow Conventional Commits for commit messages.
- Keep code clean, consistent, and well-commented.
- Prefer descriptive variable and function names.
- Use English for code, comments, docs, and PR descriptions.

---

## Pull Request Guidelines

- Make sure your PR targets `dev`, not `main`.
- Keep PRs focused (one feature/fix per PR).
- Include a clear description of what changed and why.
- Link related issues when applicable (e.g., `Closes #42`).

---

## Local Validation (Required)

```bash
dotnet restore m365-odt-wizard.sln
dotnet build m365-odt-wizard.sln --no-restore
```

If tests exist in the solution, also run:

```bash
dotnet test m365-odt-wizard.sln --no-build
```

If your change is platform-specific, validate on that platform too.

### Windows-Specific Validation Notes

- WPF UI (`ui/`) targets `net8.0-windows`.
- Build can be done on macOS/Linux, but runtime validation must be done on Windows.
- For ODT/Registry changes, validate on Windows before opening the PR.

---

## Project Structure (Current)

- `ui/`: WPF UI project (`M365OdtWizard.App`)
- `core/`: business/domain logic (`M365OdtWizard.Core`)
- `m365-odt-wizard.sln`: solution

Guideline: keep logic in `core/`; keep `ui/` focused on presentation.

---

## Security and Scope Boundaries

This project does **not** accept:

- Activation bypasses (KMS/cracks/keygens/bypasses)
- Redistribution of Microsoft 365 Apps binaries

---

## Licensing

By contributing, you agree your changes are licensed under this repository license (see `LICENSE`).
