# Status

Historical repo, `legacy` profile. Last commit 2013-12-23. Checked 2026-11-20 (audit pass 02, docs only; no code was changed).

## Works
- Nothing is confirmed to work today. The file parses and loads once `ripple-lib` is installed.

## Broken or likely broken
- **Ripple API changed.** It uses the early `ripple-lib` `Remote` object (`from_config`, `request_account_lines`, `ripple_line_set`). Current `ripple-lib` / `xrpl.js` have no `Remote`. **(inference)** it would need a rewrite, not a bump.
- **No `package.json`.** `ripple-lib` is never declared or version-pinned, so `require('ripple-lib')` fails on a fresh clone (confirmed: module not found).
- **`TrustLine.getAccountTrustLines`** is a static method that reads `this._remote`, which is only set by `TrustLine.setRemote`. It likely fails unless that is called first. **(inference)**
- **Options not honoured.** `noRipple` in the old README example is ignored; `allowRippling` is computed but its `setFlags` use is commented out.
- **Server.** `s1.ripple.com` is a public server that may or may not accept this old client; untested.

## Unknown
- Whether the trust-line transaction still succeeds against any live ledger.

## Needs a look in later passes
- `submit` prints `remote._secret` to the console, and `set_secret(null, null)` probably does not clear the account's secret **(inference)**. This belongs to the security pass; see the hub's security findings. Do not run it with a real key.

## Next (only if revived)
- Choose a real profile (`ts`), rewrite on `xrpl.js`, add tests, then CI.

## Not yet from the repo standard
LICENSE, SECURITY.md, CHANGELOG.md, CONTRIBUTING.md, ARCHITECTURE.md, `.github/`, tests, CI, API docs, and the CloudEvents catalogue (waits for revival).
