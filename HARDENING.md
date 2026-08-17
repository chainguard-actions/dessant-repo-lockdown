<!-- markdownlint-disable -->

# Hardening Report: dessant--repo-lockdown/v5.0.1

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **dessant--repo-lockdown/v5.0.1** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

The workflow uses `softprops/action-gh-release@v3`, which is pinned to a mutable tag (`v3`) rather than an immutable 40-character commit SHA. A tag can be silently moved to point to a different (potentially malicious) commit, enabling a supply-chain attack. It should be replaced with a full SHA pin, e.g. `softprops/action-gh-release@<40-char-sha> # v3`.

Locations:

- `.github/workflows/release.yml:15`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned `softprops/action-gh-release@v3` to its full commit SHA `3d0d9888cb7fd7b750713d6e236d1fcb99157228` in `.github/workflows/release.yml` (line 15). The mutable tag `v3` is preserved as an inline comment for readability.

