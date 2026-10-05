# TrackeyAI Releases

This repository holds **release artifacts only** for TrackeyAI (Morcrane Studios LLC). It contains no source code.

Each release carries:

| Asset | Purpose |
|---|---|
| `TrackeyAI-Setup-v<version>-win-x64-signed.exe` | Signed Windows installer |
| `TrackeyAI-Setup-v<version>-win-x64-signed.exe.sha256` | SHA-256 checksum of the installer |
| `trackeyai-windows-v<version>.json` | Machine-readable release manifest (version, channel, SHA-256, source commit, download URL) |
| `release-notes.md` | Release notes |

## Channels

- **Stable** releases are tagged `v<a.b.c.d>` and are the only releases the TrackeyAI website offers by default.
- **Release candidates** are tagged `v<a.b.c.d>-rc.<n>` and published as GitHub *pre-releases*. They are for validation, not general use.

## Verify a download

1. Compare the SHA-256: `Get-FileHash .\TrackeyAI-Setup-v<version>-win-x64-signed.exe -Algorithm SHA256` must equal the value in the `.sha256` file and in the manifest.
2. Check the signature: the installer's Authenticode signature must be valid and issued to **Morcrane Studios LLC**.

Windows SmartScreen may still warn about a newly published file until it builds download reputation; use *More info*, confirm the publisher, then *Run anyway* only if both checks above pass.

## How releases are published

Releases are created only by an approved, automated workflow in TrackeyAI's private source repository, after the source commit passed release verification and the signed installer passed checksum, signature and manifest checks. Nothing is uploaded by hand, and a published release is never overwritten.

Product information and support: https://trackeyai.com
