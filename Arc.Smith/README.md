<h1 align="center">⚒️ ArcSmith — Documentação Técnica</h1>

<p align="center">
  <img src="../docs/Assets/ArcSmith.png" alt="ArcSmith" width="80%"/>
</p>

<p align="center">
  <strong>Forge the arc. Smith the prompt.</strong><br>
  Documentação técnica do Declarative Agent ArcSmith, construído sobre o Microsoft 365 Agents Toolkit.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Schema-v1.9-orange?style=flat-square" alt="Schema v1.9"/>
  <img src="https://img.shields.io/badge/Version-2.0.0-success?style=flat-square" alt="Version"/>
  <img src="https://img.shields.io/badge/Language-pt--BR-yellow?style=flat-square" alt="Language"/>
</p>

> Este documento é voltado a desenvolvedores e mantenedores do projeto. Para visão geral, acesse o [README principal](../README.md).

---

## Visão técnica

O ArcSmith é um **Declarative Agent** do Microsoft 365 Copilot. A partir da versão 2.0, o conhecimento sai do GitHub Pages e passa a viver em **Custom Skills** dentro do pacote: as instruções (`instruction.txt`) funcionam como **Core de orquestração** e cada skill carrega sob demanda o procedimento e os recursos de uma tarefa.

### Componentes principais

| Componente | Tipo | Propósito |
|---|---|---|
| `declarativeAgent.json` | Manifest principal | Capabilities, actions, `agent_skills` e behavior overrides |
| `instruction.txt` | Core | Identidade, regra absoluta, roteamento para skills, caixas copiáveis e comandos (limite 8000 caracteres) |
| `skills/` | Custom Skills | Oito skills com `SKILL.md` e `references/` |
| `manifest.json` | Manifesto M365 | Metadados, ícones, versão do app |
| `ai-plugin.json` e `mcp-tools.json` | Plugin MCP | Ferramentas do Microsoft Learn MCP |
| `m365agents.yml` | Configuração Toolkit | Lifecycle stages do Agents Toolkit |

---

## Schema e capabilities

### Versão do schema

```
v1.9 — Declarative Agent (mínimo exigido para Custom Skills)
```

### Capabilities ativas

```json
"capabilities": [
  { "name": "CodeInterpreter" },
  { "name": "OneDriveAndSharePoint" },
  { "name": "TeamsMessages" },
  { "name": "Email" },
  { "name": "EmailActions" }
]
```

O `WebSearch` com as URLs do GitHub Pages foi removido na 2.0. O agente não usa `EmbeddedKnowledge`, porque no preview as skills não podem ser combinadas com arquivos embedded.

### Behavior overrides

```json
"behavior_overrides": {
  "default_response_mode": "Think deeper",
  "special_instructions": {
    "discourage_model_knowledge": true
  }
}
```

| Configuração | Efeito |
|---|---|
| `default_response_mode: "Think deeper"` | Raciocínio profundo por padrão |
| `discourage_model_knowledge: true` | Prioriza skills e Microsoft Learn MCP sobre o conhecimento genérico do modelo |

### Actions (MCP)

```json
"actions": [
  { "id": "ai-plugin", "file": "ai-plugin.json" }
]
```

O `ai-plugin.json` conecta o **Microsoft Learn MCP Server** (`https://learn.microsoft.com/api/mcp`) com as ferramentas `microsoft_docs_search`, `microsoft_docs_fetch` e `microsoft_code_sample_search`.

---

## Custom Skills

<p align="center">
  <img src="../docs/Assets/ArcSmith2.png" alt="ArcSmith — visão técnica" width="80%"/>
</p>

| Skill | Função | Recursos principais |
|---|---|---|
| `arc-cases` | Seleção e documentação de cases, classificação Aderente ou Viável em projeto | Metodologia completa, construção e sustentação, impacto x esforço, antipadrões |
| `smith-prompt` | Modos Assistente e Detalhado, Prompt-Base, caixas copiáveis, skills do agente criado | Schema, ForgeProtocol, limites por plataforma, guia de skills, exemplos |
| `copilot-chat` | Agentes para Copilot Basic | Capacidades por nível (Basic e Premium), fatos voláteis |
| `copilot-m365-agent-builder` | Agent Builder, manual ou assistido | Campos e limites, briefing da aba Descrever, passo a passo |
| `copilot-m365-toolkit` | Agentes declarativos em código | Manifestos, capabilities, skills, MCP, provision |
| `copilot-studio` | Copilot Studio | Harnesses, ferramentas, pipeline de dados, Copilot Credits |
| `copilot-notebooks` | Copilot Notebooks | Instruções, referências recomendadas, estrutura |
| `documentacao` | Discovery e Guia de Criação em .docx | Modelos, regras de formatação, adaptação por plataforma |

