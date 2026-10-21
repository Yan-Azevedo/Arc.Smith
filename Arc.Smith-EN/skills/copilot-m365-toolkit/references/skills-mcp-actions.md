# Skills, MCP and API plugins

Verified on 2026-10-20. Confirm in the Microsoft Learn MCP.

## Custom skills (preview)
- Requires schema v1.9, the Frontier Program and the TEAMSFX_AGENT_SKILLS=true variable (restart VS Code after setting it).
- Create: atk add skill --name skill-name --description "description", or Add Skill in the Toolkit pane. Import a folder: atk add skill --from PATH.
- atk registers the skill in agent_skills (folder: skills/name) and creates skills/name/SKILL.md. There is no remove command: delete the folder and the agent_skills entry.
- SKILL.md: YAML front matter with name (same as the folder name, lowercase and hyphens) and description; instructions under 20,000 characters.
- Put the description in quotes: if the text contains ": ", the YAML becomes invalid and the skill does not load. atk validate does not detect this error.
- Limits: 8 skills, 350 files, depth 3, 10 MB package, no .zip in the Toolkit, no reuse across agents.
- Scripts run in a sandbox: no network, no package installation, no authenticated calls and no access to MCP or connectors.
- Does not combine with EmbeddedKnowledge and does not work in tenants with Purview Information Barriers.
- In the agent instructions, refer to skills at a high level; the detail stays in SKILL.md.

## MCP plugin (remote MCP server)
- In the Toolkit: Create a New Agent/App, Declarative Agent, Add an Action, Start with an MCP Server. Provide the URL and the authentication type: OAuth (static registration), OAuth (dynamic registration), Entra SSO or None.
- In ai-plugin.json (schema 2.4), the runtime type is RemoteMCPServer, with spec.url.
- Tool discovery:
  - Dynamic (Toolkit default): functions empty and run_for_functions set to ["*"]; tools are read from the server at runtime.
  - Pinned: tools are listed in functions and run_for_functions, and the definitions in spec.mcp_tool_description (file with the tools/list output).
- To debug locally, point spec.url to a dev tunnel (e.g., PLUGIN_SERVER_URL variable in .env.dev.user).
- Note: atk 1.1.17 reported a false error on the RemoteMCPServer runtime; from 1.1.18 validate passes.

## API plugin (OpenAPI)
- In the Toolkit: Add Action, Start with an OpenAPI Description Document, select the file and operations, then manifest.json.
- The server address goes in servers in the OpenAPI document.

Sources: https://learn.microsoft.com/microsoft-365/copilot/extensibility/build-declarative-agents-add-custom-skills ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/build-mcp-plugins ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/plugin-dynamic-tool-discovery ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/plugin-debug-local ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/build-declarative-agents-add-capabilities
