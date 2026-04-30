# ⚒️ ArcSmith

> **Forge the arc. Smith the prompt.**  
> Agente Microsoft 365 Copilot que transforma entrevistas em cases estruturados e refina prompts com precisão de engenharia.

---

## O que é o ArcSmith?

O **ArcSmith** é um agente construído no Microsoft 365 Copilot (M365 Toolkit) que consolida dois agentes anteriores em um único fluxo coeso:

| Agente original | Função | Status no ArcSmith |
|---|---|---|
| **Casetron** | Transformar entrevistas em cases de valor | ✅ Integrado |
| **Prompt Smith** | Engenharia e refinamento incremental de prompts | ✅ Integrado |

O ArcSmith nasce do contexto de **workshops de adoção do Microsoft Copilot**, onde a entrega de valor ao cliente passa por duas etapas críticas: **capturar** o que foi construído (case) e **refinar** como foi construído (prompt).

---

## Contexto de uso

O ArcSmith é utilizado dentro de workshops de adoção de Microsoft Copilot como parte da **etapa de cases** — entregas de valor práticas para clientes que demonstram o uso real do Copilot no dia a dia organizacional.

```
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
```

<p align="center">
  <img src="docs/ArcSmith1.png" width="300"/>
</p>

# ⚒️ ArcSmith
> Forge the arc. Smith the prompt.

## Funcionalidades

### 🎯 Arc — Construção do Case
- Recebe o relato de uma entrevista ou conversa com stakeholder
- Extrai problema, contexto, solução e valor gerado
- Estrutura um case pronto para apresentação ao cliente
- Formato padronizado e replicável

### ⚒️ Smith — Engenharia de Prompt
- Recebe instruções do usuário e retorna um Prompt-Base atualizado
- Edição incremental sem perda de coerência
- Saída em formato JSON padronizado (pt-BR)
- Reset explícito via comando de encerramento
- Resolve ambiguidades com bom senso; nunca inventa dados sensíveis

---

## Arquitetura

```
arcsmith/
├── agent/
│   ├── arcsmith.json          # Definição principal do agente (M365 Toolkit)
│   ├── arc-instructions.md    # Instruções do módulo de cases
│   └── smith-instructions.md  # Instruções do módulo de prompts
├── docs/
│   ├── caso-exemplo.md        # Exemplo de case gerado
│   └── prompt-base-exemplo.json  # Exemplo de Prompt-Base gerado
└── README.md
```

---

## Status do projeto

| Módulo | Status |
|---|---|
| Arc (Cases) | 🔨 Em construção |
| Smith (Prompts) | 🔨 Em construção |
| Integração M365 Toolkit | 🔨 Em construção |
| Documentação de exemplos | 📋 Planejado |

---

## Tecnologias

- **Microsoft 365 Copilot** — plataforma de execução
- **M365 Toolkit** — framework de construção do agente
- **JSON** — formato de saída dos prompts estruturados
- **pt-BR** — idioma principal de operação

---

## Autor

Desenvolvido como parte de um ecossistema próprio de engenharia de agentes para workshops de adoção Microsoft Copilot.

> *"Forje o arco da narrativa. Construa o prompt com precisão."*