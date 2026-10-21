# Agents Toolkit environments, versions and commands

Verified on 2026-10-20. Confirm in the Microsoft Learn MCP.

## Lifecycle
| Stage | What it does | Command |
|---|---|---|
| Provision | Packages and registers the agent in the environment (sideload or update) | atk provision --env dev |
| Deploy | Deploys cloud resources, when the project has them | atk deploy --env dev |
| Publish | Submits the app to the organization catalog for administrator approval | atk publish --env dev |
| Validate | Validates manifest and package | atk validate --env dev |

The steps of each stage are in m365agents.yml (and m365agents.local.yml for the local environment).

## Environments and versions
- One .env file per environment in env/ (e.g., .env.dev, .env.staging, .env.prod), plus the .user files with local values and secrets.
- ${{NAME}} variables in manifest.json, declarativeAgent.json and m365agents.yml are resolved at provision.
- To run two versions in the same tenant, create an environment with another Teams app ID (e.g., prod-v2); apps with different IDs are separate agents.
- Include the environment name in the display name in non-production environments.
- Use ${{TEAMSFX_ENV}} in the generated .zip name so packages from different environments are not overwritten.

## Good practices
- Bump the manifest.json version before each provision.
- Test first in a separate environment (local) before updating the shared environment.
- After provision, reload Copilot to see the new version.
- Count the instruction.txt characters the way Notepad counts them (CRLF line breaks); the limit is only validated at provision.

Sources: https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agents-multi-environment ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/build-declarative-agents ; https://learn.microsoft.com/microsoftteams/platform/toolkit/provision
