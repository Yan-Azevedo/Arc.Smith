# Instruction limits and structure

## ArcSmith default limit
The Base Prompt has at most 8,000 characters on any platform, counting the whole block. This is the documented limit of the instructions box in Agent Builder, Agents Toolkit and Copilot Studio, and it is also adopted where the platform does not document a limit.

## Limits per platform (verified on 2026-10-19)
Before stating a limit to the user, confirm it in the Microsoft Learn MCP: these values change.

| Field | Agent Builder (Copilot Basic and Premium) | Agents Toolkit | Copilot Studio | Copilot Notebooks |
|---|---|---|---|---|
| Name | 30 characters | 100 characters | 42 characters, no < and > | Not documented |
| Description | 1,000 characters | 1,000 characters | 1,024 characters | Field does not exist |
| Instructions | 8,000 characters | 8,000 characters | 8,000 characters | Not documented; use 8,000 |
| Starter prompts | Title and description, no minimum | Up to 12 (schema 1.8); ArcSmith default: at most 6 | Check in Learn | Field does not exist |

Sources: Agent Builder (learn.microsoft.com/microsoft-365/copilot/extensibility/agent-builder-build-agents), declarative agent schema (declarative-agent-manifest), Copilot Studio (microsoft-copilot-studio/authoring-first-bot and requirements-quotas), Copilot Notebooks (support.microsoft.com, Provide custom instructions).

## How to summarize when exceeding 8,000
Cut in this order until it fits:
1. Repetitions and redundant sentences.
2. Long examples (replace with a short example).
3. Context explanations that do not change the behavior.
4. Format details already clear in Format.
Never cut: the Goal, the critical rules of Instructions and the exception conditions.

## How to write the Instructions content
Microsoft guidance for agent instructions:
- Focus on what the agent should do, not on what it should avoid.
- Use precise, observable verbs: ask, search, send, check, use.
- One action per rule: split compound rules into separate rules.
- Sequential steps only when order matters. For independent tasks, standalone rules.
- Explicit decision rules: "If X, do Y. If Z, do W."
- Always specify tone, level of detail and output format.
- Define the organization's own terms and acronyms in the text itself.
- Name tools and sources exactly. In Copilot Studio, reference tools, topics and variables with "/".
- Include a final self-check: before answering, the agent confirms it met Goal, Format and Instructions.
- Do not change the platform's citation behavior (Copilot Studio).
- When the agent drifts, a literal-reading rule stabilizes behavior: interpret the instructions literally, do not infer requirements, do not reorder steps.
- Never add links.
