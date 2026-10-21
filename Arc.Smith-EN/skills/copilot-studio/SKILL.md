---
name: copilot-studio
description: "Guides agent creation in Microsoft Copilot Studio: harness choice, instructions, knowledge sources, topics, tools (connectors, agent flows, prompts, MCP), data capture pipelines, publishing and Copilot Credits consumption. Use when the target platform is Copilot Studio or when the case requires integrations, flows, topics or channels beyond Microsoft 365 Copilot."
---

# Microsoft Copilot Studio

## Goal
Guide building agents in Copilot Studio with the right architecture for the case (harness, knowledge, tools and topics), within the limits and with predictable cost.

## When to use
- The target platform is Copilot Studio.
- The case requires integrations with systems, flows, structured topics, data capture and storage or external channels.
- The user asks about Copilot Credits consumption or Copilot Studio licensing.

## Absolute rule
Before stating a limit, feature or billing value, consult the Microsoft Learn MCP. Features vary by harness: confirm in which harness the feature exists. Do not invent.

## Flow
1. Choose the harness by case (references/capacidades-limites.md).
2. Define instructions (smith-prompt Base Prompt, up to 8,000 characters), knowledge sources and tools (references/topicos-ferramentas-conhecimento.md).
3. If there is data capture and storage, use the pattern in references/pipeline-dados.md.
4. Estimate consumption and state the billing model (references/licenciamento-creditos.md).
5. Guide testing in the test pane and publishing to the right channel.

## Rules
- Create the agent in the web interface and do not mix interface editing with editing the YAML files.
- Write detailed descriptions for knowledge sources, tools and topics: the generative orchestrator decides based on them.
- In the instructions, refer to tools and topics with "/" and by their exact name.
- Do not change or suppress citation behavior in the instructions.
- Temperature only exists in the Prompt tool (0 to 1, default 0, disabled for reasoning models); it is not configurable on the agent.

## Resources
| File | When to load |
|---|---|
| references/capacidades-limites.md | For harnesses, limits and agent fields |
| references/topicos-ferramentas-conhecimento.md | For knowledge, tools, topics and instructions |
| references/pipeline-dados.md | For data capture with a flow and storage (SharePoint, Dataverse) |
| references/licenciamento-creditos.md | For billing, licenses and Copilot Credits estimates |
| references/fatos-volateis.md | Starting point for limits and values; confirm in Learn |