### Padrões das skills

- `SKILL.md` com front matter YAML (`name` igual à pasta e `description` **entre aspas**) e seções Objetivo, Quando usar, Regra absoluta, Fluxo, Regras e Recursos.
- Regras de comportamento ficam só no `SKILL.md`; os `references/` trazem conteúdo descritivo.
- Cada skill de plataforma tem `references/fatos-volateis.md`, com fonte, data de verificação e prazo de revalidação.
- Limites do preview: 8 skills, 350 arquivos, profundidade 3, pacote de 10 MB, `SKILL.md` com menos de 20.000 caracteres.

### Fatos voláteis e atualização

Fatos que mudam rápido (limites, licenças, status de preview) ficam nas tabelas `fatos-volateis.md`. O método de revisão está em `docs/metodo-atualizacao.md` e o prompt reutilizável em `docs/prompts/revisao-fatos-volateis.md`.

---

## Módulos operacionais

### Arc — Seleção e Documentação de Cases

Interpreta transcrições e identifica cases. Com um case, documenta direto; com vários, gera o relatório de seleção e, depois da aprovação do cliente, documenta o escolhido. O case completo traz Apresentador e Área, Caso apresentado, Dor, Objetivo, O que resolve, Impacto, Valor e a classificação: **Aderente** (complexidade de construção e de sustentação, Baixa, Média ou Alta) ou **Viável em projeto**.

### Smith — Criação de Agentes

O primeiro passo é a **verificação de recursos** no Microsoft Learn (o que o nível e a plataforma permitem hoje, com fonte e data) e a escolha do modo, com recomendação: **Assistente** (entrevista ponto a ponto e briefing único para o Agent Builder, Copilot Basic e Premium) ou **Detalhado** (camada por camada no Agent Builder manual, Agents Toolkit, Copilot Studio e Copilot Notebooks). Quando a verificação confirmar suporte, o Smith também cria as skills do agente.

Gera o Prompt-Base em JSON, entregue em caixa copiável markdown:

```json
{
  "Parameters": {
    "Goal": "",
    "Context": "",
    "Instructions": "",
    "Tone": "",
    "Format": "",
    "Use Case": "",
    "Output": ""
  }
}
```

- Ordem fixa dos parâmetros; regras em `Instructions`, uma por linha; sem `\n` nos valores.
- `Temperature` saiu na 2.0: não é configurável em agentes (só existe na ferramenta de Prompt do Copilot Studio).
- Limite de 8.000 caracteres contando o bloco inteiro.
- No modo Detalhado, a primeira entrega são as caixas de Nome do Agente, Título resumido e Descrição, mais a pergunta do Output; no Assistente, tudo vai numa única caixa.

### Code Interpreter

Python em sandbox para análise de dados, visualizações e geração dos `.docx` de documentação.

**Limitação conhecida:** a leitura de `.xlsx` e `.docx` pode falhar em Declarative Agents. Workaround: converter para CSV ou colar o conteúdo.

---

## Comandos especiais

| Comando | Efeito |
|---|---|
| `encerrar` | Reseta o módulo Smith, retornando o Prompt-Base vazio |
| `novo case` | Inicia novo fluxo no módulo Arc, descartando contexto anterior |
| `gerar discovery` | Gera a Seleção de Cases ou o Documento do Case, conforme o momento (skill documentacao) |
| `gerar entrega` | Gera o Guia de Criação do Agente (skill documentacao) |

---

## Roteamento

| Input do usuário | Skill |
|---|---|
| Texto de reunião, transcrição ou anotações | arc-cases |
| Instruções, Prompt-Base, nome ou descrição de agente | smith-prompt |
| Plataforma de destino definida | Skill da plataforma |
| Documento de cases ou guia de criação | documentacao |
| Arquivo de dados ou pedido de análise | Code Interpreter |
| Ambiguidade | Pergunta ao usuário qual ação executar |

