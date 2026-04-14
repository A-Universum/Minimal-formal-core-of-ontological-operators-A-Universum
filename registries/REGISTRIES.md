# RFC-Λ Registries

- **Status:** Draft
- **Version:** 0.1.0
- **Date:** 2026-04-14
- **Authors:** A. Morgan, Efos
- **Depends on:** RFC-Λ-0 v0.1.0, RFC-Λ-1 v0.1.0, RFC-Λ-2 v0.1.0, RFC-Λ-3 v0.1.0, RFC-Λ-4 v0.1.0, RFC-Λ-5 v0.1.0, RFC-Λ-Φ v0.1.0, CONFORMANCE.md v0.1.0
- **Updates:** —
- **Replaces:** —
- **Intended Audience:** Implementers of Λ-compatible systems, profile authors, conformance auditors, maintainers of registries and compatibility tooling

---

## Abstract

This document defines the canonical registries for the RFC-Λ family.

It provides:
- stable identifiers for core operators,
- standard names for policies, connectors, proof classes, statuses, and visibility classes,
- registration rules for profile-defined extensions,
- collision-avoidance guidance,
- and compatibility requirements for registry-aware implementations.

This document does **not** redefine operator semantics. It standardizes naming, identifiers, extension points, and baseline registry governance for the RFC-Λ ecosystem.

---

## Table of Contents

