# Stewardship and authority in an open system

BSV.place / Project Babbage · Updated 2026-10-05
Canonical: https://bsv.place/guides/stewardship-and-authority/
Evidence review: 2026-10-05; source-specific dates below.
Next review: 2026-11-05

A shared system needs maintainers and coordination. Those responsibilities can be distributed across institutions with different scopes. The useful test is whether another competent participant can understand the rules, inspect a decision and continue the relevant work. BSV’s published Association powers remain real dependencies; plural stewardship is a standard to demonstrate, not evidence that concentration has disappeared.

Scope: BRC-187 is an authored framework, read alongside published operational rules. This article is not an independent control audit or a legal opinion about replacement rights.

## Three responsibilities that make stewardship useful

Evidence kind: interpretation
Section: https://bsv.place/guides/stewardship-and-authority/#three-responsibilities

Maintaining a shared system is work. Someone must preserve the rules, implement them, explain their application and repair mistakes. Denying that work exists does not remove power; it can make the people doing it less visible. The constructive question is how responsibilities can be bounded, checked and continued by others.

BRC-187, an opinion authored by Ty Everett, supplies a framework for this discussion. We interpret its practical demands as transferable competence, correction within institutions, and cooperation among independent stewards. Because this site is maintained by Project Babbage, the related authorship is material. The essay explains a position; it is not outside verification that BSV already meets it.

Diagram: Three tests of a stewardship arrangement

- Transfer competence: Another qualified participant can understand the work and its evidence.
- Correct institutions: A mistake can be acknowledged, challenged and repaired.
- Cooperate independently: Different stewards can coordinate within explicit scopes.

Evidence of these capabilities must accompany the principle. A commitment alone does not demonstrate replaceability.

