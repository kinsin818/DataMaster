# Data Master — Release Notes (public summary)

The publisher keeps a private SHA-256 release ledger for every build; this page
is the buyer-facing summary of what changed along the way. **No binaries are
published in this repository** — the commercial build is distributed via
Gumroad. The certificate used for every release is unchanged across versions
(`CN=DataMaster`), so all builds are mutually upgrade-installable.

## Current build: v2.4.2

Ship-audit remediation build: clearer plain-HTTP disclosure in the AI and
external-model screens, the full JVM verification suite wired into the build
check, and the server-side licensing endpoint hardened (no unauthenticated
refund route). This is the build currently served to customers.

## Lineage (abridged)

| Version | What changed |
|---|---|
| 2.0 | First release. Engine hardening: column ceiling, inflate ceiling, date clamp, boolean fidelity, CSV formula guard, bounded import, cache reclaim. Removed a public signing oracle from the release artifact. |
| 2.0.2 | Engine hardening build (formula-injection guard, bounded import, cache reclaim). |
| 2.1.0 | **Full English UI** (175 strings). Cleaning rules and activation payload unchanged. |
| 2.2.0 | Commercial build: R8 obfuscation + minify + resource shrinking, certificate pinning restored, network calls moved off the main thread (fixes a crash class), self-service rebind button removed. |
| 2.3.0 | Smart AI configuration: **Paste & detect** (extract endpoint fields from a pasted URL), API-key back-inference, model-list dropdown, free-model guide. End-to-end tested with two real providers (Agnes + NVIDIA NIM model catalog). |
| 2.4.0 | Welcome screen. |
| 2.4.1 | Zero-Chinese sweep on buyer-visible surfaces: empty markers rendered as `<MISSING>`, AI system prompt switched to English responses. Engine's ability to *parse* Chinese financial notation (万元/亿元 units, 年月日 dates, city tables) is preserved — it is input parsing, invisible to buyers and inert for foreign data. |
| 2.4.2 | Current build (see above). |

## Reproducibility note

Release APKs are **not** byte-reproducible for this project (ZIP headers and
signing blocks differ slightly between identical-source builds). A recorded
SHA-256 therefore proves *"this artifact was not modified afterwards"*, not
*"this artifact was built from this commit"*. Reproducible builds are tracked
as engineering debt.