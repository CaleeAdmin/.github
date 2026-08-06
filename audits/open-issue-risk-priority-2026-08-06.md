# Open Issue Risk and Priority Audit — 6 August 2026

**Status:** Confirmed planning audit  
**Scope:** 85 open issues in the approved CaleeAdmin complexity inventory  
**Benchmark:** `ISSUE_CLASSIFICATION.md`, policy version 2

This audit preserves the approved Complexity classification and assigns Risk and Priority independently. It is a point-in-time planning decision, not a permanent quota. Priority must be reassessed when incidents, deadlines, blockers, workarounds or commitments change.

## Distribution

- Risk: R1=0, R2=5, R3=10, R4=32, R5=38
- Priority: P0=0, P1=44, P2=29, P3=12

No issue met P0 because the issue records did not establish an active incident or immediate no-workaround blocker requiring interruption of planned work.

## Confirmed classifications

| Repository issue | Complexity | Risk | Priority | Audit rationale |
|---|---:|---:|---:|---|
| `Calee#988` | C3 | R3 | P2 | Large-account slowdown is material but bounded and measurable; planned performance work. |
| `Calee#989` | C2 | R2 | P2 | Local interaction regression is visible and readily reversible; approved UI work. |
| `Calee#990` | C3 | R5 | P1 | Activation/session mistakes can cross household or trusted-device boundaries; required for the Home model. |
| `Calee#991` | C3 | R4 | P1 | Silent stale calendar data affects a core always-on display journey; near-term correctness work. |
| `calee-hub-admin#26` | C3 | R4 | P1 | False readiness and unsafe repair can disrupt core service access; needed with provisioning repair. |
| `calee-hub-admin#27` | C3 | R5 | P1 | Admin mistakes can alter entitlements, billing-derived state, device ownership or sensitive operations; required for launch operations. |
| `calee-hub-ai#4` | C4 | R5 | P1 | Entitlement, quota or logging failure can cause billing leakage, private-data exposure or uncontrolled spend; core AI launch control. |
| `calee-hub-app#32` | C3 | R5 | P1 | Incorrect portal enforcement can grant or revoke household access across trust boundaries; required before entitlement enforcement. |
| `calee-hub-calembed#68` | C3 | R3 | P2 | Matrix rendering errors are bounded to presentation and have per-source degradation; planned product enhancement. |
| `calee-hub-core#362` | C3 | R4 | P1 | False-ready states block core access while reporting success; minimal repair precedes broader architecture. |
| `calee-hub-core#363` | C4 | R5 | P1 | Provisioning mistakes can create credential, membership and cross-service access failures; foundational reliability work. |
| `calee-hub-core#364` | C4 | R4 | P1 | Identifier collisions can mutate the wrong chore or hide data; compatibility migration should precede broader chore work. |
| `calee-hub-core#365` | C3 | R4 | P1 | Destructive manual recovery can duplicate or remove mappings and prolong a core sync failure; recurring support burden. |
| `calee-hub-core#366` | C3 | R3 | P3 | Lookup failure is bounded by free-text fallback; optional enhancement with no committed blocker. |
| `calee-hub-core#367` | C5 | R5 | P2 | Notification routing errors can expose private event routing or cross accounts, but the platform is future planned work. |
| `calee-hub-core#368` | C4 | R5 | P1 | Entitlement mistakes can improperly grant, deny or share paid household capabilities; foundation for the approved pricing model. |
| `calee-hub-core#369` | C4 | R5 | P1 | Activation replay or household-binding errors can transfer product access or trusted hardware incorrectly; required for display activation. |
| `calee-hub-core#370` | C4 | R5 | P1 | Subscription verification errors can charge, refund or entitle households incorrectly; required before AI sales. |
| `calee-hub-core#371` | C2 | R4 | P1 | Incorrect catalogue rules can propagate conflicting commercial promises and lifecycle behaviour; blocks safe implementation and publication. |
| `calee-hub-core#372` | C4 | R5 | P1 | Migration or enforcement errors can lock out valid households or grant access improperly at scale; required before rollout. |
| `calee-hub-core#373` | C3 | R4 | P1 | Capability disagreement can block production attachment use and obscure recovery; current reliability follow-up. |
| `calee-hub-intake#12` | C2 | R3 | P2 | Stale printed onboarding can block or confuse activation but is recoverable through support; approved artefact work. |
| `calee-hub-web#78` | C2 | R2 | P2 | Content or navigation defects are visible and reversible; approved marketing enhancement. |
| `calee-hub-web#81` | C3 | R4 | P1 | Conflicting pricing and legal claims can mislead customers and stores; required before the new commercial model is published. |
| `calee-hub-web#82` | C4 | R5 | P1 | Payment, refund, order or fulfilment errors can charge customers incorrectly or expose order data; required for auditable sales. |
| `calee-hub-web#83` | C2 | R2 | P2 | Focused layout regression is visible and readily reversible; planned page refinement. |
| `calee-regression#51` | C4 | R4 | P1 | Missing physical evidence or unsafe shared fixtures can invalidate release decisions; current readiness work. |
| `calee-regression#52` | C5 | R5 | P1 | Coverage must prevent incorrect charging, entitlement, migration and lockout; release-critical commercial programme. |
| `calee-regression#53` | C3 | R4 | P1 | Missing readiness coverage can allow false-ready core services into release; companion to active provisioning repair. |
| `calee-regression#54` | C3 | R4 | P1 | Calendar defects can silently omit, duplicate or misdate family events; permanent core release coverage. |
| `calee-regression#55` | C3 | R5 | P2 | Notification isolation failures can disclose private event routing across accounts; planned with the future delivery platform. |
| `calee-regression#56` | C3 | R5 | P1 | Kiosk escape or credential leakage crosses the trusted-device boundary; required with Wi-Fi onboarding. |
| `calee-regression#57` | C3 | R4 | P2 | Unbounded data can make core clients unusable, but controlled performance work can follow immediate correctness. |
| `calee-regression#58` | C3 | R3 | P2 | Website/embed regressions are material but bounded and normally reversible; planned quality coverage. |
| `calee-regression#59` | C4 | R4 | P2 | Coverage gaps or hidden flakes can produce false release confidence; approved governance platform. |
| `calee-regression#60` | C5 | R4 | P2 | Environment errors can invalidate integration evidence or mix fixtures, but it is an internal controlled system; planned foundation. |
| `calee-regression#61` | C5 | R5 | P2 | Programme covers trust, billing, privacy and cross-account boundaries; broad planned integration work rather than an active blocker. |
| `calee-regression#62` | C3 | R4 | P2 | Cross-client conflict errors can lose or duplicate important calendar data; planned integration coverage. |
| `calee-regression#63` | C3 | R5 | P2 | Cross-household mutation or metadata mismatch can expose or corrupt family task/chore data; planned integration coverage. |
| `calee-regression#64` | C3 | R4 | P2 | Cross-client meal/shopping inconsistency can silently lose household planning data; planned integration coverage. |
| `calee-regression#65` | C3 | R5 | P1 | Identity or credential boundary failure can expose tokens or cross services/accounts; high-priority security integration coverage. |
| `calee-regression#66` | C3 | R5 | P1 | Permission propagation failures can expose household resources or allow stale writes; high-priority trust-boundary coverage. |
| `calee-regression#67` | C3 | R5 | P2 | OAuth, inbound email or URL-validation failures can expose credentials/data or enable SSRF; planned provider integration coverage. |
| `calee-regression#68` | C3 | R5 | P2 | AI integration can expose private content or bypass explicit save/authorisation boundaries; planned safety coverage. |
| `calee-regression#69` | C3 | R5 | P2 | Public sharing and SSRF/revocation failures can disclose private calendar data; planned sharing coverage. |
| `calee-regression#70` | C3 | R5 | P1 | Admin repair and entitlement actions cross sensitive authorisation boundaries; high-priority operational coverage. |
| `calee-regression#71` | C3 | R5 | P1 | Deployment/version errors can expose secrets, corrupt schemas or break authentication broadly; high-priority release safety coverage. |
| `calee-regression#72` | C5 | R5 | P2 | Recovery and legacy coexistence span credentials, cross-account isolation and data integrity; planned programme work. |
| `calee-regression#73` | C5 | R4 | P3 | Appliance failure affects internal evidence and operations but not production directly; large uncommitted infrastructure programme. |
| `calee-regression#74` | C3 | R3 | P3 | Sizing mistakes are bounded to the test appliance and recoverable; exploratory prerequisite. |
| `calee-regression#75` | C4 | R4 | P3 | Container isolation or packaging mistakes can invalidate test evidence or expose test secrets; uncommitted appliance work. |
| `calee-regression#76` | C4 | R5 | P3 | Secrets or network-boundary mistakes could expose credentials or reach production, but the appliance remains future work. |
| `calee-regression#77` | C4 | R4 | P3 | Fixture collision or restore error can invalidate evidence and corrupt synthetic state; future appliance work. |
| `calee-regression#78` | C4 | R4 | P3 | Orchestration/report errors can falsely certify releases; future appliance work. |
| `calee-regression#79` | C4 | R4 | P3 | Wrong-SHA promotion or deployment ordering can invalidate release evidence; future appliance work. |
| `calee-regression#80` | C4 | R4 | P3 | Worker/evidence mismatch can falsely satisfy physical gates or expose lab credentials; future appliance work. |
| `calee-regression#81` | C4 | R4 | P3 | Backup, fault and observability failures can exhaust or misoperate the appliance; future operational work. |
| `CaleeMobile#502` | C4 | R4 | P1 | Failures affect core calendar access, reminders, scale and release readiness; near-term mobile readiness. |
| `CaleeMobile#503` | C5 | R4 | P1 | Incorrect planning/shopping data can be silently incomplete across clients; active product initiative. |
| `CaleeMobile#504` | C4 | R5 | P2 | Isolation failure can leak data or credentials across unrelated accounts; strategically approved but no immediate incident or committed blocker is stated. |
| `CaleeMobile#505` | C3 | R4 | P1 | Shopping generation can silently omit or retain stale items; correctness foundation for the active Meals initiative. |
| `CaleeMobile#506` | C3 | R4 | P2 | Partial saves or linkage errors can create misleading household meal data; sequenced after shopping correctness. |
| `CaleeMobile#507` | C3 | R3 | P2 | UI regression is visible and recoverable; planned after correctness foundations. |
| `CaleeMobile#508` | C3 | R3 | P1 | Bounded selection/linkage regression; explicitly assigned with a committed 9 August 2026 due date. |
| `CaleeMobile#509` | C3 | R3 | P2 | Wrong-week or replacement mistakes are bounded and recoverable; planned initiative work. |
| `CaleeMobile#510` | C4 | R5 | P2 | Queued mutations can cross household boundaries or lose durable changes; sequenced after core shopping correctness. |
| `CaleeMobile#511` | C3 | R4 | P2 | Incorrect aggregation can silently understate household requirements; dependent planned correctness work. |
| `CaleeMobile#512` | C2 | R2 | P3 | Optimisation errors are detectable and reversible; should not displace correctness or release work. |
| `CaleeMobile#513` | C2 | R5 | P1 | Release-process failure can expose signing credentials or publish the wrong build; near-term store readiness. |
| `CaleeMobile#514` | C2 | R3 | P2 | Workflow changes can skip checks or disrupt releases but are repository-bounded and reversible; planned governance work. |
| `CaleeMobile#518` | C3 | R4 | P1 | Onboarding errors can block acquisition or lose local subscriptions; foundation for the approved model. |
| `CaleeMobile#519` | C4 | R5 | P1 | Billing and entitlement errors can charge or unlock households incorrectly; core commercial capability. |
| `CaleeMobile#521` | C3 | R5 | P2 | Analytics could collect private schedule or children data; important but follows privacy approval and core implementation. |
| `CaleeMobile#522` | C3 | R5 | P1 | Store misconfiguration can mix environments or bill/verify incorrectly; required before selling AI. |
| `CaleeMobile#523` | C3 | R5 | P1 | Staged-file isolation failure can expose attachments across accounts and current flow is unreliable; high-priority hardening. |
| `CaleeMobile#524` | C5 | R5 | P1 | Programme includes attachment loss, authorisation mismatch and possible cross-account staged-data exposure; production reliability gate. |
| `CaleeMobile#528` | C2 | R2 | P3 | Picker cancellation discoverability is a bounded UX issue with a system-back workaround; separate lower-priority enhancement. |
| `CaleeMobile-Regression#51` | C3 | R5 | P2 | Missing isolation tests can allow cross-account data or credential leakage; planned alongside the account feature. |
| `CaleeMobile-Regression#52` | C5 | R5 | P1 | Programme covers offline account isolation and silent shopping correctness; active initiative release coverage. |
| `CaleeMobile-Regression#53` | C3 | R5 | P1 | Attachment tests protect private files, account isolation and release-critical transfer paths; immediate companion coverage. |
| `CaleeMobile-Regression#54` | C3 | R4 | P1 | Broken recovery can duplicate/remove mappings and prolong core sync failures; companion to recurring support work. |
| `CaleeMobile-Regression#55` | C3 | R4 | P1 | Deep-link/account routing failures can attach feeds to the wrong identity or block acquisition; mobile readiness dependency. |
| `CaleeMobile-Regression#56` | C3 | R4 | P1 | Identifier collisions can mutate the wrong chore or hide records; required with the compatibility migration. |
| `CaleeShell#209` | C4 | R5 | P1 | System-settings escape and Wi-Fi credential handling cross the trusted kiosk boundary; core tablet onboarding/recovery. |
| `CaleeShell#210` | C4 | R5 | P1 | Identity cloning or reset failure can transfer household entitlement or trusted sessions; foundational display security. |

## Reassessment triggers

- Promote to P0 only when an active incident or immediate no-workaround blocker is evidenced and an incident owner is active.
- Reassess R5 when architecture or controls remove—or introduce—a credible privacy, credential, billing, trust-boundary or irreversible-loss path.
- Reassess Priority when a committed release date changes, a dependency is completed, a workaround becomes available, or customer exposure materially changes.
- Child issues retain independent Risk and Priority; they do not inherit the epic values automatically.