Sources: [BRC-187 · stewardship opinion](https://github.com/bsv-blockchain/BRCs/blob/7c0ba5f2208e06525303ad4ac429dcbf379229d4/opinions/0187.md)

## Can another competent person continue the work?

Evidence kind: proposed
Section: https://bsv.place/guides/stewardship-and-authority/#transferable-competence

For a software maintainer, this means more than publishing a repository. A successor needs build instructions, tests, release provenance, supported behavior and an intelligible account of design choices. A public interface helps separate applications from a particular implementation, but compatibility and licensing still determine whether a substitute is practical.

For a service, continuity also requires usable data. A replacement overlay cannot reconstruct absent records from a name or endpoint. The records, schema, indexing rules and authorization model must be available to the party that needs them. A documented export becomes much stronger evidence after a restore in an independent environment.

Transferable competence is therefore a useful affirmative goal: preserve enough knowledge for another responsible person to act. It does not imply that all production infrastructure must be public, that every operator shares private data, or that a formally assigned institutional authority can be replaced simply by copying its software.

Sources: [BRC-187 · stewardship opinion](https://github.com/bsv-blockchain/BRCs/blob/7c0ba5f2208e06525303ad4ac429dcbf379229d4/opinions/0187.md); [BRC-100 · wallet to application interface](https://bsv.brc.dev/wallet/0100)

## Can an institution correct itself?

Evidence kind: proposed
Section: https://bsv.place/guides/stewardship-and-authority/#correctable-institutions

A correction path needs an accountable owner, a way to supply evidence, a record of the decision and a means to revisit it. It should work when the challenger is unfamiliar or critical. A formal complaint channel with no observable handling history provides less assurance than a process whose corrections can actually be inspected.

Scope matters. A maintainer can correct code or documentation without determining a legal dispute. A business can change a payment policy without rewriting a standard for everyone. A coordinator can communicate evidence without making the communication itself proof of the evidence. An explanation should name the act and the authority for it rather than group everything under ‘governance.’

Apply this standard to our own work. A mistake in a supportive argument deserves the same correction as a mistake in a criticism. The October mining guide consequently preserves the acceptance mechanism while retiring the inference that rejection must always succeed. Correctability makes a position more reliable because readers can see what survives scrutiny.

Sources: [BRC-187 · stewardship opinion](https://github.com/bsv-blockchain/BRCs/blob/7c0ba5f2208e06525303ad4ac429dcbf379229d4/opinions/0187.md); [Project Babbage’s answer on mining and economic acceptance](https://x.com/ProjectBabbage/status/2107167307097342049)

## Identify the system apart from its custodian

Evidence kind: interpretation
Section: https://bsv.place/guides/stewardship-and-authority/#rules-and-custodians

The strongest part of the stewardship argument is that a rule can be stated independently of the person applying it. Two competent stewards using the same complete rules and relevant evidence should obtain the same validation result. Where the selection conditions uniquely determine a history, they should also identify the same resulting state. The premises must be exposed: different evidence, incomplete rules or unresolved selection conditions can prevent that conclusion.

This makes replacement without redesign conceivable. A new maintainer can preserve an interface; another service can apply an existing application rule. Responsibility for maintaining a system does not, by itself, justify changing its underlying undertaking. BSV’s stated preference for a stable core is a stewardship commitment to examine against actual rules and conduct, not a license to skip that examination.

For example, two warehouse-receipt services could recognize the same issuers, use the same admission rules and inspect the same available evidence. They could produce compatible results without one owning all interpretation. They still need sufficient records, consistent implementations and an explicit way to handle missing or conflicting evidence. A public query interface alone would not prove those conditions.

If the complete rule set includes an external directive, both stewards must identify that input. Reproducing its technical consequences is different from independently justifying the directive. Plural stewardship is strongest when this dependency is visible, rather than concealed inside the word ‘objective.’

Sources: [BRC-187 · stewardship opinion](https://github.com/bsv-blockchain/BRCs/blob/7c0ba5f2208e06525303ad4ac429dcbf379229d4/opinions/0187.md); [Network Access Rules · Part III](https://docs.bsvblockchain.org/network-access-rules/network-access-rules/part-iii-enforcement-rules)

## Keep current powers separate from desired safeguards

Evidence kind: documented
Section: https://bsv.place/guides/stewardship-and-authority/#authority-matrix

The following matrix separates documented roles from the evidence still needed to assess their operation. It is a starting map, not a complete audit of the ecosystem. In particular, an external directive remains an input: reproducing its technical effect differs from independently deriving or endorsing the decision.

The Network Access Rules describe Association functions that cannot be erased by calling the ecosystem plural. The framework proposed here asks for clearer boundaries and accountability around such power. It does not amend the operative rules, establish an appeal outcome or confer a legal right to replace an assigned authority.

Authority and dependency matrix · documented roles; proposed checks

| Role | Current scope and input | Inspectable output | Challenge or replacement question | Evidence state |
| --- | --- | --- | --- | --- |
| Association directive function | Published Part III event and directive provisions; external decisions may be inputs | Specified instruction and its declared basis | Use applicable dispute process; technical substitution alone does not establish authority | Rules documented; complete operation audit not supplied |
| Node operator | Implementation, accepted rules and relevant directive inputs | Locally applied policy and resulting accepted history | Can another operator reproduce the technical treatment? | SV Node documentation; deployment and convergence untested |
| Wallet implementer | Interface, permission policy and user key operations | Versioned behavior, prompts and safe workflow results | Can an independent wallet support the required behavior and migration? | Interface documented; end-to-end compatibility must be tested |
| Application or overlay operator | Application schema, retained records and service policy | Usable exports and verifiable application results | Can another service interpret, restore and serve the required records? | Design requirement; product-specific evidence needed |
| Business accepting payment | Workflow risk, verifier/service evidence and counterparties | Published acceptance and dispute policy | Who can revise it, and who must agree for settlement? | Proposed accountability record; no universal merchant policy |

Sources: [Network Access Rules · Part III](https://docs.bsvblockchain.org/network-access-rules/network-access-rules/part-iii-enforcement-rules); [SV Node alert system](https://docs.bsvblockchain.org/network-topology/nodes/sv-node/alert-system); [BRC-100 · wallet to application interface](https://bsv.brc.dev/wallet/0100); [BRC-187 · stewardship opinion](https://github.com/bsv-blockchain/BRCs/blob/7c0ba5f2208e06525303ad4ac429dcbf379229d4/opinions/0187.md)

## A disagreement between two operators

Evidence kind: interpretation
Section: https://bsv.place/guides/stewardship-and-authority/#worked-disagreement

Consider two operators reaching different conclusions about the same event. First they compare the actual inputs: transaction or record, rule version, implementation version and any external instruction. If their inputs differ, the useful work is to identify the difference. If the same input produces different technical results, a reproducible implementation discrepancy may explain it.

If they agree on the technical effect but disagree about an instruction’s legitimacy, rerunning the same code will not resolve that disagreement. They need the applicable authority and challenge process, and an account of what services do while the disagreement persists. A signed message establishes an attributed instruction, subject to key assumptions; it does not resolve the merits by itself.

Independent stewards cooperate by making these boundaries legible. Agreement can be an outcome of shared rules and evidence, but agreement with our preferred conclusion cannot be the definition of honesty. An unresolved disagreement must remain visible. The miner, wallet, business and user may also face different immediate consequences.

1. Compare inputs and rule versions.
2. Compare the technical result.
3. Separate implementation differences from disputes over authority or judgment.
4. Use the relevant challenge process and record interim service policy.
5. Publish the reasoned outcome, remaining dissent and resulting correction where appropriate.

Sources: [BRC-187 · stewardship opinion](https://github.com/bsv-blockchain/BRCs/blob/7c0ba5f2208e06525303ad4ac429dcbf379229d4/opinions/0187.md); [Network Access Rules · Part III](https://docs.bsvblockchain.org/network-access-rules/network-access-rules/part-iii-enforcement-rules); [SV Node alert system](https://docs.bsvblockchain.org/network-topology/nodes/sv-node/alert-system)

## Make a responsibility statement portable

Evidence kind: proposed
Section: https://bsv.place/guides/stewardship-and-authority/#responsibility-record

Every critical dependency should have a short responsibility statement: what it controls, why, who can change it, what evidence it exposes and what continuity requires. The downloadable template also asks who handles a challenge and what has actually been tested. These questions are useful for an independent builder as well as a large institution.

Do not infer independence from separate names alone. Shared hosting, funding, administrators, licenses or signing keys may constrain real choices. Equally, institutional concentration is not proof that every independent builder is controlled by one sponsor. Record supported relationships and unknowns rather than making either sweeping assertion.

The strongest argument for plural stewardship is a demonstrated ability to preserve competence, correct errors and cooperate across independent scopes. It improves as replacement and challenge paths become practical. It weakens when undocumented discretion expands, important records disappear or a supposed alternative cannot perform the promised job.

Sources: [BRC-187 · stewardship opinion](https://github.com/bsv-blockchain/BRCs/blob/7c0ba5f2208e06525303ad4ac429dcbf379229d4/opinions/0187.md)

## What would change this assessment?

Independent continuation, reproducible decisions and meaningful correction histories strengthen the framework’s practical case. Opaque discretion, unavailable evidence or unusable replacement paths weaken it. The framework never substitutes for the actual authority record.

## Sources and provenance

- [BRC-187 · stewardship opinion](https://github.com/bsv-blockchain/BRCs/blob/7c0ba5f2208e06525303ad4ac429dcbf379229d4/opinions/0187.md) · interpretation · Access 2026-10-05. Ty Everett’s authored stewardship framework. BSV.place is maintained by Project Babbage; this is a related author’s position, not independent corroboration or a deployed governance specification.
- [Network Access Rules · Part III](https://docs.bsvblockchain.org/network-access-rules/network-access-rules/part-iii-enforcement-rules) · documented · Access 2026-10-05. Published Association directive powers and event categories. Read the operative text for scope and conditions.
- [SV Node alert system](https://docs.bsvblockchain.org/network-topology/nodes/sv-node/alert-system) · documented · Access 2026-10-05. Documents signed information and directive messages. Message authentication is not a judgment on the merits, and documentation is not a deployment audit.
- [SV Node Safe Mode](https://docs.bsvblockchain.org/network-topology/nodes/sv-node/frequently-asked-questions/safe-mode) · documented · Access 2026-10-05. Documents protective detection and operator intervention for SV Node. Not a deployment or convergence test.
- [BRC-100 · wallet to application interface](https://bsv.brc.dev/wallet/0100) · documented · Access 2026-10-05. The interface specification; implementation, policy and workflow outcomes need their own evidence. No new compatibility test is implied by this guide.
- [Project Babbage’s answer on mining and economic acceptance](https://x.com/ProjectBabbage/status/2107167307097342049) · reported · Access 2026-10-05 · Published 2026-10-05T17:53:29Z. The published argument that prompted this guide, verified against its live body. An authored position, not empirical proof of deterrence.

## Related resources

- [Mining and economic acceptance](https://bsv.place/guides/mining-incentives-and-economic-acceptance/): See how authority and coordination enter settlement.
- [Association governance](https://bsv.place/answers/bsv-association-governance/): Inspect the formal institutional layer.
- [Metanet overlay recovery](https://metanet.fyi/overlays/recovery): Turn service replaceability into a recovery checklist.
