<h1 align="center">⚒️ ArcSmith — Documentação Técnica</h1>

<p align="center">
  <img src="../docs/Assets/ArcSmith.png" alt="ArcSmith" width="80%"/>
</p>

<p align="center">
  <strong>Forge the arc. Smith the prompt.</strong><br>
  Documentação técnica do Declarative Agent ArcSmith, construído sobre o Microsoft 365 Agents Toolkit.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Schema-v1.7-orange?style=flat-square" alt="Schema v1.7"/>
  <img src="https://img.shields.io/badge/Version-1.4.0-success?style=flat-square" alt="Version"/>
  <img src="https://img.shields.io/badge/Language-pt--BR-yellow?style=flat-square" alt="Language"/>
</p>

> Este documento é voltado a desenvolvedores e mantenedores do projeto. Para visão geral, acesse o [README principal](../README.md).

---

## Visão técnica

O ArcSmith é um **Declarative Agent** do Microsoft 365 Copilot que utiliza arquitetura híbrida de grounding multi-fonte com retrieval aumentado, sem dependência de vector store ou pipeline RAG técnico.

### Componentes principais

| Componente | Tipo | Propósito |
|---|---|---|
| `declarativeAgent.json` | Manifest principal | Define capabilities, knowledge sources e behavior overrides |
| `instruction.txt` | Instruções operacionais | Comportamento do agente (limite 8000 caracteres) |
| `manifest.json` | Manifesto M365 | Metadados, ícones, developer info |
| `ai-plugin.json` | Plugin MCP | Definição das ferramentas do Microsoft Learn MCP |
| `m365agents.yml` | Configuração Toolkit | Lifecycle stages do Agents Toolkit |

<p align="center">
  <img src="../docs/Assets/ArcSmith2.png" alt="ArcSmith — visão técnica" width="500"/>
</p>

---

## Schema e capabilities

### Versão do schema

```
v1.7 — Declarative Agent
```

### Capabilities ativas

```json
"capabilities": [
  { "name": "CodeInterpreter" },
  {
    "name": "WebSearch",
    "sites": [
      { "url": "https://yan-azevedo.github.io/Arc.Smith/ForgeProtocol" },
      { "url": "https://yan-azevedo.github.io/Arc.Smith/SolutionKnowledge" }
    ]
  },
  { "name": "OneDriveAndSharePoint" },
  { "name": "TeamsMessages" },
  { "name": "Email" }
]
```

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
| `default_response_mode: "Think deeper"` | Força raciocínio profundo por padrão (Chain of Thought) |
| `discourage_model_knowledge: true` | Prioriza knowledge curado sobre conhecimento genérico do modelo |

### Actions (MCP)

```json
"actions": [
  {
    "id": "ai-plugin",
    "file": "ai-plugin.json"
  }
]
```

O `ai-plugin.json` define a conexão com o **Microsoft Learn MCP Server** (`https://learn.microsoft.com/api/mcp`), expondo as ferramentas `microsoft_docs_search` e `microsoft_docs_fetch`.

---

## Arquitetura de conhecimento

### Camada 1 — Conhecimento curado (estático)

Bases metodológicas autorais publicadas via GitHub Pages, consumidas via WebSearch capability.

