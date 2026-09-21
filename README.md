# Epharm POSM releases

Public, artifact-only distribution channel for Epharm POSM Windows updates.
The application source code and pharmacy configuration are not stored here.

## Current release

- Version: `1.0.58`
- Platform: `win-x64`
- File: `downloads/epharm-posm-1.0.58-compat.zip`
- SHA-256: `75313b6711273f005f938abe52de9f387bbea5cdd5f129556621bc6544dbb036`
- Source commit: `03af9eeac6796dc6a0500225a7213c54098d1926`

POSM verifies the SHA-256 checksum before applying an update. The bridge ZIP
contains application binaries only and intentionally excludes `posm.json`,
device keys, pharmacy identifiers, source code, and deployment credentials.
