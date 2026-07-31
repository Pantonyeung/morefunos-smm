# More Fun SMM｜Migration Source Entry

> Status: `SUPERSEDED AS INDEPENDENT CORE / REFERENCE ONLY`

This repository is not a current MoreFunOS application authority and must not be developed or deployed as a second SMM core.

## Canonical reading order

1. `README.md`
2. `CURRENT_DOMAIN_AUTHORITY.md`
3. `ENGINEERING_LOG.md`
4. `AGENTS.md`
5. Current `Pantonyeung/morefunos-smt` branch, PR, tests and device evidence
6. MoreFunOS Knowledge Base V2

## Current product placement

MoreFunOS keeps one SMT Application with two profiles:

- `register`: register / large-screen profile;
- `mobile`: phone / tablet profile migrated from SMM.

Both profiles share one Domain, Data Model, Business Rules, Cart, Pricing, Checkout, Order, Payment, Availability, Permission, Sync, Recovery, Audit and Print Job Contract.

## Allowed repository use

- historical mobile UI and interaction reference;
- PWA and mobile lifecycle migration source;
- reusable tests and device-behaviour evidence;
- regression comparison and historical pitfalls.

## Prohibited use

- independent Runtime, Domain, API, Auth, Firebase or Sync core;
- independent Order, Pricing, Payment or Print authority;
- production deployment as a standalone SMM application;
- direct physical-printer control from the Mobile Profile;
- treating old branch, README, handoff, WORK, FINAL, LOCK or deployment records as current authority.

## Printing boundary

```text
Mobile Profile
→ Shared Print Domain
→ Print Job API
→ SMT Android Host
→ Physical Printer
→ Actual Result Callback
```

Queue or API success is not physical print success.
