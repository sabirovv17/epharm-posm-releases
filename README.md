# ePharm POSM Windows updates

Public distribution repository for versioned Windows update artifacts.
Application source, pharmacy configuration and credentials are not stored here.

## Latest update artifact

- Version: `1.0.86`; platform: `win-x64`.
- Archive: `downloads/epharm-posm-1.0.86-20f059be078f-compat.zip`.
- SHA-256: `76b99ff648afaae60082fefc9d5fed6e4152bc3359733f986ed3a5a679d2f348`.
- Source commit: `20f059be078f11d26d187b28e1f68414927c02df`.
- Provenance: `downloads/epharm-posm-1.0.86-20f059be078f-provenance.json`.
- [Required Windows/main CI](https://github.com/sabirovv17/epharm/actions/runs/43588172996).

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

Version 1.0.86 retains the session for bounded, unverified recovery during brief unconfirmed
cashier-process observations, revokes it promptly on a confirmed cashier/account change, and keeps
registration and recovery nonblocking. Recommendation rules and all four trigger types
remain unchanged.
