# ADR 0001: Kotoba is the CCFA catalog source authority

- Status: Accepted
- Date: 2026-07-27

## Decision

`src/association_facts.kotoba` is the sole production source. Both
citations retain every present scalar field, including two DIFFERENT
establishment years — 1997 for the association and 1999 for the China
Franchise Expo — which a test pins so neither is inherited from the other.
Topic count plus indexed access preserves the ordered governance/standards
pair and the franchising singleton. Unknown values and indexes return zero
or typed option-none; no effects are declared.

CI executes reference semantics, restricted JavaScript, instantiated typed
WebAssembly, and production source-authority checks. Clojure and the JVM
are compiler/test hosts only.

## Sourcing decisions specific to this repo

- **ISIC 4719 is narrower than the association.** CCFA's stated membership
  spans 零售・餐饮・服务・供应商. The code was chosen to match the existing
  `assoc-4719-usa-nrf` peer so the two join in the federated query; the
  `coverage-note` states the mismatch, and a test asserts that the note
  still says so.
- **Both entries share one URL**, because the 简介 page states both facts.
  The page links the expo's own site; that site was not read, so it is not
  cited.
- **`url` keeps the `http://` scheme.** ccfa.org.cn does not serve HTTPS.

## Consequences

- The CHN row of the assoc family reaches 2 associations (2910 CAAM,
  4719 CCFA). 6419 remains uncovered for CHN because china-cba.net is
  unreachable — see `cloud-itonami-assoc-2910-chn-caam`'s ADR 0001.
