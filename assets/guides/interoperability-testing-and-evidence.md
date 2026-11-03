# Interoperability testing and evidence

BSV.place / Project Babbage · Updated 2026-11-02
Canonical: https://bsv.place/guides/interoperability-testing-and-evidence/
Evidence review: 2026-11-02; source-specific dates below.
Next review: 2026-12-02

A shared interface makes independently built components testable against the same contract. TPNIL adds versioned environments, program requirements, exact artifacts and retained evidence. Its first experimental wallet result has passing, failing and blocked assertions. Compatibility is established only for the tested workflow, versions and profile; broader conformance, portability and certification require separate evidence.

Scope: Editorial review of public TPNIL documentation at revision 8782a6c and the published launch thread. P2PPSR operates the laboratory and shares maintainer interests with Project Babbage. Retained-result descriptions were reviewed; no independent original-system rerun was performed.

## Give the compatibility claim a boundary

Evidence kind: documented
Section: https://bsv.place/guides/interoperability-testing-and-evidence/#test-the-handoffs

A wallet may expose the expected method while an application still fails to complete its task. Arguments, permission choices, transaction state, storage, lookup and recovery all contribute to the result. A useful test follows those handoffs and records the versions and configuration that produced the outcome.

The Transaction Processing Network Interoperability Laboratory (TPNIL) supplies a common framework. ITCVE-1 is its first Integrated Testing and Conformance Validation Environment. An ISI is an Interoperability and Standardization Initiative defining what to evaluate. The System Under Test (SUT) is the exact artifact occupying a selected role.

Diagram: From an integration claim to inspectable evidence

- Pin: Identify the program, environment, software artifacts, dependencies, fixtures and intended outcome.
- Execute: Drive the declared public interfaces in an isolated environment and retain permission decisions and raw observations.
- Evaluate: Apply versioned independent expected outcomes. Preserve passes, failures, blockers and inconclusive attempts.
- Reproduce: Verify retained evidence, replay the evaluation, then separately reconstruct and rerun the original systems.

A result applies to its declared profile and artifacts. A self-test, infrastructure qualification and SUT conformance result establish different things.

