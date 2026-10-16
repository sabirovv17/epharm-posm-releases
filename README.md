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

## Pilot candidate (not the fleet current release)

- Version: `1.0.69`, `win-x64`.
- File: `downloads/epharm-posm-1.0.69-00acf498e9a5-compat.zip`.
- SHA-256: `48a4b4726cea6beff5b6a4d98279c50c068704c096d71177d5440322c82d5db7`.
- Source commit: `00acf498e9a53e8c32c79f9d1c7d951814e243c4`.
- Windows CI provenance: `downloads/epharm-posm-1.0.69-00acf498e9a5-provenance.json`.

Adds optional employee IIN/password sign-in, pending SMS registration, activation and
phone-bound password recovery without blocking Standard-N or Windows. Keep the installed
pharmacy configuration and full runtime. This five-file archive is an update, not a fresh installer.
Actual Standard-N session field types, heartbeat cadence, window/scanner behavior and real
SMS delivery require a controlled Windows pilot before promoting this version to the fleet.
Current remains 1.0.68 until that acceptance is recorded.