---

## Versionamento

### Schema de versão (Semantic Versioning adaptado)

| Tipo de mudança | Incremento |
|---|---|
| Mudança de arquitetura ou de fonte de conhecimento | MAJOR |
| Adição de capability, skill ou feature | MINOR |
| Ajuste de instruções, skills ou configuração | PATCH |
| Correção de bug | PATCH |

### Procedimento de Provision

1. Editar os arquivos necessários
2. Incrementar `version` no `manifest.json`
3. Rodar `atk validate` e conferir o YAML dos `SKILL.md` (o validate não detecta YAML inválido)
4. Executar **Provision** pelo painel Lifecycle do M365 Agents Toolkit, primeiro no ambiente `local`
5. Validar o funcionamento no Copilot M365

> **Importante:** sem incrementar a versão, o Provision pode manter o build anterior sem avisar.

---

## Pipeline de atualização do conhecimento

Na 2.0 o conhecimento está no pacote: toda mudança em uma skill exige incremento de versão e novo Provision.

```
Editar skills/  →  incrementar version  →  atk validate  →  Provision  →  ArcSmith usa a nova versão
```

Na 1.x, o conhecimento vinha do GitHub Pages e atualizava sem re-provisionar.

---

## Pré-requisitos de desenvolvimento

- **Node.js** versões 18, 20 ou 22
- **Microsoft 365 Agents Toolkit** — VS Code extension ou CLI (`atk` 1.1.18 ou superior)
- **Licença Microsoft 365 Copilot** e tenant no **Microsoft Frontier Program**
- Variável `TEAMSFX_AGENT_SKILLS=true` definida antes de abrir o VS Code
- Permissão de upload de aplicativos personalizados no tenant

---

## Configuração do MCP Server

O Microsoft Learn MCP está configurado em `.vscode/mcp.json`:

```json
{
  "servers": {
    "learnmicro": {
      "type": "http",
      "url": "https://learn.microsoft.com/api/mcp"
    }
  }
}
```

---

## Limitações conhecidas

| Limitação | Status | Workaround |
|---|---|---|
| Leitura nativa de `.xlsx` e `.docx` falha no Code Interpreter | Limitação de plataforma | Converter para CSV antes de anexar |
| Skills e Embedded Knowledge não podem ser combinados | Preview (suporte planejado) | Conhecimento como recursos das skills |
| Instruções limitadas a 8000 caracteres | Limite de plataforma | Core enxuto e detalhes nas skills |
| Custom Skills em preview | Frontier Program | Validar no ambiente `local` antes do `dev` |
| `atk validate` não valida o YAML dos `SKILL.md` | Ferramenta | Descriptions entre aspas e checagem com parser YAML |

---

## Espelho em inglês

A pasta `Arc.Smith-EN/` na raiz do repositório traz a tradução do `instruction.txt` e das skills, com os mesmos nomes de pastas e identificadores. Ela não é provisionada.

---

## Distribuição

O ArcSmith é de uso exclusivo do autor: é provisionado apenas no tenant do autor e não é compartilhado nem publicado.

---

## Stack técnica resumida

```
Microsoft 365 Copilot
    └── Declarative Agent (Schema v1.9)
        ├── Core (instruction.txt, ≤8000 chars)
        ├── Custom Skills (8)
        │   ├── arc-cases · smith-prompt · documentacao
        │   └── copilot-chat · copilot-m365-agent-builder · copilot-m365-toolkit · copilot-studio · copilot-notebooks
        ├── Capabilities
        │   ├── CodeInterpreter
        │   ├── OneDriveAndSharePoint
        │   ├── TeamsMessages
        │   ├── Email
        │   └── EmailActions
        ├── Actions
        │   └── ai-plugin → Microsoft Learn MCP
        └── Behavior Overrides
            ├── default_response_mode: Think deeper
            └── discourage_model_knowledge: true
```

---

## Autor e licença

**Desenvolvido por Yan Azevedo**

Projeto autoral fundamentado em metodologia própria construída a partir de prática profissional contínua. Projeto proprietário, de uso exclusivo do autor. Consulte [LICENSE.md](../LICENSE.md).

---

<p align="center">
  <em>"Forje o arco da narrativa. Construa o prompt com precisão."</em>
</p>