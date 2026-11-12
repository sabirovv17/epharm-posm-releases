# ePharm POSM Windows updates

Public distribution repository for versioned Windows update artifacts.
Application source, pharmacy configuration and credentials are not stored here.

## Latest update artifact

- Version: `1.0.85`; platform: `win-x64`.
- Archive: `downloads/epharm-posm-1.0.85-addb2c97bf75-compat.zip`.
- SHA-256: `dc41228626e0a0cc7970d0aee070605ec244a1ee639ae42932ee177e189f6d38`.
- Source commit: `addb2c97bf752038688e91a6902369da5194009b`.
- Provenance: `downloads/epharm-posm-1.0.85-addb2c97bf75-provenance.json`.
- [Required Windows/main CI](https://github.com/sabirovv17/epharm/actions/runs/43153930079).

This five-file bridge updates an existing full POSM runtime; it is not a fresh-install
package. It preserves `posm.json`, device identity, pharmacy settings and the local queue.
Existing versioned artifacts are retained for recovery.

## Integrity and activation

POSM verifies the independently signed ECDSA manifest and the exact archive SHA-256.
Production distribution URLs are pinned to a full artifact commit. The signed backend
manifest determines the active release; availability of an artifact here does not prove
that a device has installed it.

Version 1.0.82 adds bounded downloads, journaled application, dispatcher readiness ACK and
verified rollback. The first handover from an older installed updater still uses that old
updater. Release acceptance and device-version telemetry remain separate from file delivery.

Version 1.0.84 adds bounded, fail-closed staff-session recovery and fresh cashier-process
confirmation. The application source and existing update trust anchor remain in the main
epharm repository. Only a signed backend manifest activates this immutable artifact.

Version 1.0.85 makes automatic staff sign-in nonblocking for the cashier, keeps
late login responses from restoring a closed window, and preserves the existing
update/recovery, pharmacy configuration and queue protections.