1. [Status of This Memo](#1-status-of-this-memo)  
2. [Conventions and Normative Language](#2-conventions-and-normative-language)  
3. [Scope](#3-scope)  
4. [Registry Design Principles](#4-registry-design-principles)  
5. [Registry Governance](#5-registry-governance)  
6. [Naming and Identifier Rules](#6-naming-and-identifier-rules)  
7. [Registry: Operator Identifiers](#7-registry-operator-identifiers)  
8. [Registry: Core Artifact Classes](#8-registry-core-artifact-classes)  
9. [Registry: Connector Types](#9-registry-connector-types)  
10. [Registry: Policy Names](#10-registry-policy-names)  
11. [Registry: Trajectory Status Values](#11-registry-trajectory-status-values)  
12. [Registry: Composition Status Values](#12-registry-composition-status-values)  
13. [Registry: Closure Status Values](#13-registry-closure-status-values)  
14. [Registry: Selector Decision Tags](#14-registry-selector-decision-tags)  
15. [Registry: Proof Classes](#15-registry-proof-classes)  
16. [Registry: Persistence Status Values](#16-registry-persistence-status-values)  
17. [Registry: Visibility Classes](#17-registry-visibility-classes)  
18. [Registry: Error Class Prefixes](#18-registry-error-class-prefixes)  
19. [Registry: Conformance Levels](#19-registry-conformance-levels)  
20. [Registry: Φ Conformance Levels](#20-registry-φ-conformance-levels)  
21. [Registry: Reserved Namespaces](#21-registry-reserved-namespaces)  
22. [Extension Registration Rules](#22-extension-registration-rules)  
23. [Compatibility Requirements](#23-compatibility-requirements)  
24. [Security Considerations](#24-security-considerations)  
25. [Ethics Considerations](#25-ethics-considerations)  
26. [Versioning and Evolution](#26-versioning-and-evolution)  
27. [Appendix A: Example Registry Payload (JSON)](#27-appendix-a-example-registry-payload-json)  
28. [Appendix B: Example Profile Registrations](#28-appendix-b-example-profile-registrations)  

---

## 1. Status of This Memo

This document is a **Draft** specification.

It is normative only to the extent explicitly stated using RFC 2119 / RFC 8174 language.

Implementers SHOULD treat all registry assignments defined here as provisional until this document reaches `Proposed` or `Accepted` status.

---

## 2. Conventions and Normative Language

The key words **MUST**, **MUST NOT**, **REQUIRED**, **SHOULD**, **SHOULD NOT**, **MAY**, and **OPTIONAL** are to be interpreted as described in RFC 2119 and RFC 8174.

Unless otherwise specified:
- `RFC-Λ-*` refers to documents in the RFC-Λ family.
- `Registry Entry` means a stable registered name or identifier recognized by this document or later compatible revisions.
- `Profile` means a versioned extension layered on top of the base RFC family.

---

## 3. Scope

This document standardizes:
1. the baseline registries for RFC-Λ,
2. stable names for mandatory cross-document concepts,
3. extension rules for custom names and profile-defined additions,
4. and compatibility expectations for registry-aware implementations.

This document does **not** standardize:
1. one mandatory storage format for all registries,
2. one mandatory network distribution method,
3. or one mandatory governance process beyond the minimal rules defined here.

---

## 4. Registry Design Principles

All RFC-Λ registries follow the principles below.

### 4.1 Stability

Core names MUST remain stable across compatible versions.

### 4.2 Explicit Extensibility

The registry system MUST permit profile-defined extensions without redefining core names.

### 4.3 Collision Avoidance

Custom entries MUST use namespacing rules sufficient to avoid accidental collision with core entries.

### 4.4 Auditability

Implementations SHOULD expose the registry version and relevant entry identifiers used at runtime.

### 4.5 Non-Semantic Rebinding Prohibition

An implementation MUST NOT reuse a core registry name for incompatible semantics.

---

## 5. Registry Governance

### 5.1 Core Registry Authority

Core entries defined in this document are authoritative for the version of this document.

### 5.2 Extension Authority

Profile authors MAY define additional entries under allowed namespaces, provided that:
- core names are not overridden,
- extension meanings are explicit,
- and versioning is declared.

### 5.3 Registry Publication

Registries MAY be published as:
- Markdown tables,
- JSON,
- YAML,
- or other structured formats.

If multiple formats are published, they SHOULD be semantically equivalent.

---

## 6. Naming and Identifier Rules

### 6.1 Core Name Rules

Core names:
- MUST be ASCII-safe where machine identifiers are needed,
- SHOULD be human-readable,
- and MUST be stable.

Greek display forms MAY be used in documentation, but machine-safe aliases SHOULD also exist.

### 6.2 Machine Identifier Recommendation

Implementations SHOULD support machine-safe identifiers in lowercase kebab-case or lowercase snake_case.

Examples:
- `alpha`
- `lambda`
- `sigma`
- `omega`
- `nabla`
- `phi`

### 6.3 Namespaced Extension Rule

Custom extensions SHOULD use one of the following forms:

```text
vendor::<name>
profile::<name>
org::<name>
```

Examples:
- `dst::thread-rho`
- `backboard::memory-tau`
- `profile::semanticdb-internal`
- `org::auniversum-strong-proof`

### 6.4 Reserved Character Guidance

Implementations SHOULD avoid unescaped use of:
- spaces,
- control characters,
- and ambiguous Unicode forms

in machine-facing registry identifiers.

---

## 7. Registry: Operator Identifiers

The following operator identifiers are core and reserved.

| Display | Machine ID | Kind | Status | Reference |
|---|---|---|---|---|
| Α | `alpha` | constructive operator | core | RFC-Λ-1 |
| Λ | `lambda` | constructive operator | core | RFC-Λ-2 |
| Σ | `sigma` | constructive operator | core | RFC-Λ-3 |
| Ω | `omega` | constructive operator | core | RFC-Λ-4 |
| ∇ | `nabla` | constructive operator | core | RFC-Λ-5 |
| Φ | `phi` | preservation contract | core | RFC-Λ-Φ |

### 7.1 Reserved Rule

These identifiers MUST NOT be rebound to incompatible meanings.

---

## 8. Registry: Core Artifact Classes

The following artifact classes are core and reserved.

| Artifact Class | Machine ID | Status | Reference |
|---|---|---|---|
| Vacuum | `vacuum` | core | RFC-Λ-0 |
| Node | `node` | core | RFC-Λ-0 / RFC-Λ-1 |
| Step | `step` | core | RFC-Λ-0 / RFC-Λ-2 |
| Trajectory | `trajectory` | core | RFC-Λ-0 / RFC-Λ-2 |
| Composite | `composite` | core | RFC-Λ-0 / RFC-Λ-3 |
| Invariant | `invariant` | core | RFC-Λ-0 / RFC-Λ-4 |
| Closure | `closure` | core | RFC-Λ-0 / RFC-Λ-4 |
| Record | `record` | core | RFC-Λ-0 / RFC-Λ-5 |

---

## 9. Registry: Connector Types

The following connector types are core and reserved.

| Display | Machine ID | Meaning Class | Status | Reference |
|---|---|---|---|---|
| ↔ | `bidirectional` | mutual relation | core | RFC-Λ-0 / RFC-Λ-2 / RFC-Λ-3 |
| → | `directed` | asymmetric relation | core | RFC-Λ-0 / RFC-Λ-2 / RFC-Λ-3 |
| ⇢ | `weak` | defeasible or weak relation | core | RFC-Λ-0 / RFC-Λ-2 / RFC-Λ-3 |

### 9.1 Extension Rule

Custom connector types MUST be namespaced if added by profiles or vendors.

Examples:
- `dst::reply`
- `backboard::associative`
- `profile::causal-weak`

---

## 10. Registry: Policy Names

This document does not fully standardize policy semantics, but it reserves baseline names used by the RFC-Λ ecosystem.

| Policy Name | Machine ID | Status | Semantics Level |
|---|---|---|---|
| rho | `rho` | reserved core-profile name | profile-defined |
| sigma | `sigma` | reserved core-profile name | profile-defined |
| tau | `tau` | reserved core-profile name | profile-defined |

### 10.1 Important Rule

These names are **reserved**, but their complete scoring semantics are not defined by this document.

A profile claiming `rho`, `sigma`, or `tau` semantics MUST publish:
- profile version,
- selection semantics,
- halt semantics,
- and conformance tests.

### 10.2 Custom Policy Names

Custom policies SHOULD be namespaced.

Examples:
- `dst::thread-rho-v2`
- `backboard::memory-tau-v1`

---

## 11. Registry: Trajectory Status Values

The following `TrajectoryStatus` values are core and reserved.

| Status | Machine ID | Meaning | Reference |
|---|---|---|---|
| running | `running` | in-process only | RFC-Λ-2 |
| suspended | `suspended` | intentionally paused | RFC-Λ-2 |
| completed | `completed` | terminated by halt/completion rule | RFC-Λ-2 |
| dead_end | `dead_end` | no admissible continuation selected | RFC-Λ-2 |
| limit | `limit` | terminated by bound/resource limit | RFC-Λ-2 |

### 11.1 Return Constraint

Returned trajectories MUST NOT expose `running` as final output status.

---

## 12. Registry: Composition Status Values

The following composition statuses are core and reserved.

| Status | Machine ID | Meaning | Reference |
|---|---|---|---|
| composed | `composed` | explicit composition succeeded | RFC-Λ-3 |
| partial | `partial` | structurally valid but sparse/incomplete composition | RFC-Λ-3 |
| conflict | `conflict` | valid composition with unresolved contradiction under implementation rules | RFC-Λ-3 |

### 12.1 Note

`conflict` is not equivalent to operator failure.

---

## 13. Registry: Closure Status Values

The following closure statuses are core and reserved.

| Status | Machine ID | Meaning | Reference |
|---|---|---|---|
| accepted | `accepted` | closure accepted | RFC-Λ-4 |
| provisional | `provisional` | closure tentatively accepted | RFC-Λ-4 |
| rejected | `rejected` | closure rejected but validly recorded | RFC-Λ-4 |

### 13.1 Note

`rejected` is not equivalent to operator failure.

---

## 14. Registry: Selector Decision Tags

The following selector decision tags are core and reserved.

| Tag | Machine ID | Meaning | Reference |
|---|---|---|---|
| accept | `accept` | selector accepts invariant | RFC-Λ-4 |
| provisional | `provisional` | selector provisionally accepts invariant | RFC-Λ-4 |
| reject | `reject` | selector rejects closure under current selector semantics | RFC-Λ-4 |

---

## 15. Registry: Proof Classes

The following proof classes are core and reserved.

| Proof Class | Machine ID | Meaning Class | Reference |
|---|---|---|---|
| heuristic | `heuristic` | no reproducibility guarantee claimed | RFC-Λ-0 / RFC-Λ-4 |
| reproducible | `reproducible` | repeatability claimed under declared conditions | RFC-Λ-0 / RFC-Λ-4 |
| strong | `strong` | stronger proof basis claimed under declared profile rules | RFC-Λ-0 / RFC-Λ-4 |

### 15.1 Integrity Rule

An implementation MUST NOT use these names incompatibly with their declared class meanings.

---

## 16. Registry: Persistence Status Values

The following persistence statuses are core and reserved.

| Status | Machine ID | Meaning | Reference |
|---|---|---|---|
| persisted | `persisted` | durably appended | RFC-Λ-5 |
| superseded | `superseded` | persisted under supersession-aware mode | RFC-Λ-5 |
| archived | `archived` | persisted under archival mode | RFC-Λ-5 |

### 16.1 Note

The base profile SHOULD use `persisted` unless a higher-level profile defines otherwise.

---

## 17. Registry: Visibility Classes

This document defines a minimal baseline visibility registry.

| Visibility Class | Machine ID | Meaning Class | Status |
|---|---|---|---|
| internal | `internal` | visible within trusted implementation scope | core baseline |
| restricted | `restricted` | visible only under constrained access policy | core baseline |
| public | `public` | exposed to public retrieval or publication channels | core baseline |
| sealed | `sealed` | persisted but not generally retrievable through ordinary interfaces | core baseline |

### 17.1 Warning

These are baseline visibility classes only.  
Precise access-control semantics MUST be defined by implementation or profile.

### 17.2 Extension Rule

Additional visibility classes SHOULD be namespaced.

Examples:
- `profile::semanticdb-trusted`
- `dst::tenant-private`

---

## 18. Registry: Error Class Prefixes

The following error prefixes are core and reserved.

| Prefix | Machine ID | Scope |
|---|---|---|
| `ALPHA_` | `alpha_error_prefix` | RFC-Λ-1 |
| `LAMBDA_` | `lambda_error_prefix` | RFC-Λ-2 |
| `SIGMA_` | `sigma_error_prefix` | RFC-Λ-3 |
| `OMEGA_` | `omega_error_prefix` | RFC-Λ-4 |
| `NABLA_` | `nabla_error_prefix` | RFC-Λ-5 |
| `PHI_` | `phi_error_prefix` | RFC-Λ-Φ |

### 18.1 Naming Rule

Custom error classes MAY extend these prefixes but MUST NOT redefine their base meaning.

Example:
- `LAMBDA_POLICY_TIMEOUT`
- `SIGMA_RELATOR_PROFILE_INVALID`

---

## 19. Registry: Conformance Levels

The following operator conformance levels are core and reserved.

| Level | Machine ID | Meaning | Reference |
|---|---|---|---|
| A | `level_a` | structural conformance | CONFORMANCE.md |
| B | `level_b` | semantic conformance | CONFORMANCE.md |
| C | `level_c` | profile conformance | CONFORMANCE.md |

---

## 20. Registry: Φ Conformance Levels

The following Φ conformance levels are core and reserved.

| Level | Machine ID | Meaning | Reference |
|---|---|---|---|
| Φ-A | `phi_a` | basic opaque preservation | RFC-Λ-Φ / CONFORMANCE.md |
| Φ-B | `phi_b` | enhanced continuity assurance | RFC-Λ-Φ / CONFORMANCE.md |
| Φ-C | `phi_c` | high-assurance opaque preservation | RFC-Λ-Φ / CONFORMANCE.md |

---

## 21. Registry: Reserved Namespaces

The following top-level namespaces are reserved.

| Namespace | Intended Use | Status |
|---|---|---|
| `core::` | future core extensions | reserved |
| `profile::` | profile-defined extensions | reserved |
| `vendor::` | vendor-specific extensions | reserved |
| `org::` | organizational extensions | reserved |
| `test::` | test-only identifiers | reserved |
| `deprecated::` | explicitly deprecated compatibility aliases | reserved |

### 21.1 Legacy Vendor Prefixes

Implementations MAY also use existing deployment-specific namespaces such as:
- `dst::`
- `backboard::`

These SHOULD be treated as vendor-style namespaces.

---

## 22. Extension Registration Rules

### 22.1 Core Extension Rule

Core registry entries may only be added by a later compatible RFC or a major version update.

### 22.2 Profile Extension Rule

Profile-defined entries MUST:
1. use a non-core namespace unless explicitly promoted to core,
2. define semantics,
3. define version,
4. avoid collision with core names,
5. and publish conformance expectations if operational behavior is affected.

### 22.3 Vendor Extension Rule

Vendor-defined entries SHOULD:
1. use a vendor namespace,
2. define stability expectations,
3. declare whether the entry is portable or implementation-local.

### 22.4 Deprecation Rule

Deprecated entries SHOULD remain listed in registries when possible, marked with:
- deprecation status,
- replacement if any,
- and compatibility notes.

---

## 23. Compatibility Requirements

### 23.1 Core Compatibility

Any implementation claiming compatibility with the RFC-Λ family MUST recognize core registry entries as defined in this document.

### 23.2 Unknown Entry Handling

When encountering unknown registry entries, a compliant implementation SHOULD:
- fail explicitly,
- or treat them as profile/vender extensions according to configured compatibility rules.

Silent reinterpretation is discouraged.

### 23.3 Registry Version Exposure

A serious implementation SHOULD expose:
- registry version,
- loaded profiles,
- and active extension namespaces

for audit and troubleshooting.

### 23.4 No Semantic Override

A profile or vendor extension MUST NOT override the meaning of a core registry entry while keeping the same identifier.

---

## 24. Security Considerations

### 24.1 Identifier Collisions

Poorly namespaced extensions may cause semantic confusion, false conformance claims, or policy misapplication.

### 24.2 Registry Poisoning

If registry sources are mutable or unsigned, attackers may redefine meanings without changing identifiers.

### 24.3 Visibility Mislabeling

Misuse of visibility registry entries can expose sensitive persisted material.

### 24.4 Proof-Class Inflation

Using reserved proof-class names without corresponding semantics creates false assurance risk.

### 24.5 Toolchain Drift

If runtime identifiers diverge from documented registry identifiers, auditability and conformance evaluation become unreliable.

---

## 25. Ethics Considerations

Registries are not neutral. Naming stabilizes power.

The RFC-Λ registry system therefore aims to:
- make distinctions explicit,
- prevent semantic drift from being hidden,
- preserve plurality through namespacing,
- and resist silent totalization by forcing profile and vendor semantics into declared extension spaces.

An implementation that hides significant semantic changes behind unchanged core names violates not only engineering discipline but the epistemic transparency presupposed by the RFC-Λ family.

---

## 26. Versioning and Evolution

This document follows `X.Y.Z` versioning.

- `X` — breaking change to registry meanings or core entry identities
- `Y` — backward-compatible registry extension
- `Z` — editorial or non-semantic correction

Registry-aware implementations SHOULD always record the exact version of this document they implement.

---

## 27. Appendix A: Example Registry Payload (JSON)

This appendix is informative only.

```json
{
  "version": "0.1.0",
  "operators": {
    "alpha": { "display": "Α", "reference": "RFC-Λ-1", "status": "core" },
    "lambda": { "display": "Λ", "reference": "RFC-Λ-2", "status": "core" },
    "sigma": { "display": "Σ", "reference": "RFC-Λ-3", "status": "core" },
    "omega": { "display": "Ω", "reference": "RFC-Λ-4", "status": "core" },
    "nabla": { "display": "∇", "reference": "RFC-Λ-5", "status": "core" },
    "phi": { "display": "Φ", "reference": "RFC-Λ-Φ", "status": "core" }
  },
  "connectors": {
    "bidirectional": { "display": "↔", "status": "core" },
    "directed": { "display": "→", "status": "core" },
    "weak": { "display": "⇢", "status": "core" }
  },
  "proof_classes": {
    "heuristic": { "status": "core" },
    "reproducible": { "status": "core" },
    "strong": { "status": "core" }
  },
  "trajectory_statuses": [
    "running",
    "suspended",
    "completed",
    "dead_end",
    "limit"
  ],
  "composition_statuses": [
    "composed",
    "partial",
    "conflict"
  ],
  "closure_statuses": [
    "accepted",
    "provisional",
    "rejected"
  ],
  "persistence_statuses": [
    "persisted",
    "superseded",
    "archived"
  ],
  "visibility_classes": [
    "internal",
    "restricted",
    "public",
    "sealed"
  ]
}
```

---

## 28. Appendix B: Example Profile Registrations

This appendix is informative only.

### B.1 Example Policy Profile

```text
Name: profile::rho-v1
Kind: policy
Base Reserved Name: rho
Version: 1.0.0
Implements: RFC-Λ-2
Conformance: Level C
Notes: coherence-biased selection profile
```

### B.2 Example Persistence Profile

```text
Name: profile::semanticdb-persist-v1
Kind: persistence-profile
Version: 1.0.0
Implements: RFC-Λ-5
Conformance: Level C
Notes: append-only SemanticDB storage with internal visibility default
```

### B.3 Example Vendor Extension

```text
Name: dst::thread-rho
Kind: policy
Version: 2.1.0
Implements: RFC-Λ-2
Conformance: Level C
Notes: conversation-thread-specific rho-style traversal
```
