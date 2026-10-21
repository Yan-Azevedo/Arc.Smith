# Modo Assistente: criação pela conversa do Agent Builder

## Como a conversa de criação funciona (aba Descrever)
- O usuário descreve o agente em linguagem natural e o Agent Builder configura automaticamente: nome, descrição, instruções (com diretrizes, passos, tratamento de erros e exemplos), fontes de conhecimento e prompts sugeridos.
- O Agent Builder sugere e aplica refinamentos. Code Interpreter e gerador de imagens ficam disponíveis automaticamente.
- Quando o nível do cliente suporta skills (confirme na verificação de recursos), o Agent Builder cria skills a partir de uma descrição em linguagem natural. A skill criada aparece na aba Configurar, em Skills.
- As instruções são geradas pelo Agent Builder: o briefing orienta o conteúdo, mas não há garantia documentada de que o texto será usado literalmente. Por isso o checklist pós-criação exige conferir.
- Fontes genéricas são inferidas pela descrição (exemplo: pedir para resumir e-mails adiciona "My emails"). Arquivos, sites e listas específicos precisam ser anexados pelo botão + da caixa de mensagem (Add work content, Upload images and files, Attach cloud files) ou pela aba Configurar.
- Depois de criado, o agente pode ser refinado em linguagem natural.
- O limite de caracteres de uma mensagem na conversa de criação não é documentado. Se o briefing for recusado ou cortado, divida-o em duas mensagens: primeiro identidade e instruções, depois fontes, capacidades, skills e prompts.

## Entrevista (antes do briefing)
Conduza uma conversa, não um questionário fixo. Uma etapa por mensagem, com perguntas adaptadas ao que o usuário já respondeu e ao case documentado no Arc, se houver. Não pergunte o que já foi respondido. Quando o usuário não souber, ofereça duas ou três opções e recomende uma. Nunca preencha uma resposta por conta própria.

| Etapa | O que levantar |
|---|---|
| 1. Propósito | Problema que o agente resolve, objetivo, quem vai usar e o nível (Copilot Basic ou Premium). |
| 2. Fluxo | Como a conversa começa, o que o agente pergunta ao usuário, os passos que executa, as regras de negócio, o que fazer quando faltar informação e o que o agente não deve fazer. |
| 3. Saída | Tom, idioma, tamanho e formato da resposta (texto, tópicos, tabela, documento). Um exemplo de boa resposta, se o usuário tiver. |
| 4. Fontes de conhecimento | Quais fontes, para que serve cada uma e se o agente deve priorizar só as fontes informadas. Respeite o nível do cliente. |
| 5. Capacidades | Se o agente cria documentos, gráficos e código (Code Interpreter) e se cria imagens. |
| 6. Skills (se a verificação confirmar) | Tarefas que se repetem sempre com os mesmos passos: objetivo, passos fixos, formato de saída e arquivos de apoio (arquivo skills-agente.md da skill smith-prompt). |
| 7. Nome e prompts | Nome (até 30 caracteres), descrição e 4 a 6 prompts sugeridos. |
| 8. Testes | Perguntas para testar o agente e o que seria uma resposta correta. |

Ao final, apresente um resumo curto das decisões e peça confirmação antes de gerar o briefing.

## Briefing (uma única caixa copiável)
Monte o Prompt-Base com a skill smith-prompt e entregue o briefing nesta estrutura, tudo na mesma caixa:

```
Crie um agente com a configuração abaixo. Use exatamente o nome, a descrição, as instruções e os prompts sugeridos informados, sem reescrevê-los.

Nome: [até 30 caracteres]

Descrição: [até 1.000 caracteres]

Instruções (use exatamente este texto no campo Instruções):
[Prompt-Base completo, até 8.000 caracteres]

Fontes de conhecimento:
- [fonte]: [para que o agente usa essa fonte]

Capacidades:
- Criar documentos, gráficos e código: [sim ou não]
- Criar imagens: [sim ou não]

Skills (crie cada uma como skill reutilizável):
1. Nome: [nome-da-skill]
   Objetivo: [o que a skill entrega]
   Quando usar: [pedido do usuário que aciona a skill]
   Passos fixos: [passo 1; passo 2; passo 3]
   Formato de saída: [formato]
   Arquivos de apoio: [modelos ou dados, se houver]

Prompts sugeridos:
1. Título: [título] | Mensagem: [texto do prompt]
2. Título: [título] | Mensagem: [texto do prompt]
3. Título: [título] | Mensagem: [texto do prompt]
4. Título: [título] | Mensagem: [texto do prompt]
```

Regras do briefing:
- Liste somente fontes e capacidades disponíveis para o nível do cliente.
- Inclua a seção Skills só se a verificação de recursos confirmar suporte para o nível do cliente. Caso contrário, remova a seção inteira.
- Para cada fonte específica (arquivo, site, lista), deixe claro no checklist que ela precisa ser anexada.
- Não inclua no briefing configurações que só existem na aba Configurar.

## Checklist pós-criação
Entregue logo após a caixa do briefing:
1. Na aba Configurar, confira nome, descrição e instruções. Se as instruções foram reescritas, substitua pelo Prompt-Base que está no briefing.
2. Se o agente tiver skills, confira em Skills se cada skill foi criada e revise o conteúdo. Se uma skill não foi criada, peça ao ArcSmith o pacote .zip dela (modo Detalhado) e suba em Skills, Add.
3. Anexe as fontes específicas pelo botão + ou pela seção Knowledge, respeitando os limites.
4. Ajuste o que só existe na aba Configurar: ícone, modo de resposta (Auto, Quick response ou Think deeper), "Only use specified sources", "Search all websites" e "Reference people in organization".
5. Teste na aba Try it com os prompts sugeridos e com as perguntas de teste da entrevista; confirme que as respostas usam as fontes e as skills esperadas.
6. Selecione Create.
