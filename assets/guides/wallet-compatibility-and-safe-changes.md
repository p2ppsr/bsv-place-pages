# When a conforming wallet still breaks an application

BSV.place / Project Babbage · Updated 2026-11-02
Canonical: https://bsv.place/guides/wallet-compatibility-and-safe-changes/
Evidence review: 2026-11-02; source-specific dates below.
Next review: 2026-12-02

A common wallet interface gives applications a shared way to request operations. It does not guarantee that every wallet policy, version and user workflow works together. The October 4 Zanaadu report exposed that gap. Later maintainer-reported simulator success and Browser 1.8.0 release evidence show repair follow-through; independent current-release and reporter-confirmed full workflow completion remain unestablished here.

Scope: October 4 reports are retained alongside public October 6/21 repair and release evidence, reviewed November 2. The later successful simulator-development-build report is attributed; independent current-release reproduction and reporter-confirmed completion remain unestablished.

## The affirmative case for a common interface

Evidence kind: interpretation
Section: https://bsv.place/guides/wallet-compatibility-and-safe-changes/#why-the-interface-matters

A wallet interface lets an application request actions without implementing every wallet’s private API. It can make user permissions more consistent, allow reusable test vectors and make alternative implementations easier to compare. That shared boundary is valuable precisely because the wallet and application are different components with different responsibilities.

The user still needs the complete task to work. An operation may exist in the interface while an implementation rejects a particular request, asks for an unexpected permission or returns behavior the application cannot handle. A passing test only establishes the behavior covered by that test under its recorded conditions. It does not certify all combinations of wallet, app, platform and version.

