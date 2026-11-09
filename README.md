# ePharm POSM Windows updates

Public distribution repository for versioned Windows update artifacts.
Application source, pharmacy configuration and credentials are not stored here.

## Latest update artifact

- Version: `1.0.82`; platform: `win-x64`.
- Archive: `downloads/epharm-posm-1.0.82-fbb4545e32c9-compat.zip`.
- SHA-256: `cd825a2d00f86937c48212f830cd899ad37c91007628dc0d54d2f0df1ed712dc`.
- Source commit: `fbb4545e32c9d1c3030ca856c1c0f02e754ca4a0`.
- Provenance: `downloads/epharm-posm-1.0.82-fbb4545e32c9-provenance.json`.
- [Required Windows/main CI](https://github.com/sabirovv17/epharm/actions/runs/42642856425).

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
