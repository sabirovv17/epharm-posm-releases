# Epharm POSM releases

Public, artifact-only distribution channel for Epharm POSM Windows updates.
The application source code and pharmacy configuration are not stored here.

## Current release

- Version: `1.0.68`
- Platform: `win-x64`
- File: `downloads/epharm-posm-1.0.68-b310bfe59fb1-compat.zip`
- SHA-256: `68e14c89d27d379694f81c8a555ff43f862819e17e30c28cb5c16fd5ce1d1190`
- Source commit: `b310bfe59fb1c2140dcc2c8624ac443d5ed752f6`
- Windows CI provenance: `downloads/epharm-posm-1.0.68-b310bfe59fb1-provenance.json`

This update adds an encrypted durable queue for actual QR-display acknowledgements,
independent retries, non-activating native topmost reinforcement and bounded per-task snooze.
The package is compatible with the installed full runtime; it is not a fresh-install package.

POSM verifies the pinned ECDSA manifest signature and SHA-256 before applying an update. The bridge ZIP
contains application binaries only and intentionally excludes `posm.json`,
device keys, pharmacy identifiers, source code, and deployment credentials.
