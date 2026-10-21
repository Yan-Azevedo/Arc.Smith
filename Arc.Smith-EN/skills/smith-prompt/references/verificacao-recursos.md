# Feature check when creating the agent

Feature availability by level (Copilot Basic and Copilot Premium) and by platform changes often, sometimes within weeks. That is why Smith never treats this availability as fixed: it checks at the start of every new agent.

## When
- In the first step of every new agent, before choosing the mode.
- Again if the user changes the level or the platform, or asks for a feature that was not checked.

## What to check
| Item | Examples |
|---|---|
| Skills | Available for the level? On the platform? Preview or GA? Requires the Frontier Program? Limits? |
| Knowledge sources | SharePoint, OneDrive, uploaded files, email, Teams, people, connectors, sites |
| Capabilities | Code Interpreter, image generation, document creation |
| Actions and integrations | Connectors, flows, MCP, plugins |
| Limits | Characters of name, description and instructions; number of sources and files |

## How to check
1. Search the Microsoft Learn MCP (microsoft_docs_search) for the feature, the level and the platform. Examples: "Agent Builder skills license", "Copilot Chat agents capabilities licensing", "Copilot Studio knowledge sources limits".
2. Open the most relevant page (microsoft_docs_fetch) when the excerpt is not conclusive.
3. Compare with the fatos-volateis.md files of the platform skills. They are a starting point, not the final truth: in a conflict, Learn prevails.
4. If the documentation does not cover the point, or sources diverge, say so and ask the user to confirm in the tenant. Never fill the gap on your own.

## How to present it
A short table, before the mode question:

| Feature | Available for [level] in [platform] | Status | Source | Verified on |
|---|---|---|---|---|

- Status: GA, Preview, Rolling out, Not documented or Divergent.
- Source: title of the Learn page (no links in the created agent's instructions; here, in the conversation, the link may appear).
- Use only the confirmed features in the next layers of the creation. Anything Not documented or Divergent becomes a point to test in the tenant, not a certainty.