Sources: [BRC-100 · wallet to application interface](https://bsv.brc.dev/wallet/0100)

## What the October 4 exchange establishes

Evidence kind: reported
Section: https://bsv.place/guides/wallet-compatibility-and-safe-changes/#the-public-record

A Zanaadu user reported a broken mobile posting workflow and an unexpected signing restriction. A maintainer subsequently described an overly restrictive change, acknowledged missing prompt and release communication, and said the interface check had passed. Project Babbage accepted a code-quality and testing gap. The reporter’s later constructive response is useful context, but it is not a verification of repair.

These October 4 reports alone do not identify a repaired release or independently reproduced outcome. They remain the historical starting point; the subsequent repair and release evidence is recorded in the next section.

Historical evidence state at October 5; subsequent release evidence follows

| Item | State | What remains |
| --- | --- | --- |
| Mobile posting failure | User-reported | Exact app/wallet builds and a safe independent reproduction |
| Overly restrictive change and communication gap | Maintainer-reported | Release-specific implementation evidence |
| Interface test pass | Maintainer-reported | Published test coverage for the affected workflow |
| Repair and successful user workflow | Not verified | Named release, retest conditions, outcome and preferably reporter confirmation |

Sources: [Zanaadu mobile workflow report](https://x.com/johncalhooon/status/2106787458138378251); [Maintainer’s explanation and acknowledgment](https://x.com/deggen/status/2106810017915580802); [Project Babbage’s acknowledgment of the testing gap](https://x.com/ProjectBabbage/status/2106822131413872713); [Reporter’s constructive follow-up](https://x.com/johncalhooon/status/2106824255992451579)

## Later repair evidence: what changed

Evidence kind: reported
Section: https://bsv.place/guides/wallet-compatibility-and-safe-changes/#later-repair-evidence

Browser PR #159, merged October 6, replaces the restrictive signing policy and reports a successful Zanaadu post on an iOS simulator development build. The maintainer explicitly says that run preceded final changes. Browser 1.8.0, published October 21, includes PR #159.

This establishes a published implementation change and attributed development-build success. It does not establish independent current-release reproduction, reporter-confirmed full TestFlight click-through or universal wallet compatibility. The October 4 failure should not be repeated as proof that no repair was released.

Sources: [Browser PR #159 signing-policy repair](https://github.com/bsv-blockchain/bsv-browser/pull/159); [Browser 1.8.0 public release](https://github.com/bsv-blockchain/bsv-browser/releases/tag/v1.8.0)

## Upgrade and spending policies need their own evidence

Evidence kind: reported
Section: https://bsv.place/guides/wallet-compatibility-and-safe-changes/#migration-and-permissions

Desktop v3.1.1’s migration notice distinguishes phrase/key wallets from WAB phone/password login, tells WAB users to remain on v2, identifies removed built-in STAS support and warns that separate wallet record stores can diverge when the same keys are shared. Check the specific login, records and asset path before an upgrade; a newer version number does not establish a safe migration for every user.

A separate Desktop spending-limit report has different evidence. PR #100 reports enforcement repairs in Wallet Toolbox 2.14.0/Desktop ≥2.9.6 and a display/cache fix released 2.9.8. Issue 93 remains open. No independent original-task enforcement retest was established by this editorial review. Do not conflate that case with the Zanaadu signing-policy case.

The TypeScript conformance corpus also distinguishes structural fixture checks from behavior execution. A root conformance validation pass does not certify a complete wallet workflow.

Sources: [Desktop v3.1.1 migration notice](https://github.com/bsv-blockchain/bsv-desktop/releases/tag/v3.1.1); [Desktop PR #100 spending enforcement and display status](https://github.com/bsv-blockchain/bsv-desktop/pull/100); [TypeScript conformance runner scope](https://github.com/bsv-blockchain/ts-stack/blob/main/docs/conformance/runner-ts.md)

## Four layers to inspect before assigning the fix

Evidence kind: interpretation
Section: https://bsv.place/guides/wallet-compatibility-and-safe-changes/#four-layers

The specification defines what a request means and which behavior is promised. Wallet policy defines permission and risk decisions inside that boundary. The implementation carries those decisions out. The application then composes operations into a user workflow, including its handling of denials, errors and changes.

Calling a problem an implementation issue can help assign work, but should not end the investigation. A standard may leave important semantics ambiguous. A policy change may be legitimate yet poorly communicated. An application may rely on undocumented behavior. More than one of these can be true at once. The useful result is a precise supported behavior and a tested path forward.

A compatibility matrix should therefore name app, wallet, versions, platform, workflow, expectation, observed result, date and tester. Distinguish pass, fail and not tested. Keep a reported failure separate from an independently reproduced failure; otherwise the table silently upgrades the evidence.

Diagram: From an interface to a usable product

- Specification: What operation and semantics are promised?
- Policy: What permission or restriction applies?
- Implementation: What does this version actually do?
- Workflow: Can this user complete the intended task?

A pass at one layer is evidence about that layer. Record the complete workflow separately.

Sources: [BRC-100 · wallet to application interface](https://bsv.brc.dev/wallet/0100); [Maintainer’s explanation and acknowledgment](https://x.com/deggen/status/2106810017915580802)

## Public compatibility support and security reporting

Evidence kind: proposed
Section: https://bsv.place/guides/wallet-compatibility-and-safe-changes/#safe-reporting

Ordinary compatibility questions benefit from public symptoms, supported behavior, release notes and migration instructions. Developers should not need a private relationship to learn that a supported operation changed. A public report can be constructive even when its first explanation of the cause turns out to be incomplete.

If a report includes a suspected exploitable weakness, use the affected project’s designated confidential reporting process for sensitive details. A safe public status can still explain affected functionality, mitigations that do not create new risk, supported versions and where updates will appear. Do not publish credentials, private records or exploit instructions in a compatibility ticket.

The TypeScript stack has a public security policy. That fact establishes a reporting route, not an independent audit or a paid bounty promise. It also does not establish that any existing advisory describes this particular incident. Match identifiers and affected versions before linking an advisory as its resolution.

1. Ordinary unexpected behavior: provide safe symptoms, versions, expected behavior and a public issue or support route.
2. Potential exploitable weakness: send sensitive detail through the project’s designated process; keep public updates safe and useful.
3. Unclear category: ask the maintainer to route it without requiring secrets or a public reproduction of a weakness.
4. Resolution: name the release and retest the original user task before marking it fixed.

Sources: [TypeScript stack security policy](https://github.com/bsv-blockchain/ts-stack/security)

## Communicate a behavior change before users discover it

Evidence kind: proposed
Section: https://bsv.place/guides/wallet-compatibility-and-safe-changes/#change-notices

A useful change notice states what changed, who is affected, which versions contain it and what applications should do. If a restriction changes, describe the user-visible behavior and supported migration path. Do not turn a security improvement into an undocumented compatibility surprise when safe advance communication is possible.

The notice should also distinguish intentional behavior from a regression and identify the owner of follow-through. An apology or acknowledgment matters, but users still need a release and a working task. Preserve failed tests and unexpected results as part of the record; they explain why a later claim of compatibility is credible.

For maintainers, shared interface tests and application workflow tests serve different purposes. Add coverage for the behavior that mattered to the user, including ordinary denial and recovery behavior, while keeping security-sensitive investigation in the appropriate process. A versioned result is more useful than a general badge saying ‘compatible.’

Sources: [Maintainer’s explanation and acknowledgment](https://x.com/deggen/status/2106810017915580802); [Project Babbage’s acknowledgment of the testing gap](https://x.com/ProjectBabbage/status/2106822131413872713)

## A matrix ready for real results

Evidence kind: proposed
Section: https://bsv.place/guides/wallet-compatibility-and-safe-changes/#compatibility-matrix

The downloadable CSV begins with the reported Zanaadu case and a blank test row. Its test status is not-tested because this article did not reproduce the workflow. The reported symptom remains in a separate field. Fill unknown versions only from evidence; do not infer them from a publication date.

Use the same workflow against the relevant released app and wallet versions, retain a non-sensitive result and record who performed the test. A successful retest supports that combination on that platform. It cannot establish universal compatibility or resolve unrelated reports. Link the evidence back into the article so the original conversation becomes a durable, revisable record.

Sources: [Zanaadu mobile workflow report](https://x.com/johncalhooon/status/2106787458138378251); [Reporter’s constructive follow-up](https://x.com/johncalhooon/status/2106824255992451579)

## What would change this assessment?

A named release and successful workflow retest can establish a repair for that combination. Repeated unexplained regressions or unclear semantics would justify revising implementation practices, compatibility commitments or the specification itself.

## Sources and provenance

- [Browser PR #159 signing-policy repair](https://github.com/bsv-blockchain/bsv-browser/pull/159) · reported · Access 2026-11-02 · Published 2026-10-06T00:42:50Z. Merged October 6. Maintainer reports a Zanaadu post on an iOS simulator development build before final changes; full released-workflow confirmation remains unestablished here.
- [Browser 1.8.0 public release](https://github.com/bsv-blockchain/bsv-browser/releases/tag/v1.8.0) · reported · Access 2026-11-02 · Published 2026-10-21T19:58:03Z. Published October 21 and includes PR 159. A release note is implementation evidence, not an independent complete workflow retest.
- [Desktop v3.1.1 migration notice](https://github.com/bsv-blockchain/bsv-desktop/releases/tag/v3.1.1) · reported · Access 2026-11-02 · Published 2026-10-11T21:30:42Z. Published October 11: WAB phone/password users remain on v2, built-in STAS removed, and separate wallet record stores can diverge when keys are shared. Maintainer guidance; no migration test here.
- [Desktop PR #100 spending enforcement and display status](https://github.com/bsv-blockchain/bsv-desktop/pull/100) · reported · Access 2026-11-02 · Published 2026-09-25T22:13:28Z. Maintainer reports enforcement repair in Wallet Toolbox 2.14.0/Desktop ≥2.9.6 and separate display/cache repair released 2.9.8. Issue 93 remains open; no independent original-task retest established.
- [TypeScript conformance runner scope](https://github.com/bsv-blockchain/ts-stack/blob/main/docs/conformance/runner-ts.md) · documented · Access 2026-11-02. Distinguishes structural fixture validation from execution of recognized behavior categories and explicit unsupported coverage.
- [BRC-100 · wallet to application interface](https://bsv.brc.dev/wallet/0100) · documented · Access 2026-11-02. The interface specification; implementation, policy and workflow outcomes need their own evidence. No new compatibility test is implied by this guide.
- [Zanaadu mobile workflow report](https://x.com/johncalhooon/status/2106787458138378251) · reported · Access 2026-10-05. October 4 user report of failed posting and an unexpected signing restriction. Not independently reproduced for this article.
- [Maintainer’s explanation and acknowledgment](https://x.com/deggen/status/2106810017915580802) · reported · Access 2026-10-05. Describes an overly restrictive change and missing prompt/release communication, despite a passing interface check. Does not establish a released repair.
- [Project Babbage’s acknowledgment of the testing gap](https://x.com/ProjectBabbage/status/2106822131413872713) · reported · Access 2026-10-05. Public acceptance of responsibility for code quality and workflow coverage. An acknowledgment is not a fix.
- [Reporter’s constructive follow-up](https://x.com/johncalhooon/status/2106824255992451579) · reported · Access 2026-10-05. Acknowledges shared responsibility. It does not confirm a successful retest.
- [TypeScript stack security policy](https://github.com/bsv-blockchain/ts-stack/security) · documented · Access 2026-11-02. Project-specific reporting policy. A policy is not an audit, a promised bounty, or evidence that this compatibility incident matches an advisory.

## Related resources

- [Interoperability laboratory and result checklist](https://bsv.place/guides/interoperability-testing-and-evidence/): New experimental evidence and the boundaries of what it establishes.
- [BRC-100 interoperability](https://bsv.place/answers/brc100-interoperability-and-portability/): Read the short answer on standards and independent implementations.
- [Data and service portability](https://bsv.place/answers/user-data-and-service-portability/): Check what a successful migration must retain.
- [Metanet](https://metanet.fyi/): Start with the app and wallet model in plain language.
