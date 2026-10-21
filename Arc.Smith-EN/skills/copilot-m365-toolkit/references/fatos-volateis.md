# Volatile facts: Microsoft 365 Agents Toolkit

Fast-changing facts. In case of conflict, Microsoft Learn prevails. Revalidate according to the Revalidate column.

| ID | Fact | Current value | Status (GA, Preview, Planned) | Source (Learn URL) | Verified on | Affects | Revalidate (days) |
|---|---|---|---|---|---|---|---|
| FV-01 | Max. skills per agent | 8 | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit | 30 |
| FV-02 | Max. files in skills (Toolkit) | 350 (support matrix) / 400 (Toolkit article): docs diverge; use 350 as the limit | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills#support-matrix | 2026-10-19 | copilot-m365-toolkit | 30 |
| FV-03 | Max. directory depth | 3 | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit | 30 |
| FV-04 | Package size (Toolkit) | 10 MB | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit | 30 |
| FV-05 | Skill as .zip in the Toolkit | not supported (directory) | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit | 30 |
| FV-06 | Skills + embedded files | do not combine (support planned) | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit | 30 |
| FV-07 | Minimum manifest for skills | declarativeAgent v1.9 | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit | 30 |
| FV-08 | Variable to enable | TEAMSFX_AGENT_SKILLS=true | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit | 30 |
| FV-09 | Scripts in the sandbox | no network, no package installation, no authenticated calls, no MCP/connectors | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit | 30 |
| FV-10 | Tenants with Purview Information Barriers | skills unavailable | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit | 30 |
| FV-11 | ISVs / Partner Center | not supported yet | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit | 30 |
| FV-12 | Valid default_response_mode values | Auto, Quick response, Think deeper (default Auto) | GA | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-manifest-1.8 | 2026-10-20 | copilot-m365-toolkit | 90 |
| FV-13 | Agent instructions limit | 8000 characters | GA | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-instructions | 2026-10-19 | copilot-m365-toolkit | 90 |
| FV-14 | SKILL.md limit | SKILL.md: instructions < 20,000 characters (resources do not count) | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit | 30 |
| FV-15 | Knowledge source content is not trusted instruction (XPIA): directives may be blocked or truncated. Behavior rules stay in instruction.txt and SKILL.md | Treat as untrusted | GA | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-instructions | 2026-10-19 | copilot-m365-toolkit | 90 |
| FV-16 | Schema version documented as latest | 1.8 (the 1.9 page is not published; 1.9 is required for skills) | GA (1.8) | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-manifest-1.8 | 2026-10-20 | copilot-m365-toolkit | 30 |
| FV-17 | Max. conversation_starters | 12 (in schema 1.6 the docs diverged between 6 and 12) | GA | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-manifest-1.8 | 2026-10-20 | copilot-m365-toolkit | 90 |
| FV-18 | Max. actions (plugins) | 1 to 10 | GA | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-manifest-1.8 | 2026-10-20 | copilot-m365-toolkit | 90 |
| FV-19 | WebSearch sites | Docs: up to 4, at most two path segments, no parameters; observed: 10 provisioned successfully (Marchtron) | GA | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-manifest-1.8 | 2026-10-20 | copilot-m365-toolkit | 90 |
| FV-20 | EmbeddedKnowledge in the manifest | Up to 10 files of 1 MB | to verify | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-manifest-1.8 | 2026-10-20 | copilot-m365-toolkit | 30 |
| FV-21 | EmailActions and MeetingActions | Introduced in schema 1.8 | to verify | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-manifest-1.8 | 2026-10-20 | copilot-m365-toolkit | 30 |
| FV-22 | MCP tool discovery | Dynamic is the Toolkit default (run_for_functions ["*"]); pinned with mcp_tool_description | to verify | https://learn.microsoft.com/microsoft-365/copilot/extensibility/plugin-dynamic-tool-discovery | 2026-10-20 | copilot-m365-toolkit | 30 |
| FV-23 | atk validator and RemoteMCPServer | False error in atk 1.1.17; fixed in 1.1.18 | to verify | observed in the ArcSmith project | 2026-10-20 | copilot-m365-toolkit | 90 |
| FV-24 | Email draft with EmailActions | The docs mention supervised send; draft creation is not documented. Test in ArcSmith | to verify | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-manifest-1.8 | 2026-10-21 | copilot-m365-toolkit, documentacao | 30 |
| FV-25 | Sending a Teams message from a declarative agent | No native capability; the documented paths are Work IQ MCP (preview) or a Microsoft Graph API plugin | to verify | https://learn.microsoft.com/microsoft-365/copilot/extensibility/work-iq/mcp/overview | 2026-10-21 | copilot-m365-toolkit | 30 |
