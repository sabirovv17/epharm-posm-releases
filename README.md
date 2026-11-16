# ePharm POSM Windows updates

Public distribution repository for versioned Windows update artifacts.
Application source, pharmacy configuration and credentials are not stored here.

## Latest update artifact

- Version: `1.0.89`; platform: `win-x64`.
- Archive: `downloads/epharm-posm-1.0.89-b0afb4698a9d-compat.zip`.
- SHA-256: `ebaa179f7da9675d856ec0f63ef999c7e7352b72a43f98b51db093df42b14528`.
- Source commit: `b0afb4698a9d42ecb3488bd5d68f2dfb68de87dd`.
- Provenance: `downloads/epharm-posm-1.0.89-b0afb4698a9d-provenance.json`.
- [Required Windows/main CI](https://github.com/sabirovv17/epharm/actions/runs/43822856904).

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

Version 1.0.87 adds source-bound recommendation-sale evidence, verified package quantities,
native returns and safe archival of disappeared unpaid checkouts. A direct sale without a
shown recommendation cannot earn its bonus. Evidence admission and automatic wallet credit
remain controlled by the server; the package preserves staff login, client display, local
configuration, updater recovery and existing queues.

Version 1.0.88 preserves unsupported queued records, handles Standard-N checkout line reuse for another product, and removes obsolete SMS prompts from new staff registration. Existing runtime dependencies, settings, device identity, queues, recommendations and update recovery are preserved.

Version 1.0.89 separates automatic RPS presentation from grant/session invalidation. Confirmed Standard-N user changes prompt once; technical context changes retain an unfinished same-user form and credentials use a fresh context only on explicit submit. Expired and stale grants remain invalid. Cashier operation, existing settings, queues, recommendations and customer display are preserved.
