# cloud-itonami-assoc-4719-chn-ccfa

Industry rule catalog for **中国连锁经营协会 (China Chain Store & Franchise
Association, CCFA)** — the second CHN member of the
`cloud-itonami-assoc-*` family after
[`cloud-itonami-assoc-2910-chn-caam`](https://github.com/cloud-itonami/cloud-itonami-assoc-2910-chn-caam),
and the CHN peer of
[`cloud-itonami-assoc-4719-usa-nrf`](https://github.com/cloud-itonami/cloud-itonami-assoc-4719-usa-nrf).
Part of the [`cloud-itonami`](https://github.com/cloud-itonami)
compliance-fact family (ADR-2607141700, in `com-junkawasaki/root`).

## Scope

A **read-only reference/archive** catalog — not an Advisor⊣Governor
actuation actor. It proposes or executes nothing on CCFA's behalf, and it
is not CCFA.

## Data

- `src/association_facts.kotoba` — the sole production source.
- `schema/association-rule.edn` — DataScript schema, identical to every
  sibling so the federated query joins across them unchanged.
- `data/datascript-tx.edn` — derived DataScript tx-data.

## Verification

Both entries come from CCFA's own **简介** page
(<http://www.ccfa.org.cn/portal/cn/xiangxic.jsp?type=11>, 发布 2025/01/01),
read on **2026-07-27**. That page states the 1997 founding, the 1600+
member companies, the membership scope (零售・餐饮・服务・供应商), the
stated purpose, and that 中国特许加盟展 was 始办于1999年 and is 经中国商务部
批准 and 由中国连锁经营协会主办.

**Two things recorded rather than smoothed over:**

1. **ISIC 4719 is narrower than CCFA.** CCFA's own membership spans
   retail, food service, services and suppliers. The code follows the
   assignment `cloud-itonami-assoc-4719-usa-nrf` already uses, so the two
   are joinable — it is *not* a claim that CCFA is confined to 4719. The
   `coverage-note` says so and a test asserts that it does.
2. **Both entries cite the same URL**, because that one page states both
   facts. No separate expo-site URL is claimed even though the page links
   one; only the page that was read is cited.

The site is HTTP-only; the `url` field records the `http://` scheme it
actually serves.

## License

AGPL-3.0-or-later. Document text remains CCFA's; this repo stores only
citation metadata.

## Running it

`clojure -M:test` (3 tests, 17 assertions: reference semantics, restricted
JavaScript, instantiated typed WebAssembly, source authority) and
`clojure -M:lint`.
