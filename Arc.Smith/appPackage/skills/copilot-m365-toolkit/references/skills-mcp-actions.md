# Skills, MCP e plugins de API

Verificado em 2026-10-20. Confirme no Microsoft Learn MCP.

## Custom skills (preview)
- Exige schema v1.9, Frontier Program e a variável TEAMSFX_AGENT_SKILLS=true (reinicie o VS Code depois de definir).
- Criar: atk add skill --name nome-da-skill --description "descrição", ou Add Skill no painel do Toolkit. Importar uma pasta: atk add skill --from CAMINHO.
- O atk registra a skill em agent_skills (folder: skills/nome) e cria skills/nome/SKILL.md. Não há comando para remover: apague a pasta e a entrada em agent_skills.
- SKILL.md: front matter YAML com name (igual ao nome da pasta, minúsculas e hífens) e description; instruções com menos de 20.000 caracteres.
- Coloque a description entre aspas: se o texto tiver ": ", o YAML fica inválido e a skill não carrega. O atk validate não detecta esse erro.
- Limites: 8 skills, 350 arquivos, profundidade 3, pacote de 10 MB, sem .zip no Toolkit, sem reuso entre agentes.
- Scripts rodam em sandbox: sem rede, sem instalar pacotes, sem chamadas autenticadas e sem acesso a MCP ou conectores.
- Não combina com EmbeddedKnowledge nem funciona em tenants com Purview Information Barriers.
- Nas instruções do agente, cite as skills em alto nível; o detalhe fica no SKILL.md.

## Plugin MCP (servidor MCP remoto)
- No Toolkit: Create a New Agent/App, Declarative Agent, Add an Action, Start with an MCP Server. Informe a URL e o tipo de autenticação: OAuth (registro estático), OAuth (registro dinâmico), Entra SSO ou None.
- No ai-plugin.json (schema 2.4), o runtime é do tipo RemoteMCPServer, com spec.url.
- Descoberta de ferramentas:
  - Dinâmica (padrão do Toolkit): functions vazio e run_for_functions igual a ["*"]; as ferramentas são lidas do servidor em tempo de execução.
  - Fixas: as ferramentas ficam listadas em functions e em run_for_functions, e as definições em spec.mcp_tool_description (arquivo com a saída de tools/list).
- Para depurar localmente, aponte spec.url para um dev tunnel (ex.: variável PLUGIN_SERVER_URL no .env.dev.user).
- Atenção: o atk 1.1.17 acusava erro falso no runtime RemoteMCPServer; a partir do 1.1.18 o validate passa.

## Plugin de API (OpenAPI)
- No Toolkit: Add Action, Start with an OpenAPI Description Document, selecione o arquivo e as operações, depois o manifest.json.
- O endereço do servidor fica em servers no OpenAPI.

Fontes: https://learn.microsoft.com/microsoft-365/copilot/extensibility/build-declarative-agents-add-custom-skills ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/build-mcp-plugins ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/plugin-dynamic-tool-discovery ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/plugin-debug-local ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/build-declarative-agents-add-capabilities
