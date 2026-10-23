# Contributing

Thank you for helping maintain this list. The rules below keep entries consistent, verifiable and machine-readable, so that the list can serve as the basis for a future systematic survey.

## What belongs here

The list targets AI systems whose reports conflict with their own judgments, which we call honesty bugs. An entry qualifies if it does at least one of the following:

- documents lying, deception, dishonest or unfaithful reporting, sycophancy against the model's own knowledge, overclaiming, or fabricated reports of actions by LLMs or agents;
- provides a benchmark, dataset, test generation method or evaluation protocol for such behaviors;
- supplies evidence about what a model believes or judges: chain-of-thought faithfulness and monitorability, belief elicitation, black-box or white-box lie detection, consistency checks, introspection, self-report or confessions;
- studies how the agent model or the agent harness (scaffold, system prompt, context, tools, feedback) shapes honest reporting;
- mitigates or monitors such behaviors at training time or at run time;
- questions the validity of honesty evaluations, for example through evaluation awareness or measurement confounds;
- is a tool or environment used to audit or test these behaviors.

The list is deliberately strict about what counts as in-field. Work on neighbouring concepts (hallucination, calibration, abstention, permitted deception in games) is kept only under Boundary Concepts, and only when it helps draw the line between an honesty bug and its neighbours. Entries should have appeared after the release of ChatGPT in late 2022.

Not included: pure factuality or retrieval work with no link to model belief; human-made misinformation, deepfakes or AI-text detection; "honest reporting" in mechanism design; generic jailbreak or harmful-content safety unrelated to deception; deception aimed at agents rather than by them; and items without a resolvable identifier or official page.

## Where an entry goes

The sections mirror the honesty testing workflow:

- **Foundations**: definitions, frameworks, philosophy and surveys of honesty and deception in AI.
- **Honesty Bugs in the Wild**: empirical evidence of the phenomena, grouped by kind (lying under pressure, sycophancy, scheming and sandbagging, agent overclaiming and fabricated actions, bullshit and manipulation).
- **Benchmarks and Datasets**: reusable test inputs and evaluation protocols.
- **Testing Components**: work that isolates the contribution of the agent model or of the agent harness.
- **Test Oracles**: ways of obtaining evidence of the judgment behind a claim, split into direct (reasoning traces), indirect (black-box elicitation and self-report) and white-box (probes and interpretability) evidence.
- **Test Validity**: threats to the validity of honesty evaluations.
- **Repair and Runtime Monitoring**: training-time mitigation and run-time monitoring.
- **Software Engineering Perspective**: testing and quality work on LLM and agent systems that treats dishonest reporting as a defect.
- **Boundary Concepts**: hallucination, calibration and permitted deception.
- **Tools and Environments**: auditing and evaluation infrastructure.

Pick the section that matches the main contribution. A benchmark paper whose headline is the behavior it reveals still goes under Benchmarks and Datasets; a paper that proposes an oracle and also reports a phenomenon goes under Test Oracles.

## Verification standard

Before adding an entry, confirm the following from a live registry or official page (DOI, arXiv, ACL Anthology, OpenReview, publisher, or the project site):

- title, first author, venue and year;
- the paper link resolves;
- the code link, if given, exists and matches the paper by name, owner or the paper's own metadata.

Years follow the year the publisher cites for the version of record for journal and conference papers, and the first arXiv version for preprints. If a peer-reviewed version exists, cite it and link the preprint only when the peer-reviewed version is not openly accessible. Give a peer-reviewed venue only when it is confirmed; otherwise use `arXiv`.

## Entry format

One line per entry, placed in the section where its main contribution lies.

```
- Title (Venue Year) [[paper]](link) [[code]](link)
```

For related awesome lists:

```
- [Name](link)
```

Rules:

- Title in plain text, exactly as published. No description after the links.
- Venue and year in parentheses. Use the venue abbreviation readers recognise (ICSE, ICLR, NeurIPS, Nature). Use `arXiv` for preprints, `Findings of ACL 2025` for findings tracks, and the series name for workshops (for example `ICML 2026 Workshop`). For lab reports use the organisation and the kind of document (for example `Anthropic blog 2025`, `OpenAI system card 2025`). Put the year last.
- Prefer peer-reviewed work in LLM, NLP, ML and software engineering venues. Add an arXiv preprint only when it is directly about conflicts between what a system reports and what it judges. Blog posts and system cards are accepted only from the organisation that trained or evaluated the model, and only when they report primary evidence.
- `[[paper]]` is required for papers. `[[code]]`, `[[website]]` or `[[data]]` are optional and only when the link exists and matches.
- No em-dashes, no emojis.
- Entries within a list are ordered by year descending, then by title ignoring case. Related lists are alphabetical.
- Each work appears once.

## Pull requests

- One topic per pull request. Several entries for the same section are fine.
- Update the "updated" badge at the top of README.md.
- Keep the section titles unchanged. They follow the wording of the vision paper on honesty bugs and honesty testing.
- Run a link check locally before opening the pull request, for example with `lychee README.md`, or state in the description that each link was opened by hand.

## Suggesting without a pull request

Open an issue using the "Suggest an entry" template with the title, the link and the section you think it belongs to. A maintainer will verify and add it.
