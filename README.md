# Tiny11 ISO

Download a customized Windows 11 Pro x64 image created on October 24, 2026.

This repository documents a generated ISO. It does not contain the Tiny11 builder application's source code or a standalone build script.

## Download the ISO

[Download Tiny11 ISO from Google Drive](https://drive.google.com/file/d/1RQan2hQp8zaQBkQhhfsRoOxafUWz1-E2/view?usp=drivesdk)

The download is the complete `tiny11-20261024-204553.iso` file (5.32 GiB). Anyone with the link can view and download it. No ZIP extraction or file reassembly is required. Verify the SHA-256 below after downloading.

## Build details

| Setting | Recorded value |
| --- | --- |
| Windows edition | Windows 11 Pro, x64 |
| Version | 10.0.26300.9457 |
| Source image index | 6 |
| Mode / flavor | Tiny11 / Regular |
| Compression | Recovery |
| .NET Framework 3.5 | Enabled in the recipe |
| Compact installation | Enabled in the recipe |
| Turbo mode | Enabled |
| Output | `tiny11-20261024-204553.iso` |
| Output size | 5,710,086,144 bytes (approximately 5.32 GiB) |

## Local build records

The original local archive has a `tiny11-c56260c4430846f1bb4858fba72b3448/` folder containing the following records. They are not included in this repository:

- `recipe.json`: input paths, selected customization options, and build settings.
- `report.json`: image metadata, feature outcomes, output size, and recorded checksum.
- `operations.json`: individual operation results; inspect these before treating a selected option as successfully applied.
- `timings.json`: elapsed time for each build stage.
- `job.json`: build job identifier and completion status.
- `build.log` and `dism.log`: local diagnostic logs.

The recipe selects app removals and Windows customizations including Copilot, Teams, Xbox apps, Edge, OneDrive, widgets, privacy settings, hardware checks, reserved storage, and device encryption. A selection records intent; the operation results establish what happened.

## Validation status

The job reports completion, and the report lists no warnings. However, `BootValidated` is `false`: these records do not establish that the ISO boots, installs, or behaves correctly in a running system. Some cleanup operations were skipped because servicing operations were pending. Offline registry changes do not establish that Windows enforces the corresponding policies.

The build report records this SHA-256:

```text
1C993210431B2A67A7AD98DA36B7664528DE19198BEF4FD5380CECCD5446BE98
```

To compare a local copy against the recorded checksum in PowerShell:

```powershell
Get-FileHash -LiteralPath .\tiny11-20261024-204553.iso -Algorithm SHA256
```

## Rebuilding

Rebuilding requires the builder that produced this recipe, compatible source Windows media, DISM, and `oscdimg`. The recipe contains machine-specific paths; update them for your environment. The builder version and source are not recorded here, so this archive alone is insufficient for a reproducible rebuild.

## Repository contents

The repository holds documentation and checksums. The ISO is hosted on Google Drive and is not stored in Git history. Build records contain machine-specific paths and remain local unless separately reviewed for publication.