| URL | Conteúdo |
|---|---|
| [ForgeProtocol](https://yan-azevedo.github.io/Arc.Smith/ForgeProtocol) | Engenharia de prompt — estrutura JSON, parâmetros, boas práticas |
| [SolutionKnowledge](https://yan-azevedo.github.io/Arc.Smith/SolutionKnowledge) | Metodologia completa de construção de soluções de IA |

### Camada 2 — Retrieval dinâmico (externo)

Microsoft Learn MCP Server — acesso em tempo real à documentação oficial Microsoft.

### Camada 3 — Grounding nativo (tenant)

Acesso direto ao contexto do usuário via capabilities nativas: OneDrive, SharePoint, Teams, Email.

---

## Módulos operacionais

### Arc — Documentação de Cases

Interpreta transcrições de conversas com stakeholders, identifica cases, estrutura no template institucional e classifica complexidade (Baixa 🟢 / Média 🟡 / Alta 🔴 / Projeto 💼).

### Smith — Engenharia de Prompt

Gera Prompt-Base estruturado em JSON. Cada mensagem é tratada como edição incremental.

**Schema do output:**
```json
{
  "Parameters": {
    "Temperature": "[0.0–1.0]",
    "Goal": "[Objetivo detalhado]",
    "Tone": "[Tom]",
    "Format": "[Formato]",
    "Use Case": "[Cenário]",
    "Context": "[Contexto]",
    "Instructions": "[Diretrizes]",
    "Output": "[Formato de saída do agente criado]"
  }
}
```

**Campos apresentados separadamente em texto na primeira resposta:**
- Nome do Agente
- Título resumido
- Descrição

### Code Interpreter

Python em sandbox para validação de JSONs, análise de planilhas (CSV/TSV) e geração de artefatos.

**Limitação conhecida:** Arquivos `.xlsx` e `.docx` apresentam bug em Declarative Agents (reportado desde nov/2025). Workaround: converter para CSV antes de anexar.

---

## Comandos especiais

| Comando | Efeito |
|---|---|
| `encerrar` | Reseta o módulo Smith, retornando Prompt-Base zerado |
| `novo case` | Inicia novo fluxo no módulo Arc, descartando contexto anterior |

---

## Identificação de módulo ativo

| Input do usuário | Módulo ativado |
|---|---|
| Texto de reunião, transcrição ou anotações | Arc |
| Instruções de agente ou solicitação de JSON | Smith |
| Arquivo de dados ou pedido de análise | Code Interpreter |
| Ambiguidade | Pergunta ao usuário qual módulo usar |

---

## Versionamento

### Schema de versão (Semantic Versioning adaptado)

| Tipo de mudança | Incremento |
|---|---|
| Adição de capability ou feature maior | MINOR ou MAJOR |
| Ajuste de instruções ou configuração | PATCH |
| Correção de bug | PATCH |

### Procedimento de Provision

1. Editar arquivos necessários
2. Incrementar `version` no `manifest.json`
3. Executar **Provision** pelo painel Lifecycle do M365 Agents Toolkit
4. Validar funcionamento no Copilot M365

> **Importante:** Toda mudança requer incremento de versão. O M365 rejeita Provisions com versão igual ou inferior à existente no tenant.

---

## Pipeline de atualização do conhecimento

Knowledge sources publicadas via GitHub Pages atualizam **em tempo real** — sem necessidade de re-provisionamento.

```
Editar .md em docs/  →  git push  →  GitHub Pages rebuild (1-2min)  →  ArcSmith consome versão atualizada
```

---

## Pré-requisitos de desenvolvimento

- **Node.js** versões 18, 20 ou 22
- **Microsoft 365 Agents Toolkit** — VS Code extension 5.0.0+ (ou CLI equivalente)
- **Licença Microsoft 365 Copilot**
- **Conta Microsoft 365** com permissões de desenvolvimento

---

## Execução local

### Preview no Copilot

1. Abra o projeto no VS Code
2. Selecione o ícone do Microsoft 365 Agents Toolkit
3. Em **Account**, faça login com a conta Microsoft 365
4. No dropdown de launch, selecione **Preview Local in Copilot (Edge)** ou **(Chrome)**
5. O ArcSmith abre no Copilot conectado ao tenant

> **Nota:** Declarative Agents não suportam debug local tradicional (`localhost`). O Preview Local executa diretamente no tenant.

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

Ferramentas expostas via `ai-plugin.json`:
- `microsoft_docs_search` — busca semântica
- `microsoft_docs_fetch` — recuperação de páginas completas

---

## Limitações conhecidas

| Limitação | Status | Workaround |
|---|---|---|
| Leitura nativa de `.xlsx` e `.docx` falha no Code Interpreter | Bug Microsoft (nov/2025) | Converter para CSV antes de anexar |
| Embedded Knowledge não aceita `.md` | Limitação plataforma | Usar GitHub Pages + WebSearch capability |
| Instruções limitadas a 8000 caracteres | Limitação Toolkit | Distribuir conhecimento entre instructions + knowledge sources |
| WebSearch limitado a 4 URLs | Limitação plataforma | Consolidar conteúdo em documentos maiores |

---

## Extensões suportadas (pontos de evolução futura)

- Conversation starters
- Web content / WebSearch (em uso)
- OneDrive e SharePoint (em uso)
- Microsoft Copilot connectors (Graph Connectors)
- API plugins customizados
- Embedded knowledge (aguardando suporte a `.md`)

---

## Distribuição

### Tenant próprio (modo dev)

Usuários do mesmo tenant podem receber o agente via compartilhamento direto no Microsoft 365 Agents Toolkit (Lifecycle → Compartilhar).

### Múltiplos tenants (futuro)

Publicação na Microsoft Marketplace ou Microsoft 365 Admin Center exige aprovação adicional e revisão técnica completa.

---

## Stack técnica resumida

```
Microsoft 365 Copilot
    └── Declarative Agent (Schema v1.7)
        ├── Instructions (≤8000 chars)
        ├── Capabilities
        │   ├── CodeInterpreter
        │   ├── WebSearch (GitHub Pages)
        │   ├── OneDriveAndSharePoint
        │   ├── TeamsMessages
        │   └── Email
        ├── Actions
        │   └── ai-plugin → Microsoft Learn MCP
        └── Behavior Overrides
            ├── default_response_mode: Think deeper
            └── discourage_model_knowledge: true
```

---

## Autor e licença

**Desenvolvido por Yan Azevedo**

Projeto autoral fundamentado em metodologia própria construída a partir de prática profissional contínua. Consulte [LICENSE.md](../LICENSE.md) para termos de uso (CC BY-NC-ND 4.0).

---

<p align="center">
  <em>"Forje o arco da narrativa. Construa o prompt com precisão."</em>
</p>