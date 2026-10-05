# Mining incentives and economic acceptance

BSV.place / Project Babbage · Updated 2026-10-05
Canonical: https://bsv.place/guides/mining-incentives-and-economic-acceptance/
Evidence review: 2026-10-05; source-specific dates below.
Next review: 2026-11-05

Producing a block, checking it and accepting a payment are different decisions. Hashpower makes production possible and competing histories costly. Credible, coordinated rejection can reduce a profit-seeking attacker’s realizable payoff. That depends on actual enforcement, compatible settlement policies and continued accepted mining; one participant’s refusal cannot guarantee agreement.

Scope: Editorial synthesis of published rules, implementation documentation and the October 5 exchange. No current miner-control measurement, attack-resilience test or deployment audit was performed.

## Start with a merchant payment

Evidence kind: interpretation
Section: https://bsv.place/guides/mining-incentives-and-economic-acceptance/#three-jobs

A merchant hands over a product only after deciding that a payment meets its acceptance policy. A miner may include the transaction in a block. A verifier may check the transaction and relevant history. A payment service may do some of those checks for the merchant. These are related jobs, but the person doing one need not do all of them.

A non-mining validator therefore has a useful role: it can independently inspect the evidence and refuse to recognize a result. Its refusal contributes no hashpower and creates no replacement blocks. The merchant can also delegate checking to a wallet or payment service, gaining convenience while depending on that provider’s implementation, information and policy.

The relevant question is not just whether a block was produced. It is whether the businesses and services involved will treat its result as settling their obligations. Each participant’s choice matters within its own scope; neither the merchant nor the miner can unilaterally make every other participant agree.

Diagram: Different jobs in one settlement process

- Produce: Miners supply work and continuing blocks.
- Verify: Operators check rules and evidence themselves or through services.
- Accept: Businesses and users decide which result settles their exchange.
- Coordinate: Participants communicate and apply compatible policies.

Verification can justify local refusal. Successful convergence also requires compatible acceptance and continuing accepted block production.

