# m365-odt-wizard

A planned Windows GUI wizard for deploying Microsoft 365 Apps with the official Office Deployment Tool (ODT). Its goal is to simplify ODT workflows by generating a valid `configuration.xml` and running the right ODT commands from a clean interface.

## Planned scope
- **App selection (checkboxes):** pick which Microsoft 365 apps to install (Word, Excel, PowerPoint, etc.).
- **Generate `configuration.xml`:** create a valid ODT config from your selections.
- **Detect current install:** show what is already installed (edition, architecture, channel, languages) when possible.
- **Install / update:** run ODT in configure mode to install/update based on the generated config.
- **Trim existing installs:** exclude apps and re-run ODT to remove unwanted apps when supported.
- **Offline cache mode:** download installation files first (ODT `/download`), then install later (ODT `/configure`).
- **Logs:** show and export clear logs for troubleshooting.

## Non-goals
- No activation features (KMS, cracks, key generators, bypasses).
- No redistribution of Microsoft 365 Apps binaries.

## Base architecture (scaffolded)
- `ui/`: WPF UI project (`M365OdtWizard.App`) with starter `MainWindow`.
- `core/`: .NET class library project (`M365OdtWizard.Core`) for business/domain logic.
- `m365-odt-wizard.sln`: solution containing both `M365OdtWizard.App` and `M365OdtWizard.Core`.

As the app grows, add implementation in `core/` first and keep `ui/` focused on presentation.
