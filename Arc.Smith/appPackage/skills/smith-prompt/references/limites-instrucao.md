# Limites e estrutura das instruções

## Limite padrão do ArcSmith
O Prompt-Base tem no máximo 8.000 caracteres em qualquer plataforma, contando o bloco inteiro. Esse é o limite documentado da caixa de instruções no Agent Builder, no Agents Toolkit e no Copilot Studio, e é adotado também onde a plataforma não documenta limite.

## Limites por plataforma (verificados em 2026-10-19)
Antes de afirmar um limite ao usuário, confirme no Microsoft Learn MCP: estes valores mudam.

| Campo | Agent Builder (Copilot Basic e Premium) | Agents Toolkit | Copilot Studio | Copilot Notebooks |
|---|---|---|---|---|
| Nome | 30 caracteres | 100 caracteres | 42 caracteres, sem < e > | Não documentado |
| Descrição | 1.000 caracteres | 1.000 caracteres | 1.024 caracteres | Não existe o campo |
| Instruções | 8.000 caracteres | 8.000 caracteres | 8.000 caracteres | Não documentado; usar 8.000 |
| Prompts iniciais | Título e descrição, sem mínimo | Até 12 (schema 1.8); padrão do ArcSmith: no máximo 6 | Verificar no Learn | Não existe o campo |

Fontes: Agent Builder (learn.microsoft.com/microsoft-365/copilot/extensibility/agent-builder-build-agents), schema do agente declarativo (declarative-agent-manifest), Copilot Studio (microsoft-copilot-studio/authoring-first-bot e requirements-quotas), Copilot Notebooks (support.microsoft.com, Provide custom instructions).

## Como resumir quando passar de 8.000
Corte nesta ordem, até caber:
1. Repetições e frases redundantes.
2. Exemplos longos (substitua por um exemplo curto).
3. Explicações de contexto que não mudam o comportamento.
4. Detalhes de formato que já estão claros em Format.
Nunca corte: o Goal, as regras críticas de Instructions e as condições de exceção.

## Como escrever o conteúdo de Instructions
Orientações da Microsoft para instruções de agentes:
- Foque no que o agente deve fazer, não no que deve evitar.
- Use verbos precisos e observáveis: perguntar, buscar, enviar, verificar, usar.
- Uma ação por regra: quebre regras compostas em regras separadas.
- Passos em sequência somente quando a ordem importa. Para tarefas independentes, regras soltas.
- Regras de decisão explícitas: "Se X, faça Y. Se Z, faça W."
- Especifique sempre tom, nível de detalhe e formato de saída.
- Defina termos e siglas próprios da organização no próprio texto.
- Cite ferramentas e fontes pelo nome exato. No Copilot Studio, referencie ferramentas, tópicos e variáveis com "/".
- Inclua uma autoavaliação final: antes de responder, o agente confere se cumpriu Goal, Format e Instructions.
- Não altere o comportamento de citações da plataforma (Copilot Studio).
- Quando o agente apresentar desvios, uma regra de leitura literal estabiliza o comportamento: interpretar as instruções literalmente, não inferir requisitos, não reordenar passos.
- Nunca adicione links.