Sources: [Bitcoin whitepaper · sections 5, 6 and 8](https://bitcoin.org/bitcoin.pdf); [Project Babbage’s answer on mining and economic acceptance](https://x.com/ProjectBabbage/status/2107167307097342049); [JS’s question about rejecting miners without mining](https://x.com/jionny112/status/2107129424135225455)

## Validity and competing histories are different questions

Evidence kind: documented
Section: https://bsv.place/guides/mining-incentives-and-economic-acceptance/#rules-and-histories

More work does not make a transaction pass a rule it violates. The original network description has nodes check blocks before accepting and extending them. But a conflict can also involve alternative histories whose individual transactions otherwise satisfy the relevant checks. Resolving that dispute requires a chain-selection and settlement policy; calling one participant dishonest supplies neither the policy nor its evidence.

Be explicit about which rules are being applied. Transaction validity, a software implementation’s protective behavior, and an institutionally issued directive are different inputs. A repeatable technical check does not by itself establish the legitimacy of an external decision. Readers should be able to identify the rule version, actor, evidence and decision being relied on.

Sources: [Bitcoin whitepaper · sections 5, 6 and 8](https://bitcoin.org/bitcoin.pdf); [Network Access Rules · Part III](https://docs.bsvblockchain.org/network-access-rules/network-access-rules/part-iii-enforcement-rules)

## What the BSV mechanisms establish

Evidence kind: documented
Section: https://bsv.place/guides/mining-incentives-and-economic-acceptance/#documented-mechanisms

SV Node’s Safe Mode documentation describes detection and protective behavior, together with operator intervention. It provides a basis for saying an operator can withhold acceptance locally. It does not establish that every service is running that software, that detection is infallible, or that all participants will choose the same response. Do not silently transfer an SV Node behavior to every Teranode installation.

The published Network Access Rules assign the Association directive functions, including specified block treatment under defined events. The alert system is a channel for signed information and directives. Authenticating a message helps establish its origin under the signing-key assumptions; it does not independently establish the truth of an allegation or make the response unanimous.

Those powers belong in the explanation, alongside operator and business decisions. Treating coordination as automatic hides operational risk. Treating every response as a purely informal choice hides the documented institutional layer. Both make it harder to evaluate what an actual settlement policy depends on.

Sources: [SV Node Safe Mode](https://docs.bsvblockchain.org/network-topology/nodes/sv-node/frequently-asked-questions/safe-mode); [Network Access Rules · Part III](https://docs.bsvblockchain.org/network-access-rules/network-access-rules/part-iii-enforcement-rules); [SV Node alert system](https://docs.bsvblockchain.org/network-topology/nodes/sv-node/alert-system)

## Why credible rejection can change incentives

Evidence kind: interpretation
Section: https://bsv.place/guides/mining-incentives-and-economic-acceptance/#economic-mechanism

A profit-seeking attack needs more than a history on disk: it needs a realizable benefit. Suppose an attacker’s intended gain depends on a merchant, exchange or other counterparty recognizing an attack branch. If those parties effectively reject the result, the intended payoff may disappear. If the target economy also refuses that branch’s mining rewards, producing additional work does not by itself make those rewards spendable there.

That is the affirmative deterrence argument. A credible response known in advance can make accepted mining more attractive than an attempted attack. The word credible carries substantial work: participants need usable rules, timely evidence, the ability to act, compatible policies and enough continuing accepted production to serve the economy they are protecting.

This does not imply an attack branch has zero value everywhere. Another economy could accept it. A position elsewhere, a political objective or a desire to cause disruption could also make an attack worthwhile to its sponsor. There is no verified estimate here of holdings, outside exposure, response probabilities or miner concentration from which to calculate a numerical safety margin.

The position is strongest as a conditional economic argument: effective rejection can remove a particular payoff, changing incentives. It is weaker when compressed into ‘attacks will always be orphaned’ or ‘hashpower no longer matters.’ Even when a defense prevents the intended theft, delayed service and disputed settlement can still hurt users.

Illustrative scenarios, not forecasts

| Conditions | Economic consequence | What remains |
| --- | --- | --- |
| Compatible policies; effective response; continuing accepted mining | The targeted payoff may be denied; accepted mining remains an alternative | Operational cost and disruption still need measurement |
| Services disagree or respond too slowly | Some counterparties may realize or recognize a conflicting result | Split settlement, loss and recovery risk |
| Sabotage or significant outside incentives | Foregone local rewards may not deter the sponsor | Sustained disruption and a need for an explicit service policy |

Sources: [Project Babbage’s answer on mining and economic acceptance](https://x.com/ProjectBabbage/status/2107167307097342049); [Bitcoin whitepaper · sections 5, 6 and 8](https://bitcoin.org/bitcoin.pdf)

## Local refusal is not network convergence

Evidence kind: interpretation
Section: https://bsv.place/guides/mining-incentives-and-economic-acceptance/#convergence

One business can refuse a payment without forcing another business to refuse it. One operator can reject a branch without forcing other operators to produce a replacement. Convergence means the participants whose agreement matters actually resume compatible settlement. It is an outcome to demonstrate, not a synonym for having a rejection mechanism.

During a disagreement, users need to know which operations are paused, what evidence is available, which counterparties share a policy and what unresolved obligations remain. A transparent incident record should include dissent and unsuccessful coordination, not only the eventual preferred result. If accepted block production stops, local conviction cannot supply the missing service.

Hashpower remains essential to production and the cost of competing histories. Economic acceptance explains what gives those histories relevance to particular transactions. Their interaction is the useful model; erasing either side makes the account less complete.

Sources: [Project Babbage’s answer on mining and economic acceptance](https://x.com/ProjectBabbage/status/2107167307097342049); [Bitcoin whitepaper · sections 5, 6 and 8](https://bitcoin.org/bitcoin.pdf)

## What the 2013 fork does and does not show

Evidence kind: documented
Section: https://bsv.place/guides/mining-incentives-and-economic-acceptance/#historical-comparison

BIP 50 records a chain split caused by incompatible software behavior. Coordination mattered: participants selected a compatible path and mining pools downgraded, moving hashpower. The incident also involved disruption and a documented double spend. It is evidence that software choices, human communication and mining all matter to the outcome.

It is not evidence that a minority’s refusal alone necessarily defeats a sustained majority, nor a blanket endorsement of BSV’s present governance. A historical analogy becomes useful when its differences are retained. Ask what changed the outcome in that incident, and what corresponding capability is actually available in the case now being considered.

Sources: [BIP 50 · March 2013 chain fork post-mortem](https://github.com/bitcoin/bips/blob/master/bip-0050.mediawiki)

## Make the acceptance policy inspectable

Evidence kind: proposed
Section: https://bsv.place/guides/mining-incentives-and-economic-acceptance/#acceptance-policy

Before a high-consequence workflow depends on settlement, document what will be accepted, who checks it and who can change that decision. The worksheet is a design and review aid; completing it is not certification. A low-value receipt and an irreversible high-value delivery can reasonably require different controls.

The accompanying incident template separates observations from reports and decisions. It helps preserve an explanation after a social conversation has disappeared, without publishing private logs, keys or operational details that users do not need. Use public references and sanitized evidence. An unknown is a legitimate result; an unrecorded assumption is much harder to challenge.

1. Name the workflow, value at risk and irreversible consequence.
2. Name the rules, implementation version, verifier and delegated providers.
3. Document accepted-history, delay and disagreement policies, including who authorizes changes.
4. Identify required coordination and continuing production; record untested assumptions.
5. Retain the public evidence, decisions, affected outcomes and unresolved disagreements.

Sources: [SV Node Safe Mode](https://docs.bsvblockchain.org/network-topology/nodes/sv-node/frequently-asked-questions/safe-mode); [Network Access Rules · Part III](https://docs.bsvblockchain.org/network-access-rules/network-access-rules/part-iii-enforcement-rules); [Project Babbage’s answer on mining and economic acceptance](https://x.com/ProjectBabbage/status/2107167307097342049)

## What would change this assessment?

Observed coordination failures, inconsistent acceptance or inability to sustain accepted production weaken the deterrence case. Transparent incident outcomes and independent review can strengthen confidence. Neither establishes an unconditional guarantee.

## Sources and provenance

- [Bitcoin whitepaper · sections 5, 6 and 8](https://bitcoin.org/bitcoin.pdf) · documented · Access 2026-10-05. The original network, incentive and verification model. It does not document later BSV institutions.
- [SV Node Safe Mode](https://docs.bsvblockchain.org/network-topology/nodes/sv-node/frequently-asked-questions/safe-mode) · documented · Access 2026-10-05. Documents protective detection and operator intervention for SV Node. Not a deployment or convergence test.
- [Network Access Rules · Part III](https://docs.bsvblockchain.org/network-access-rules/network-access-rules/part-iii-enforcement-rules) · documented · Access 2026-10-05. Published Association directive powers and event categories. Read the operative text for scope and conditions.
- [SV Node alert system](https://docs.bsvblockchain.org/network-topology/nodes/sv-node/alert-system) · documented · Access 2026-10-05. Documents signed information and directive messages. Message authentication is not a judgment on the merits, and documentation is not a deployment audit.
- [Project Babbage’s answer on mining and economic acceptance](https://x.com/ProjectBabbage/status/2107167307097342049) · reported · Access 2026-10-05 · Published 2026-10-05T17:53:29Z. The published argument that prompted this guide, verified against its live body. An authored position, not empirical proof of deterrence.
- [JS’s question about rejecting miners without mining](https://x.com/jionny112/status/2107129424135225455) · reported · Access 2026-10-05 · Published 2026-10-05T15:22:57Z. The direct question answered by the October 5 reply. The guide answers the substance independently of access to X.
- [BIP 50 · March 2013 chain fork post-mortem](https://github.com/bitcoin/bips/blob/master/bip-0050.mediawiki) · documented · Access 2026-10-05. Records software incompatibility, coordinated downgrade and movement of mining hashpower, disruption and a double spend.

## Related resources

- [Stewardship and authority](https://bsv.place/guides/stewardship-and-authority/): Identify who is empowered to decide and how a decision can be challenged.
- [Hashpower and reorganizations](https://bsv.place/answers/security-hashpower-and-reorgs/): Put the mechanism alongside the settlement risks.
- [Proof and preservation](https://bsv.place/proof/merkle-proof-not-backup/): Distinguish retained inclusion evidence from current accepted history.
