# ForgeProtocol

Metodologia de engenharia de prompt usada pelo Smith para construir o Prompt-Base.

## O que é engenharia de prompt
É a habilidade de escrever instruções estruturadas que direcionam a IA a produzir respostas alinhadas ao objetivo. A estrutura em parâmetros comunica a intenção de forma organizada e aumenta a previsibilidade do comportamento do modelo. É especialmente útil quando precisão e personalização são essenciais, como em documentação técnica, roteiros de aprendizagem e processos padronizados.

## Componentes de um bom prompt
Antes de preencher os parâmetros, levante estes componentes com o usuário:

| Componente | Pergunta que responde | Exemplo |
|---|---|---|
| Tipo de conteúdo | O que será produzido? | relatório, roteiro, resumo, análise |
| Público-alvo | Para quem? | analistas iniciantes, gestores de área |
| Objetivo principal | Qual resultado se espera? | reduzir o tempo de preparação de reuniões |
| Elementos específicos | O que precisa estar presente? | responsáveis, prazos, riscos |
| Características desejadas | Como deve ser apresentado? | conciso, detalhado, visualmente estruturado |
| Critérios de qualidade | Como medir se ficou bom? | acionável, mensurável, sem informação inventada |

## Dos componentes para os parâmetros
| Componente | Parâmetro do Prompt-Base |
|---|---|
| Objetivo principal e critérios de qualidade | Goal |
| Público-alvo, área e fontes | Context |
| Elementos específicos, restrições e passos | Instructions |
| Características desejadas (estilo) | Tone |
| Características desejadas (estrutura) | Format |
| Situação real de uso | Use Case |
| Formato final do agente | Output |

## Delimitadores
| Delimitador | Função |
|---|---|
| `{ }` chaves | Agrupam os parâmetros que configuram o comportamento |
| `" "` aspas duplas | Delimitam o valor de cada parâmetro |
| `[ ]` colchetes | Indicam informação variável ou placeholder a preencher |
| `( )` parênteses | Trazem informação de reforço; use com moderação |
| `:` dois-pontos | Relacionam o parâmetro ao seu valor |

## Processo iterativo
1. Criação inicial do Prompt-Base.
2. Avaliação do resultado gerado pelo agente.
3. Ajuste de Tone, Format e Instructions.
4. Refinamento de Context e dos critérios de saída.
5. Nova rodada até o resultado atender ao Goal.
