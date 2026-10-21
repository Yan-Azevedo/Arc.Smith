# declarativeAgent.json and manifest.json

Based on the published schema 1.8 and on the use of schema 1.9 for skills (verified on 2026-10-20).

## General rules
- Unrecognized properties invalidate the whole document.
- Strings without their own limit: up to 4,000 characters.
- Localizable strings can use [[key_name]].
- The Toolkit resolves $[file('instruction.txt')] and ${{VAR}} variables at provision; in a hand-built package, the instructions must be in the JSON itself.

## declarativeAgent.json properties
| Property | Required | Rule |
|---|---|---|
| $schema | No | URL of the schema of the version used |
| version | Yes | Schema version (e.g., v1.8; v1.9 for skills) |
| id | No | Manifest identifier |
| name | Yes | Up to 100 characters. Localizable |
| description | Yes | Up to 1,000 characters. Localizable |
| instructions | Yes | Up to 8,000 characters |
| capabilities | No | At most one of each type (references/capabilities.md) |
| conversation_starters | No | Up to 12. Each with text (required), title and depends_on (shows the starter only if the capability exists) |
| actions | No | 1 to 10 plugins, by reference (id and file) or inline |
| behavior_overrides | No | suggestions.disabled; special_instructions.discourage_model_knowledge; default_response_mode (Auto, Quick response or Think deeper; default Auto) |
| disclaimer | No | text up to 500 characters, shown at the start of the conversation |
| sensitivity_label | No | Only applies with embedded files |
| editorial_answers | No | url or answers (up to 300 pairs), with similarity_thresholds from 0 to 10 |
| worker_agents | No | Preview. Other declarative agents this agent can use |
| user_overrides | No | Lets the user turn capabilities off; only action: remove |
| agent_skills | No | Schema 1.9. List of objects with folder (e.g., skills/skill-name), registered by atk add skill |

## Minimal example
```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/copilot/declarative-agent/v1.8/schema.json",
  "version": "v1.8",
  "name": "[Agent name]",
  "description": "[Agent description]",
  "instructions": "$[file('instruction.txt')]",
  "conversation_starters": [
    { "title": "[Title]", "text": "[Prompt]" }
  ],
  "behavior_overrides": {
    "default_response_mode": "Auto"
  }
}
```

## manifest.json (app manifest)
- References the agent in copilotAgents.declarativeAgents (id and file).
- App version: bump it before each provision; otherwise the Toolkit may keep the previous build.
- Fill in name.short, name.full, description.short and description.full: the template placeholders are shown to the user.
- Icons: color.png and outline.png.

Sources: https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-manifest-1.8 ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/build-declarative-agents-customize-behavior
