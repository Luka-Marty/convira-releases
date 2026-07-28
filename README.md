# Convira

**The AI agent that works on the files already on your computer.**

Convira is a desktop AI agent for macOS, Windows and Linux that works on the real
Word, Excel, PowerPoint and PDF files already on your machine. You can watch every
step, approve sensitive actions before they happen, and choose where the AI runs:
fully on your own device, on a private box you control, or in the cloud.

[convira.ai](https://www.convira.ai)

---

## What this repository is

This repository hosts the **published installers and the auto-update feed** for the
Convira desktop app. It is the only place official builds are distributed from, and
it is what the in-app updater checks.

Convira's source code is not public. Issues opened here about the source will not
have anywhere to go - see [Support](#support) below for where things should be sent
instead.

## Status

Convira has not had its first public release yet. When it does, the installers will
appear on the [Releases](../../releases) page and on
[convira.ai/download](https://www.convira.ai/download).

## Download

Installers for every supported platform are attached to each release:

- **macOS** - `.dmg`
- **Windows** - `.exe`
- **Linux** - `.AppImage` and `.deb`

Get the newest build from [Releases](../../releases/latest), or from
[convira.ai/download](https://www.convira.ai/download).

## System requirements

| Platform | Requirement |
| --- | --- |
| macOS | 12 or later, Apple silicon only |
| Windows | 10 or 11, x64 |
| Linux | x86_64 |

## Verifying a download

Convira runs on your own machine and touches your own files, so it should be easy
to confirm that what you downloaded is what was built. Every release carries:

- **`SHA256SUMS`** - deterministic checksums for every payload in the release.
- **Code signatures** - macOS builds are signed and notarized by Apple with a
  stapled ticket; Windows builds are Authenticode signed.
- **A CycloneDX 1.5 SBOM** per platform, listing what went into the build.
- **A signed SLSA v1 provenance statement** recording which workflow run produced
  the artifacts.
- **Sigstore bundles** for every payload, for `SHA256SUMS`, and for the provenance
  statement, each issued to the release workflow's own identity.

To check a download against the published checksums:

```sh
# macOS / Linux
shasum -a 256 -c SHA256SUMS --ignore-missing

# Windows (PowerShell)
Get-FileHash .\Convira-Setup.exe -Algorithm SHA256
```

Releases are published as drafts first and only made public after their checksums
are verified, so a draft's assets are never reachable by the updater.

## Automatic updates

The app checks this repository for new stable releases and updates itself. Releases
roll out in stages rather than to everyone at once. You can turn automatic updates
off in the app under Settings.

Downgrading in-app is deliberately not supported. If a release regresses, the fix
ships as a higher version.

## Support

- **Questions and help** - [convira.ai/help](https://www.convira.ai/help) or
  <support@convira.ai>
- **Sales and licensing** - <sales@convira.ai>
- **Security vulnerabilities** - <security@convira.ai>. Please report privately and
  give us a chance to ship a fix before disclosing.

## Links

- Website - [convira.ai](https://www.convira.ai)
- How it works - [convira.ai/architecture](https://www.convira.ai/architecture)
- Security model - [convira.ai/security](https://www.convira.ai/security)
- Pricing - [convira.ai/pricing](https://www.convira.ai/pricing)
- Changelog - [convira.ai/changelog](https://www.convira.ai/changelog)

---

Convira OÜ, Tallinn, Estonia. Registry code 17268095.
