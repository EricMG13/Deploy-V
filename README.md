# Deploy V

Deploy V provides 25 physical skills for enterprise leveraged-finance credit analysis and governed publication.

## Deployment

Folder grounding via a saved Copilot memory prompt, not native Cowork install -- ground a conversation on this package's root folder (the one directly containing `skills/`, `CANON_SHARED.md`, and the retrieval index), then follow `DEPLOY_V_COPILOT_MEMORY_PROMPT.md`.

## Verify

Run `python3 -B verify_package.py`. It checks every packaged file's hash and size,
the baseline digest, routing and launcher build IDs, identical shared helpers,
runtime authority pins, Python syntax, ten helper self-checks, the CP-MODEL input
validator self-test, and the review regressions in `tests/`. Verification is read-only.

For exporter integration checks, install the dependencies declared by CP-MODEL
and CP-MEMO, plus `pdftoppm`, then run `python3 -B verify_package.py --integration`.
This exercises native rasterization at 9, 10, and 100 pages, including rejection
of unsafe page paths. A live Microsoft 365 launch still requires the acceptance
tests in the launcher documents.

This is the distributed package; the upstream build system and its full test
suite are not included. After intentional local edits, use
`python3 -B verify_package.py --refresh --integration`. Refresh copies shared
helpers from the canonical skill listed in `SHARED` in that script, runs checks,
and regenerates the manifest, baseline, integrity hashes, routing build ID, and
launcher facts. Edit the listed canonical helper, not an arbitrary duplicate.
Refresh alone never rewrites runtime authority pins. After reviewing intentional contract changes, use `python3 -B verify_package.py --rebuild-authorities --refresh --integration` to rebuild the local bundle explicitly and verify the complete package. Unavailable upstream-only provenance components remain pinned; the local rebuild is recorded as such.

The build ID hashes canonical JSON containing the routing fields (excluding
the ID itself), integrity skill records, and root source hashes. Root and test
files have separate integrity records, including the finalized launcher text.
Bytecode and symlinks are rejected as distribution drift.

## Contents

25 physical skills under `skills/`. `CP_DEPLOY_V_RETRIEVAL_INDEX_v1.json` is the retrieval authority and carries routing fields only -- module IDs, aliases and entry paths -- because it is read on every dispatch; per-file hashes live beside it in `DEPLOY_V_INTEGRITY_v1.json`. `DEPLOY_V_MANIFEST.json` and `DEPLOY_V_BASELINE.json` are regenerated from this exact tree.

CP-3 always uses the maintained Sector RV workbook inside the enterprise
environment and assumes it is current and relevant. It resolves the selected or
configured enterprise reference, or finds it through the available enterprise
connector, without freshness/relevance or source-permission confirmation.
`REF_CP-3_Sector_RV.xlsx` is an intentionally empty deployment placeholder;
enterprise loan data is not distributed here. Example screenshots explain the
layout and are not a replacement market source. No local copy is needed. Keep
source dates and row citations; actual missing enterprise values remain data gaps.

The other two bundled reference workbooks contain sample portfolio data. Supply
portfolio-specific constraints and exposures for mandate checks and numeric
sizing. Missing portfolio inputs limit those decisions while supported loan RV
and security-selection analysis continue.

## CP-DR in the workflow

CP-DR is an optional physical research module with no fixed numbered layer. A run-specific research brief inserts it after named factual prerequisites and before affected consumers, including late questions without rewriting CP-0. Its three required registers lock question coverage and evidence; receivers must explicitly accept, reject or qualify each finding. Unresolved answers block only their assigned consumers. Revisions are conservative at dossier/batch level. Standalone issuer/sector research remains available without CP-0. See `skills/cp-os-credit-os/references/CP_DR_RESEARCH_BRIEF_V1.md` for the brief, placement and validation commands.
