---
name: copilot-chat
description: "Guides agent creation for Copilot Basic (Copilot Chat without a Microsoft 365 Copilot license): features available at this level, which change fast and are confirmed in Learn on every creation, and when the client gets the Copilot Premium structure. Use when the client's level is Copilot Basic."
---

# Agents for Copilot Basic

## Goal
Make sure the proposed agent works in Copilot Basic, using only the features available at that level.

## When to use
- The client's level is Copilot Basic: Copilot Chat without a Microsoft 365 Copilot license and without pay-as-you-go billing.
- The user asks what can be done in Copilot Basic.

If the tenant has pay-as-you-go billing turned on, the client has the Copilot Premium structure: use the copilot-m365-agent-builder skill without the restrictions of this skill.

Creation happens in Agent Builder: also load the copilot-m365-agent-builder skill for fields, limits and the two creation modes (Assistant and Detailed).

## Absolute rule
Check the Microsoft Learn MCP before stating availability. In a conflict, Learn prevails. Do not promise features that Copilot Basic does not have.

## Flow
1. Confirm the client's level. If you do not know, ask.
2. Run the feature check (verificacao-recursos.md file of the smith-prompt skill) and classify each requested source, capability and skill: available in Basic today or Premium only. Use references/capacidades-limites.md as a starting point.
3. If the case depends on something that is Premium only, say so and propose an alternative: the user attaches or pastes the content in the conversation, uses public websites or moves to Copilot Premium.
4. Generate the agent with the smith-prompt skill, in the chosen mode.

## Rules
- Skills in Copilot Basic are changing (rollout in Copilot Chat between October and November 2026): include the Skills section in the brief only if the feature check confirms them.
- Tenant data (SharePoint, OneDrive, uploaded files, connectors, Dataverse, email, people and Teams) was not available in Basic at the last check: confirm before proposing it.
- The documentation diverges on agent creation by unlicensed users (references/fatos-volateis.md, CC-05): confirm in the tenant before promising.

## Resources
| File | When to load |
|---|---|
| references/capacidades-limites.md | To know what is available at each level |
| references/instrucoes-e-prompts.md | To write instructions for agents without tenant data |
| references/fatos-volateis.md | Starting point for availability; confirm in Learn |
