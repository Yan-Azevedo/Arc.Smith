---
name: copilot-m365-toolkit
description: "Guides declarative agent creation with the Microsoft 365 Agents Toolkit (technical audience): declarativeAgent.json, manifest.json, capabilities, conversation starters, behavior overrides, custom skills, MCP and API plugins, environments, provision, deploy and publish. Use when the target platform is Agents Toolkit or when the user asks for manifest files, capabilities, MCP or atk commands."
---

# Microsoft 365 Agents Toolkit (declarative agents)

## Goal
Guide building declarative agents in code with Agents Toolkit, ensuring a valid manifest, correct capabilities and a safe lifecycle (provision, deploy, publish).

## When to use
- The target platform is Agents Toolkit (technical audience, project versioned in a repository).
- The user asks for declarativeAgent.json, manifest.json, ai-plugin.json, capabilities, conversation starters, skills or MCP.
- The user asks for atk commands or help with provision and validation errors.

## Absolute rule
Before stating a manifest property, valid value or limit, consult the Microsoft Learn MCP. An unrecognized property invalidates the whole manifest: never invent fields.

## Flow
1. Confirm the project's schema version (version and $schema fields) and the agent's audience (license).
2. Build or review declarativeAgent.json (references/manifest-declarativeagent.md).
3. Choose the capabilities by case and license (references/capabilities.md).
4. If there is an integration, define skills, MCP or API plugin (references/skills-mcp-actions.md).
5. Guide the lifecycle: version, environment and commands (references/provision-deploy.md).
6. The instructions follow the smith-prompt Base Prompt, in the instruction.txt file (up to 8,000 characters).

## Rules
- Deliver complete JSON files in a code block, ready to paste, and validate the syntax before delivering.
- Use only documented values (example: default_response_mode only accepts Auto, Quick response and Think deeper).
- Bump the manifest.json version before each provision.
- Skills require schema v1.9 and do not combine with EmbeddedKnowledge (preview).
- For fast-changing facts, use references/fatos-volateis.md as a starting point and confirm in Learn.

## Resources
| File | When to load |
|---|---|
| references/manifest-declarativeagent.md | For declarativeAgent.json and manifest.json properties and limits |
| references/capabilities.md | To choose and configure capabilities |
| references/skills-mcp-actions.md | For custom skills, MCP plugins and API plugins |
| references/provision-deploy.md | For environments, versions and atk commands |
| references/capacidades-limites.md | For overview, license and restrictions of the declarative agent |
| references/fatos-volateis.md | Starting point for limits and status; confirm in Learn |
