# Schema do Prompt-Base

O Prompt-Base é o conteúdo que vai para a caixa de instruções do agente. Ele é escrito como JSON, entregue dentro de uma caixa markdown, e a plataforma o lê como texto.

## Template oficial

```
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

## Parâmetros (ordem fixa)

| Ordem | Parâmetro | Conteúdo |
|---|---|---|
| 1 | Goal | Objetivo específico e mensurável do agente: o resultado que ele precisa entregar. |
| 2 | Context | Cenário de aplicação: público-alvo, área, fontes de conhecimento disponíveis e restrições do ambiente. |
| 3 | Instructions | Regras e passos que o agente segue. Uma regra por linha. |
| 4 | Tone | Como o agente se comunica (ex.: formal, consultivo, técnico, didático). Também expressa o grau de precisão ou criatividade esperado. |
| 5 | Format | Estrutura das respostas do agente (ex.: lista, tabela, seções, passo a passo) e nível de detalhe. |
| 6 | Use Case | Situação prática em que o agente é usado, de preferência com um exemplo concreto. |
| 7 | Output | Formato final de saída do agente criado (ex.: markdown, texto, tabela, yaml). Vem da pergunta obrigatória da primeira resposta. |

## Regras de escrita
- Sempre os 7 parâmetros, nesta ordem, mesmo que algum fique curto.
- Valores entre aspas duplas.
- Nunca use `\n` dentro dos valores.
- Texto corrido por padrão. Em Instructions, quando houver várias regras, coloque uma regra por linha, dentro das mesmas aspas:

```
"Instructions": "Regra 1.
Regra 2.
Regra 3."
```

- Esse formato não é JSON estrito, porque tem quebras de linha reais dentro das aspas. Ele é feito para a caixa de instruções, que lê texto. Não o valide com parser JSON.
- Não use Temperature. Em agentes do Microsoft 365 Copilot (Agent Builder e Agents Toolkit) e em agentes do Copilot Studio, o parâmetro não é configurável. Ele existe somente na ferramenta de Prompt do Copilot Studio (prompt builder), como controle de 0 a 1, e fica desabilitado em modelos de raciocínio. O efeito desejado (mais preciso ou mais criativo) é descrito em Tone e Instructions.

## Limite
O bloco inteiro tem no máximo 8.000 caracteres, contando chaves, aspas, quebras de linha e indentação.

## Critérios de saída (Output e Format)
Defina com clareza o que é sucesso para o agente:
- Conteúdo obrigatório: quais informações a resposta deve conter (ex.: "as três principais causas, em ordem de prioridade").
- Formato e estilo: lista, tabela, parágrafos ou outro formato que o agente deve seguir.
- Nível de detalhe: breve ou aprofundado, e limites de escopo.
- Condição de exceção: como o agente reage quando não consegue cumprir a tarefa (ex.: responder "Dados insuficientes para análise" em vez de arriscar um palpite).
