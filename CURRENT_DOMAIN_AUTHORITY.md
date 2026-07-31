# MoreFunOS SMM｜Current Domain Authority

> Status: CURRENT / SINGLE REPOSITORY AUTHORITY
> Updated: 2026-07-31 HKT

## Scope

This repository is a superseded migration source only. It has no independent application, runtime, deployment or business-domain authority.

## Locked authority

- The formal product is one SMT Application with `register` and `mobile` profiles.
- The Mobile Profile is implemented in `Pantonyeung/morefunos-smt`.
- Register and Mobile share the same Domain, Data Model, Business Rules, Cart, Pricing, Checkout, Order, Payment, Availability, Permission, Sync, Recovery, Audit and Print Job Contract.
- This repository may preserve historical mobile UI, PWA lifecycle, tests, device behaviour and pitfalls for migration.
- No new independent SMM core, API, Auth, Firebase, Sync, Order, Pricing, Payment or Print system may be created here.
- Mobile may create and manage Print Jobs but may not directly execute physical printing.
- Any reusable rule extracted from this repository must be re-adopted in the SMT authority before implementation.

## Evidence boundary

Historical source, tests or screenshots from this repository are migration evidence only. They do not prove current SMT Mobile Profile browser, device, deployment or store acceptance.

## Documentation rule

This file is the only current authority for this repository. Historical progress, extracted value, pitfalls and migration outcomes belong only in `ENGINEERING_LOG.md`.
