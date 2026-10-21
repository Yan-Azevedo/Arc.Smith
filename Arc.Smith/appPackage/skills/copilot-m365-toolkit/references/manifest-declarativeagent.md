# declarativeAgent.json e manifest.json

Baseado no schema 1.8 publicado e no uso do schema 1.9 para skills (verificado em 2026-10-20).

## Regras gerais
- Propriedades não reconhecidas invalidam o documento inteiro.
- Strings sem limite próprio: até 4.000 caracteres.
- Strings localizáveis podem usar [[nome_da_chave]].
- O Toolkit resolve $[file('instruction.txt')] e variáveis ${{VAR}} no provision; em um pacote montado à mão, as instruções precisam estar no próprio JSON.

## Propriedades do declarativeAgent.json
| Propriedade | Obrigatória | Regra |
|---|---|---|
| $schema | Não | URL do schema da versão usada |
| version | Sim | Versão do schema (ex.: v1.8; v1.9 para skills) |
| id | Não | Identificador do manifesto |
| name | Sim | Até 100 caracteres. Localizável |
| description | Sim | Até 1.000 caracteres. Localizável |
| instructions | Sim | Até 8.000 caracteres |
| capabilities | Não | No máximo uma de cada tipo (references/capabilities.md) |
| conversation_starters | Não | Até 12. Cada um com text (obrigatório), title e depends_on (exibe o starter só se a capability existir) |
| actions | Não | 1 a 10 plugins, por referência (id e file) ou inline |
| behavior_overrides | Não | suggestions.disabled; special_instructions.discourage_model_knowledge; default_response_mode (Auto, Quick response ou Think deeper; padrão Auto) |
| disclaimer | Não | text com até 500 caracteres, exibido no início da conversa |
| sensitivity_label | Não | Só se aplica com arquivos embedded |
| editorial_answers | Não | url ou answers (até 300 pares), com similarity_thresholds de 0 a 10 |
| worker_agents | Não | Preview. Outros agentes declarativos que este agente pode usar |
| user_overrides | Não | Permite ao usuário desligar capabilities; única ação: remove |
| agent_skills | Não | Schema 1.9. Lista de objetos com folder (ex.: skills/nome-da-skill), registrados pelo atk add skill |

## Exemplo mínimo
```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/copilot/declarative-agent/v1.8/schema.json",
  "version": "v1.8",
  "name": "[Nome do agente]",
  "description": "[Descrição do agente]",
  "instructions": "$[file('instruction.txt')]",
  "conversation_starters": [
    { "title": "[Título]", "text": "[Prompt]" }
  ],
  "behavior_overrides": {
    "default_response_mode": "Auto"
  }
}
```

## manifest.json (app manifest)
- Referencia o agente em copilotAgents.declarativeAgents (id e file).
- version do app: suba antes de cada provision; sem isso o Toolkit pode manter o build anterior.
- Preencha name.short, name.full, description.short e description.full: os placeholders do modelo aparecem para o usuário.
- Ícones: color.png e outline.png.

Fontes: https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-manifest-1.8 ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/build-declarative-agents-customize-behavior
