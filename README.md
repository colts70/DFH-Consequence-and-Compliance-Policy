DFH-Consequence-and-Compliance-Policy
Global Enforcement Framework for the Semantic Stack & Deterministic First-Hop (DFH)

Status: Open Specification
Version: 1.0.0
License: MIT

This repository defines the compliance, validation, and consequence model for the DFH Semantic Stack.

Shape breaks → determinism breaks
Determinism breaks → grounding breaks
Grounding breaks → authority collapses


Non-criminal — no legal, financial, or punitive enforcement

Protocol-level only — consequences emerge from loss of trust and resolution

Deterministic — if the required shape is broken, the system must ignore it

DFH / Semantic Stack only functions if all participants follow the same structural contract.

0. Scope

These rules apply to any implementation of:

The Semantic Stack concept

The DFH (Deterministic First-Hop) mechanism

The /.well-known/stack descriptor

The Five Anchors: type, entity, url, sitemap, canonical

DFH-aware tooling (validators, generators, installers)

Domain-level or topic-level semantic roots built on this specification

This document defines:

Mandatory compliance requirements

Deterministic consequences of non-compliance

Failure modes at both domain and ecosystem scale

1. Hard Requirements (Compliance Contract)

To be considered DFH / Semantic Stack compliant, an implementation MUST satisfy all of the following.

1.1 Stack Descriptor Location

A valid DFH stack descriptor MUST be published at:

/.well-known/stack


The descriptor MUST be a valid JSON-LD document.

1.2 Required Anchors (Normative)

The top-level object MUST expose exactly the following five anchors, spelled exactly as shown:

{
  "type":      "…",
  "entity":    "…",
  "url":       "…",
  "sitemap":   "…",
  "canonical": "…"
}


Keys are case-sensitive

Anchors MUST be top-level

Anchors MUST NOT be renamed, aliased, or nested

If any required anchor is missing, renamed, or structurally altered, the stack is non-compliant.

1.3 Structural Stability

A compliant stack MUST maintain:

Stable key names

Stable document shape

Valid JSON-LD semantics

The stack MUST NOT:

Reorder anchors into nested objects

Introduce incompatible schema variations

Mix unrelated or conflicting semantic data

Determinism requires predictable structure.

1.4 Naming & Protocol Integrity

Implementations MUST NOT:

Rename DFH, the Semantic Stack, or the Five Anchors

Create “DFH-but-different” variants

Publish incompatible “v2” or alternative first-hop protocols under the DFH name

Forks are permitted only if they do not claim DFH compliance.

If you change the contract, you are no longer DFH-compliant.

2. Consequence Model (Protocol-Only)

There is no central authority, no enforcement body, and no punishment.

Compliance is enforced entirely through resolution and trust.

If a system cannot deterministically rely on your stack, it must ignore it.

2.1 Consequence Types
Local (Per-Domain)

Stack marked non-compliant by validators

DFH resolvers reject the descriptor

AI and search systems skip the domain for grounding

DFH-based topic authority and ranking advantages are lost

Network-Level (If Non-Compliance Is Widespread)

Deterministic first-hop resolution degrades

Conflicting interpretations emerge

AI systems revert to probabilistic guessing

The Semantic Stack is treated as noise rather than signal

3. Deterministic Rule-Break Outcomes
3.1 Renaming Anchors

Example violations

entity → id

type → kind

Result

Required anchors are missing

Validators mark the stack invalid

AI / search tools ignore the descriptor

Why

Anchor names are contract keys, not labels.
Change the keys → break the contract → lose determinism.

3.2 Omitting or Restructuring Anchors

Example violations

Removing sitemap

Nesting canonical

Publishing only partial anchors

Result

Shape becomes unpredictable

Multi-agent resolution disagrees

DFH systems downgrade or ignore the stack

Why

Determinism requires complete and stable shape.

3.3 Domain & TLD Alignment (Observed Web Reality)

Important clarification

DFH does not assign or mandate TLDs.

Instead, DFH inherits the authoritative domain conventions that already exist on the public web.

Observed reality:

.com dominates global commercial entities and generic topics

.org dominates institutions and nonprofits

.gov dominates government authorities

DFH records this reality — it does not redefine it.

Example

Claiming global topic authority for “Cars” on cars.xyz

Publishing topic.ai while topic.com is widely established

Result

DFH systems treat the domain as non-authoritative

Competing, convention-aligned domains are preferred

The claim fails silently

Why

Deterministic first-hop requires collision avoidance.
Ignoring existing web conventions introduces ambiguity and breaks resolution.

DFH does not ban other TLDs

DFH does not block innovation

DFH does not mandate .com

It simply reflects this rule:

The semantic root should live on the same domain that already represents the entity to the world.

3.4 Fragmenting the Pillars (Governance Rule)

The DFH ecosystem relies on stable, recognizable roots:

Concept root

Specification root

Installation guidance

Tooling and validators

If these are fragmented, renamed, or split into incompatible structures:

Tooling cannot reliably reference the standard

Implementers cannot identify the authoritative spec

Adoption confidence collapses

This is a governance requirement, not a wire-format rule.

3.5 Breaking JSON-LD Semantics

Violations

Removing required @context or @type

Invalid JSON-LD structure

Arbitrary semantic mixing

Result

Parsers fail

Graph resolution fails

Stack ignored

JSON-LD is the interoperability layer.
If it breaks, grounding breaks.

3.6 Forking the DFH Protocol

Violations

“DFH2” with incompatible anchors

Parallel first-hop standards claiming DFH lineage

Result

Ecosystem fragmentation

No single deterministic entry point

AI systems revert to probabilistic grounding

DFH is analogous to DNS: one shared system or none.

4. Failure Models
4.1 Local Failure

If only your domain violates the rules:

Your stack is ignored

You lose topic authority

Compliant competitors gain advantage

You harm only yourself.

4.2 Network Failure

If violations become widespread:

DFH loses trust

Vendors abandon deterministic grounding

The ecosystem collapses back to heuristic crawling

You harm the entire system.

5. Why the Rules Are Strict

DFH derives its power from:

Universality — one first-hop per topic

Determinism — same anchors, same shape

Simplicity — minimal surface area

Decentralization — anyone can publish, under one contract

Stability — shipped contracts do not drift

Changing the contract is not customization — it is exit.

6. Enforcement (How It Actually Happens)

There is no court, no appeals, no negotiation.

Enforcement occurs through code and consumption.

Validators

Mark non-compliance

Emit machine-readable errors

AI / Search Systems

Skip non-compliant stacks

Remove DFH-based authority signals

Ecosystem Tools

Exclude invalid roots from topic graphs

You are not punished.
You are simply not trusted.

7. Minimal Compliant Example
{
  "@context": "https://example.org/dfh/context",
  "@type": "DFHStackRoot",
  "type": "Topic",
  "entity": "Cars",
  "url": "https://cars.com/",
  "sitemap": "https://cars.com/sitemap.xml",
  "canonical": "https://cars.com/"
}


Any deviation in naming, structure, or domain alignment renders this non-compliant.

8. Validator Guidance (Non-Normative)

Example validation logic:

RULE 1: /.well-known/stack MUST exist and be valid JSON-LD
RULE 2: Required anchors MUST exist exactly as defined
RULE 3: Domain MUST align with established web conventions
RULE 4: No conflicting DFH variants may be present
RULE 5: Violations → status = non_compliant + reason code

9. Summary

Break naming → break determinism
Break determinism → break grounding
Break grounding → break authority

DFH works because the contract is strict.

You may do anything you want with your domain.
You may not break the contract and still call it DFH-compliant.
