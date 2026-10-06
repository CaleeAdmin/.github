# Calee GitHub Standards

This repository contains default GitHub governance files for repositories owned by `CaleeAdmin`.

## Calee vision

The organisation-wide product and network direction is recorded in [Calee Vision](CALEE_VISION.md).

That document is strategic direction, not an automatic runtime/product-policy change. Repository-specific architecture, product-policy and implementation contracts remain authoritative for shipped behaviour until changed through their normal review process.

## Issue classification

The authoritative Calee benchmark for issue Complexity, Risk and Priority is:

- [Issue classification benchmark](ISSUE_CLASSIFICATION.md)
- [Machine-readable classification policy](issue-classification.yml)
- [Confirmed open-issue Risk and Priority audit — 6 August 2026](audits/open-issue-risk-priority-2026-08-06.md)

Default issue forms are stored in [`.github/ISSUE_TEMPLATE`](.github/ISSUE_TEMPLATE).

## Current audit snapshot

The confirmed 85-issue planning audit records:

- Complexity: C1=0, C2=9, C3=44, C4=23, C5=9
- Risk: R1=0, R2=5, R3=10, R4=32, R5=38
- Priority: P0=0, P1=44, P2=29, P3=12

The distributions are calibration snapshots, not quotas. Priority must be reassessed when incidents, commitments, blockers or workarounds change.

## Scope

The benchmark applies to product, engineering, operations, infrastructure and regression issues across all Calee repositories. Complexity measures implementation structure and uncertainty; it does not replace Risk or Priority.

## Administration

This repository must remain **public** for GitHub to apply its default issue templates to other repositories owned by `CaleeAdmin`. A repository-specific `.github/ISSUE_TEMPLATE` directory overrides these defaults for that repository.
