⚒️ ArcSmith — Declarative Agent (Microsoft 365 Copilot)

Forge the arc. Smith the prompt.
Agente Microsoft 365 Copilot (baseado em Declarative Agent template / M365 Agents Toolkit) que transforma entrevistas em cases estruturados e refina prompts com precisão de engenharia.
![ArcSmith Logo](docs/assets/arcsmith.png)
# ⚒️ ArcSmith
> Forge the arc. Smith the prompt.
Visão geral
O ArcSmith consolida dois agentes em um único fluxo coeso:

Casetron → transformar entrevistas em cases de valor ✅ Integrado
Prompt Smith → engenharia e refinamento incremental de prompts ✅ Integrado

O ArcSmith nasce do contexto de workshops de adoção do Microsoft Copilot, onde a entrega de valor tipicamente passa por duas etapas críticas:

Capturar o que foi construído (case)
Refinar como foi construído (prompt)


Contexto de uso (Workshops)
Fluxo conceitual de utilização dentro do workshop:
Workshop de Adoção M365 Copilot
         │
         ▼
  [ Entrevista / Conversa com cliente ]
         │
         ▼
     ⚒️ ArcSmith
    ┌────────────────────────────┐
    │  1. Captura da narrativa   │  ← herança do Casetron
    │  2. Estruturação do case   │
    │  3. Refinamento do prompt  │  ← herança do Prompt Smith
    │  4. Entrega formal ao      │
    │     cliente                │
    └────────────────────────────┘


Funcionalidades
🎯 Arc — Construção do Case

Recebe o relato de uma entrevista ou conversa com stakeholder
Extrai problema, contexto, solução e valor gerado
Estrutura um case pronto para apresentação ao cliente
Formato padronizado e replicável

⚒️ Smith — Engenharia de Prompt

Recebe instruções do usuário e retorna um Prompt-Base atualizado
Faz edição incremental sem perda de coerência
Saída em JSON padronizado (pt-BR)
Reset explícito via comando de encerramento
Resolve ambiguidades com bom senso; nunca inventa dados sensíveis


Base técnica: Declarative Agent (M365 Agents Toolkit)
Este projeto utiliza o Declarative Agent template, que permite construir uma versão customizada do Copilot para cenários específicos (ex.: conhecimento especializado, processos, reutilização de prompts).
O que o template inclui (componentes principais)

.vscode/ — arquivos de debug do VS Code
appPackage/ — templates do application manifest, GPT manifest e API specification
env/ — arquivos de ambiente

Arquivos-chave do template

appPackage/declarativeAgent.json — define comportamento e configurações do agente declarativo
appPackage/manifest.json — manifesto do aplicativo, com metadados do agente
m365agents.yml — arquivo principal do Microsoft 365 Agents Toolkit:

define Properties
define Stage definitions (configuração por estágios)




Pré-requisitos (desenvolvimento local)
Para rodar localmente, é necessário:

Node.js (versões suportadas): 18, 20, 22
Conta Microsoft 365 para desenvolvimento
Microsoft 365 Agents Toolkit:

Extensão do Visual Studio Code versão 5.0.0+ ou
M365 Agents Toolkit CLI


Licença do Microsoft 365 Copilot


Como executar (preview local no Copilot)
Passo a passo (via VS Code):

Abra o projeto no VS Code
Selecione o ícone do Microsoft 365 Agents Toolkit na barra lateral esquerda
Em Account, faça login com sua conta Microsoft 365 (se ainda não estiver logado)
No dropdown de configurações de execução (launch configuration), selecione:

Preview Local in Copilot (Edge) ou
Preview Local in Copilot (Chrome)


No Copilot, selecione o declarative agent do app
Faça perguntas ao agente — ele deve responder conforme as instruções definidas no projeto


Arquitetura do ArcSmith
Estrutura informada do projeto ArcSmith:
arcsmith/
├── agent/
│   ├── arcsmith.json              # Definição principal do agente (M365 Toolkit)
│   ├── arc-instructions.md        # Instruções do módulo de cases
│   └── smith-instructions.md      # Instruções do módulo de prompts
├── docs/
│   ├── caso-exemplo.md            # Exemplo de case gerado
│   └── prompt-base-exemplo.json   # Exemplo de Prompt-Base gerado
└── README.md
Observação: além da estrutura do ArcSmith acima, o template Declarative Agent também descreve diretórios típicos como .vscode/, appPackage/ e env/, bem como o arquivo m365agents.yml como núcleo do projeto no Agents Toolkit.


Extensões suportadas pelo template (pontos de evolução)
O template Declarative Agent suporta extensões do tipo:

Conversation starters (hints exibidos ao usuário)
Web content (busca de informação na web)
OneDrive e SharePoint como grounding knowledge
Microsoft Copilot connectors para conhecimento corporativo
API plugins para interação com REST APIs


Status do projeto

Arc (Cases): 🔨 Em construção
Smith (Prompts): 🔨 Em construção
Integração M365 Toolkit: 🔨 Em construção
Documentação de exemplos: 📋 Planejado


Tecnologias

Microsoft 365 Copilot — plataforma de execução
Microsoft 365 Agents Toolkit — framework de construção
JSON — formato de saída dos prompts estruturados
pt-BR — idioma principal


Autor
Desenvolvido como parte de um ecossistema próprio de engenharia de agentes para workshops de adoção Microsoft Copilot.

“Forje o arco da narrativa. Construa o prompt com precisão.”