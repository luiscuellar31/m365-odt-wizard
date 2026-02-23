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
- `src/M365OdtWizard.App`: WPF UI scaffold (`net8.0-windows`) with a starter `MainWindow`.
- `src/M365OdtWizard.Core`: project scaffold with placeholder folders (`Models`, `Interfaces`, `UseCases`).
- `src/M365OdtWizard.Infrastructure`: project scaffold with placeholder folders (`Odt`, `OfficeDetection`, `Xml`, `Logging`, `Extensions`).
- `tests/`: test folder scaffold (`M365OdtWizard.Core.Tests`, `M365OdtWizard.Infrastructure.Tests`) reserved for future test projects.
