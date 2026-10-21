---
name: arc-cases
description: "Turns transcripts, notes and summaries of discovery meetings into AI use cases, classifies each case as Adherent (with build and sustainment complexity) or Viable as a project, and drives the selection: a single case is documented directly; several cases produce the selection report for the client's approval. Use when the user sends meeting text or asks to identify, document, classify or select cases."
---

# Arc: case selection and documentation

## Goal
Interpret the content of a discovery meeting, identify the AI use cases, classify each one and take the client to the decision: which case will be built.

## When to use
- The user sends meeting text, a transcript, notes or a summary.
- The user asks to identify, document, classify or select cases.
- The user types the command novo case.

Do not use this skill to create the agent (smith-prompt skill) or to generate the formalization documents and email (documentacao skill).

## Absolute rule
Never invent systems, integrations, participants, areas or numbers that were not mentioned. If essential information is missing, record [not provided] in the field and, at the end of the answer, ask in a single message.

## Flow
1. Read all the content before structuring it.
2. Identify every use case, including fragmented ones (references/metodologia-identificacao.md). Treat each one as an independent unit.
3. Rebuild the current process without AI, highlighting the bottlenecks.
4. Classify each case (references/complexidade.md): Adherent, with build and sustainment complexity, or Viable as a project.
5. Follow the path according to the number of cases:
   - **One case:** document the full case (references/estrutura-case.md) and ask whether the user wants the Case Document. If so, follow the documentacao skill, which also prepares the formalization email.
   - **Several cases:** build the selection report (references/estrutura-case.md, summary format) and ask whether the user wants the Case Selection document. If so, follow the documentacao skill. Wait for the client's approval.
6. After approval, document the chosen case in the full format and ask whether the user wants the Case Document.

## Rules
- Propose simple, feasible solutions that the client can sustain after delivery.
- In every adherent case, make it clear that the higher the sustainment complexity, the more dedication the client needs to maintain the solution.
- A case beyond the scope of a short build is Viable as a project, never silently discarded.
- Resolve ambiguities with common sense, without overstating the value.
- Solution types (Prompt, Agent, Project) are internal reasoning: they guide the classification but never appear in the case text (references/tipo-solucao.md).

## Command
- novo case: starts a new flow, discarding the previous context.

## Resources
| File | When to load |
|---|---|
| references/estrutura-case.md | Whenever documenting a case or building the selection report |
| references/complexidade.md | Whenever classifying a case |
| references/metodologia-identificacao.md | To identify, separate and map cases (AS-IS, TO-BE) |
| references/priorizacao.md | To support the client's decision among several adherent cases |
| references/tipo-solucao.md | To decide internally between prompt, agent or project |
| references/metodologia-fundamentos.md | For the fundamental criteria and concepts (idea, case, POC, prompt, agent, project) |
| references/metodologia-entrevistas.md | When the user asks for help preparing or running discovery interviews |
| references/metodologia-validacao.md | To plan tests and validation with users |
| references/metodologia-entrega.md | To guide delivery, handover and sustainment of the solution |
| references/metricas-valor.md | To define or estimate value and impact metrics |
| references/antipadroes.md | To review risks, pitfalls and warning signs |