Sources: [Laboratory architecture](https://github.com/p2ppsr/interop/blob/main/docs/architecture.md); [Published Project Babbage launch thread](https://x.com/ProjectBabbage/status/2117403408961573040)

## Choose the program that matches the question

Evidence kind: documented
Section: https://bsv.place/guides/interoperability-testing-and-evidence/#four-programs

ISI-1 addresses the complete transaction-processing application. Its reference and joined Broadcaster/Teranode/Merkle service qualifications are retained; the complete browser application and external-wallet SUT run remain pending.

ISI-2 targets overlay submission, lookup and synchronization, including duplicate handling, interrupted sync and expected topical state. Its external-SUT vectors remain draft. ISI-3 targets remote wallet storage through a multi-remote wallet; direct database copying bypasses that boundary. Its HTTP driver and independent state oracle remain unfinished.

ISI-4 exercises a production wallet and application through supported interfaces, with explicit controlled services and fixtures. Its ToDo sequence covers initialization and funding, encrypted task creation, cold reload and reconstruction, and redemption. Additional assertions cover permissions, transaction lifecycle, portability and comprehensive method coverage.

Sources: [Versioned ISI program register](https://github.com/p2ppsr/interop/blob/main/programs/README.md); [Implementation status and retained-result descriptions](https://github.com/p2ppsr/interop/blob/main/docs/implementation-status.md)

## Substitute a component without changing the question

Evidence kind: documented
Section: https://bsv.place/guides/interoperability-testing-and-evidence/#component-substitution

An implementation can replace a declared role while all supporting roles remain pinned. In another run, that implementation can become a supporting dependency while a different component is evaluated. Each matrix cell identifies the exact combination; success in one cell does not establish success in unexecuted combinations.

The adapter describes, verifies, installs, configures, initializes, funds, readies, drives, observes, resets and stops the component. It returns observations; the evaluator determines the verdict. The adapter preserves the original interface semantics and native permission choices.

A proposed overlay example submits a synthetic record, checks lookup, repeats the submission, interrupts sync, restarts and compares the recovered state to an independent expected projection. This is a test plan. An actual result requires an admitted artifact, qualified driver, executed vectors and retained evidence.

Sources: [Laboratory architecture](https://github.com/p2ppsr/interop/blob/main/docs/architecture.md); [Common adapter contract](https://github.com/p2ppsr/interop/blob/main/adapters/README.md)

## Read the first wallet results precisely

Evidence kind: documented
Section: https://bsv.place/guides/interoperability-testing-and-evidence/#first-wallet-results

The retained Yours Wallet 5.1.0 record describes two clean runs with matching semantic outcomes. V001–V004 pass; V005–V006 fail; V007–V008 are blocked. The passing ToDo sequence does not override the other outcomes.

Metanet Explorer 1.1.10 has four Android observations reaching activation, controlled funding, UMP publication and ToDo transaction submission, followed by an unresolved wallet-response and task-visibility boundary. BSV Browser has engineering evidence from a source candidate pending a publisher binary; BSV Desktop has native intake/bridge qualification with service configuration and fixture prerequisites remaining.

These are different evidence states. A candidate listing is not admission, an intake check is not complete conformance, and an experimental result is not certification. The laboratory is a related project, not independent corroboration by an unrelated reviewer.

Yours Wallet 5.1.0: retained experimental outcomes, reviewed November 2

| Assertions | Recorded outcome | Meaning |
| --- | --- | --- |
| V001–V004 | PASS | Initialization/funding, encrypted task creation, cold reload and redemption in the declared controlled profile. |
| V005–V006 | FAIL | Permissions/communications and transaction-lifecycle criteria were not met. |
| V007–V008 | BLOCKED | Storage replacement and comprehensive wallet coverage lack required prerequisites. |

Sources: [Implementation status and retained-result descriptions](https://github.com/p2ppsr/interop/blob/main/docs/implementation-status.md)

## Keep the test network boundary visible

Evidence kind: documented
Section: https://bsv.place/guides/interoperability-testing-and-evidence/#network-boundary

ISI-1 through ISI-3 select the ITCVE-1 0.1.0 regtest design. ISI-4 selects the 1.0.0 production-wallet controlled-service profile. Mainnet configuration in a production wallet does not mean fixtures were accepted by the public mainnet or have economic value.

The fixture state, funding ancestry, observed endpoints, dependency digests and clean reset procedure belong in the record. These tests do not establish broader adoption, settlement finality, complete recovery or the removal of rail-specific dependencies.

Sources: [Versioned ISI program register](https://github.com/p2ppsr/interop/blob/main/programs/README.md); [Implementation status and retained-result descriptions](https://github.com/p2ppsr/interop/blob/main/docs/implementation-status.md)

## Record a result someone else can inspect

Evidence kind: documented
Section: https://bsv.place/guides/interoperability-testing-and-evidence/#result-checklist

Use the downloadable empty run record and matrix to turn a compatibility assertion into a reviewable claim. Leave unknown values unknown. The assets are proposed templates, not observed tests.

1. Identify the exact app, wallet or service artifact and digest, platform and configuration.
2. Name the program/version, environment profile, vector IDs and independent expected outcome.
3. Record controlled dependencies, origins, fixtures, funding and permission decisions.
4. Retain raw observations and the source/evaluator revisions; identify every attempted matrix cell.
5. Report PASS, FAIL, BLOCKED or INCONCLUSIVE with its actual reason and evidence references.
6. Compare two clean repetitions using the declared semantic projection. Keep exact randomized bytes in each run.
7. Distinguish verifying/replaying retained evidence from rerunning original systems under independent operation.

Sources: [Operator quickstart](https://github.com/p2ppsr/interop/blob/main/docs/operator-quickstart.md); [Common adapter contract](https://github.com/p2ppsr/interop/blob/main/adapters/README.md)

## Begin with an offline self-test

Evidence kind: documented
Section: https://bsv.place/guides/interoperability-testing-and-evidence/#first-example

The offline core demo creates a synthetic LAB_SELF_TEST_ONLY result. Verification checks the retained bundle, while replay evaluates the stored observations. Neither action executes an external wallet or establishes complete SUT conformance.

The Metanet.fyi example gives the current command sequence and explains when native artifacts and controlled services become necessary. The repository quickstart remains authoritative for commands and prerequisites.

Sources: [Operator quickstart](https://github.com/p2ppsr/interop/blob/main/docs/operator-quickstart.md)

## Contribute the missing evidence

Evidence kind: documented
Section: https://bsv.place/guides/interoperability-testing-and-evidence/#remaining-work

The next work includes complete application execution, independent overlay and storage substitutions, broader wallet/platform coverage, permission and recovery cases, and independent reconstruction. Formal certification requires separately published criteria and review.

A useful contribution names an ISI and role: provide an adapter, a clause-level fixture, an independent expected-state check, a reproducible failure, or a clean-environment rerun. Publish only intentionally public synthetic records and follow the affected project’s security-reporting path for sensitive defects.

Sources: [Remaining work](https://github.com/p2ppsr/interop/blob/main/ROADMAP.md)

## What would change this assessment?

Independent original-system repetitions, additional admitted implementations, completed overlay/storage replacement matrices and broader clause-level coverage would strengthen specific compatibility claims. Divergent clean repetitions, missing artifacts or unexplained permission and state differences would weaken them. Retained failures and blockers remain part of the record.

## Sources and provenance

- [Laboratory architecture](https://github.com/p2ppsr/interop/blob/main/docs/architecture.md) · documented · Access 2026-11-02. Versioned primary laboratory documentation; inspect the executed scope and current status.
- [Versioned ISI program register](https://github.com/p2ppsr/interop/blob/main/programs/README.md) · documented · Access 2026-11-02. Versioned primary laboratory documentation; inspect the executed scope and current status.
- [Implementation status and retained-result descriptions](https://github.com/p2ppsr/interop/blob/main/docs/implementation-status.md) · documented · Access 2026-11-02. Source-reported experimental results reviewed at revision 8782a6c. No independent SUT rerun was performed for this article.
- [Common adapter contract](https://github.com/p2ppsr/interop/blob/main/adapters/README.md) · documented · Access 2026-11-02. Versioned primary laboratory documentation; inspect the executed scope and current status.
- [Operator quickstart](https://github.com/p2ppsr/interop/blob/main/docs/operator-quickstart.md) · documented · Access 2026-11-02. Versioned primary laboratory documentation; inspect the executed scope and current status.
- [Remaining work](https://github.com/p2ppsr/interop/blob/main/ROADMAP.md) · documented · Access 2026-11-02. Versioned primary laboratory documentation; inspect the executed scope and current status.
- [Published Project Babbage launch thread](https://x.com/ProjectBabbage/status/2117403408961573040) · reported · Access 2026-11-02 · Published 2026-11-02T23:48:06Z. Launch and six continuations verified live. Owned announcement with shared P2PPSR/Babbage interests; not independent validation.

## Related resources

- [Understand the environment](https://metanet.fyi/interoperability): Visual architecture, programs and profiles.
- [Plan an integration](https://metanet.fyi/interoperability/integrate): Role selection, artifact intake and a proposed substitution example.
- [Try the offline example](https://metanet.fyi/interoperability/examples): Self-test and evidence verification without a live wallet.
- [Wallet compatibility and safe changes](https://bsv.place/guides/wallet-compatibility-and-safe-changes/): The interface, policy and workflow distinction in a dated support case.
- [BRC-100 testing](https://brc100.org/#testing): Developer entry point and primary implementation references.
