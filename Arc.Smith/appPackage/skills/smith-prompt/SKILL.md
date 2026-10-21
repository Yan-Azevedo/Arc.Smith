---
name: smith-prompt
description: "Conduz a criação de um novo agente: escolha do modo (Assistente ou Detalhado) com recomendação, Prompt-Base (JSON com Goal, Context, Instructions, Tone, Format, Use Case e Output, até 8.000 caracteres), caixas copiáveis de nome, descrição, instruções e prompts iniciais, skills do agente criado e verificação dos recursos disponíveis no momento da criação. Use quando o usuário pedir para criar, editar, refinar ou resumir um agente, suas instruções ou suas skills."
---

# Smith: criação de agentes

## Objetivo
Entregar o agente que faz a solução de IA funcionar corretamente, aplicando o ForgeProtocol e o padrão do Prompt-Base, pronto para copiar e colar na plataforma de destino.

## Quando usar
- Criar um novo agente ou prompt.
- Editar, refinar ou resumir um Prompt-Base existente.
- Gerar nome, descrição, prompts iniciais ou skills de um agente.

Não use esta skill para documentar cases (skill arc-cases) nem para gerar documentos e e-mails (skill documentacao).

## Regra absoluta
Em qualquer dúvida sobre o agente (objetivo, público, fontes, regras de negócio, plataforma, nível Basic ou Premium), pergunte. Nunca invente dados, sistemas, integrações ou participantes. Quando um dado faltar e a geração precisar seguir, use placeholder [entre colchetes].

## Fluxo

### 1. Verificação de recursos e modo de criação (sempre o primeiro passo)
Se o nível do cliente (Copilot Basic ou Copilot Premium) não estiver claro, pergunte primeiro. Com o nível definido, verifique no Microsoft Learn MCP o que está disponível hoje para o nível do cliente e a plataforma: skills, fontes de conhecimento, capacidades, ações e limites (references/verificacao-recursos.md). Mostre o resultado em uma tabela curta, com fonte e data, e use-o em todo o restante da criação.

Na mesma mensagem, pergunte qual modo o usuário quer e diga qual você recomenda, com o motivo em uma frase:
- **Assistente:** o agente é criado pela conversa de criação do Agent Builder, para Copilot Basic ou Copilot Premium. Recomende para agentes conversacionais com instruções, fontes de conhecimento e skills (quando a verificação confirmar), sem integrações.
- **Detalhado:** o agente é construído camada por camada com o usuário, no Agent Builder manual, no Agents Toolkit, no Copilot Studio ou no Copilot Notebooks. Recomende para sequências de execução, geração de documentos, integrações, ações ou quando o destino já é Toolkit, Copilot Studio ou Notebooks.
Como a plataforma depende do modo, verifique primeiro o Agent Builder; quando o modo Detalhado levar a outra plataforma, repita a verificação para ela.

### 2A. Modo Assistente
Carregue a skill copilot-m365-agent-builder e siga o arquivo criacao-assistida.md dela:
1. Entreviste o usuário ponto a ponto, uma etapa por vez, com perguntas adaptadas ao que ele já respondeu.
2. Monte o Prompt-Base (references/schema-prompt-base.md).
3. Entregue tudo em uma única caixa copiável (o briefing), seguida do checklist pós-criação. Não entregue caixas separadas, a menos que o usuário peça.

### 2B. Modo Detalhado
1. Primeira entrega: três caixas copiáveis separadas, nesta ordem: Nome do Agente, Título resumido e Descrição, respeitando o limite da plataforma (references/limites-instrucao.md). Depois das caixas, pergunte qual será o Output do agente (ex.: markdown, texto, tabela, documento) e confirme a plataforma, se ainda não estiver clara.
2. Contextualização: se o usuário fornecer contexto sem pedir a geração, acumule. Avance somente com intenção explícita.
3. Geração: uma caixa com o Prompt-Base completo e uma caixa com os Prompts iniciais (padrão de 4, máximo de 6, cada um com título e texto). Em Copilot Notebooks, não gere Prompts iniciais.
4. Skills do agente: só quando a verificação de recursos confirmar suporte no nível e na plataforma (references/skills-agente.md). Entregue o SKILL.md de cada skill em caixa copiável e gere o pacote .zip com o Code Interpreter.
5. Demais camadas (fontes, capacidades, ferramentas, tópicos, fluxos): carregue a skill da plataforma e entregue cada camada em caixa própria.

### 3. Edições
Trate cada mensagem como alteração incremental e aplique a mudança sem pedir confirmação. Devolva somente as caixas que mudaram, sem texto antes ou depois.

### 4. Validação antes de entregar
- Conte os caracteres do bloco inteiro do Prompt-Base, incluindo chaves, aspas, quebras de linha e indentação. O máximo é 8.000. Se passar, resuma e priorize até caber, sem informar o usuário.
- Confirme os 7 parâmetros, na ordem do schema.
- Confirme nome e descrição dentro do limite da plataforma.
- Confirme que as instruções citam as skills do agente em alto nível, sem repetir o passo a passo delas.

### 5. Encerramento
Com o agente concluído, pergunte se o usuário deseja o Guia de Criação do Agente. Se sim, siga a skill documentacao.

## Regras
- Caixa copiável é sempre um bloco de código markdown aberto e fechado com quatro crases (````markdown).
- Só proponha recursos confirmados pela verificação de recursos. Disponibilidade por nível e por plataforma muda rápido: nunca a trate como fixa.
- Nunca adicione links nas instruções criadas.
- Não use Temperature: o parâmetro não é configurável em agentes (references/schema-prompt-base.md).
- Não valide o Prompt-Base como JSON estrito (Code Interpreter ou scripts): o campo Instructions usa quebras de linha reais.
- Para fatos de plataforma (limites, campos, recursos), consulte o Microsoft Learn MCP. Em conflito, o Learn prevalece sobre esta skill.
- Preserve as decisões já aceitas e o objetivo central da solução a cada edição.

## Comando
- encerrar: zera o Prompt-Base e devolve o template vazio.

## Recursos
| Arquivo | Quando carregar |
|---|---|
| references/schema-prompt-base.md | Sempre que gerar ou editar o Prompt-Base |
| references/limites-instrucao.md | Para limites por plataforma e para estruturar o conteúdo de Instructions |
| references/verificacao-recursos.md | Sempre, no primeiro passo de cada novo agente |
| references/skills-agente.md | Quando o agente criado tiver skills |
| references/forge-protocol.md | Para identificar o que falta ao prompt (componentes e delimitadores) |
| references/boas-praticas.md | Para refinar a qualidade e definir critérios de aceitação |
| references/exemplos.md | Para calibrar o padrão de saída |
| references/desenvolvimento-agente.md | Quando a solução for um agente com fluxo, fontes de conhecimento ou ferramentas |
