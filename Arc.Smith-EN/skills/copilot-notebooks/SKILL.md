---
name: copilot-notebooks
description: "Guides the creation of complete Copilot Notebooks: name, custom instructions (Copilot instructions), recommended references (files, sites, folders, Pages, meetings and emails), usage structure, generated outputs and governance. Use when the user asks for a Copilot notebook or when the solution is to organize knowledge about a project or topic to query with Copilot, without creating an agent."
---

# Copilot Notebooks

## Goal
Deliver a notebook ready to set up: name, custom instructions, recommended references and usage guidance, working almost like an agent focused on the notebook's content.

## When to use
- The user asks for a Copilot Notebook.
- The need is to gather knowledge about a project, topic or client and talk with Copilot about that content, without configuring an agent.

## Absolute rule
Consult the Microsoft Learn MCP and the support documentation before stating limits and features (references/fatos-volateis.md). Undocumented limits, such as the instructions size, must not be invented. Do not recommend references the user has not indicated as existing: ask for the real files, sites or folders, or leave a placeholder.

## Flow
1. Understand the notebook's goal, its audience and the license of those who will use it (Copilot Chat or Microsoft Copilot).
2. Propose the notebook name.
3. Generate the custom instructions with the smith-prompt skill (7-parameter Base Prompt, up to 8,000 characters, ArcSmith standard).
4. Build the list of recommended references (references/referencias-recomendadas.md), respecting the limit and the sources of the license.
5. Guide the usage structure and outputs (references/estrutura-notebook.md).

## Delivery (copyable boxes)
- Notebook name.
- Copilot instructions (Base Prompt).
- Recommended references: table with reference, type and purpose.
- Suggested questions for the notebook chat (usage guidance; the notebook has no starter prompts field).
- Setup step by step (references/estrutura-notebook.md).

## Rules
- Respect the reference limit: 50 in Copilot Chat; more than 300 in Microsoft Copilot, but only the first 300 are used for grounding.
- Without a Microsoft Copilot license, use only standard sources (files, Pages, images, audio and public URLs).
- External URLs must be public (no sign-in, paywall or subpages).
- Warn that a deleted notebook cannot be recovered and that there is no automatic ownership transfer.

## Resources
| File | When to load |
|---|---|
| references/capacidades-limites.md | For license, limits, governance and storage |
| references/estrutura-notebook.md | To set up the notebook and guide usage and outputs |
| references/instrucoes-modelo.md | To write the notebook's Copilot instructions |
| references/referencias-recomendadas.md | To choose and recommend references |
| references/fatos-volateis.md | Starting point for limits; confirm in the sources |
