# Ambientes, versões e comandos do Agents Toolkit

Verificado em 2026-10-20. Confirme no Microsoft Learn MCP.

## Ciclo de vida
| Etapa | O que faz | Comando |
|---|---|---|
| Provision | Empacota e registra o agente no ambiente (sideload ou atualização) | atk provision --env dev |
| Deploy | Publica recursos de nuvem, quando o projeto tem | atk deploy --env dev |
| Publish | Envia o app ao catálogo da organização para aprovação do administrador | atk publish --env dev |
| Validate | Valida manifesto e pacote | atk validate --env dev |

Os passos de cada etapa ficam no m365agents.yml (e m365agents.local.yml para o ambiente local).

## Ambientes e versões
- Um arquivo .env por ambiente em env/ (ex.: .env.dev, .env.staging, .env.prod), mais os .user com valores locais e segredos.
- Variáveis ${{NOME}} no manifest.json, no declarativeAgent.json e no m365agents.yml são resolvidas no provision.
- Para rodar duas versões no mesmo tenant, crie um ambiente com outro Teams app ID (ex.: prod-v2); apps com IDs diferentes são agentes separados.
- Inclua o nome do ambiente no nome exibido em ambientes que não são de produção.
- Use ${{TEAMSFX_ENV}} no nome do .zip gerado para não sobrescrever pacotes de ambientes diferentes.

## Boas práticas
- Suba o version do manifest.json antes de cada provision.
- Teste primeiro em um ambiente separado (local) antes de atualizar o ambiente compartilhado.
- Depois do provision, recarregue o Copilot para ver a nova versão.
- Conte os caracteres do instruction.txt como o Bloco de Notas conta (quebra de linha CRLF); o limite só é validado no provision.

Fontes: https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agents-multi-environment ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/build-declarative-agents ; https://learn.microsoft.com/microsoftteams/platform/toolkit/provision
