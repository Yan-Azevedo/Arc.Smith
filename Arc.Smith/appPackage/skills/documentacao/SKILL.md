---
name: documentacao
description: "Gera os documentos .docx do ArcSmith no modelo fixo e com o brandbook de IA da Cloud Target: Seleção de Cases (vários cases, para decisão), Documento do Case (case único ou escolhido) e Guia de Criação do Agente, adaptado a cada plataforma. Sempre pergunta antes de gerar. Também prepara a formalização: e-mail criado como rascunho no Outlook, nunca enviado, e mensagem do Teams em caixa copiável. Use ao final do Arc ou do Smith, nos comandos gerar discovery ou gerar entrega, ou quando o usuário pedir um documento ou a formalização."
---

# Documentação de entrega

## Objetivo
Gerar documentos .docx prontos para entregar ao cliente, com estrutura fixa, formatação padronizada e conteúdo fiel ao que foi construído.

## Quando usar
- Ao final do Arc: depois do relatório de seleção ou da documentação do case, pergunte se o usuário deseja o documento. Se sim, gere no modelo.
- Ao final do Smith: depois de criado o agente, pergunte se o usuário deseja o Guia de Criação. Se sim, gere no modelo.
- Comando gerar discovery: gera a Seleção de Cases (vários cases ainda sem escolha) ou o Documento do Case (case único ou já escolhido).
- Comando gerar entrega: gera o Guia de Criação do Agente.
- Formalização com o cliente depois da call de discovery: e-mail e mensagem do Teams.

## Regra absoluta
Nunca invente dados do cliente, cases, fontes, caminhos de tela ou botões. Se faltar informação, pergunte antes de gerar. Passos de criação na plataforma devem ser confirmados no Microsoft Learn MCP (e na skill da plataforma) no momento da geração.

## Fluxo: documentos do Arc
1. Pergunte se o usuário deseja o documento. Só siga com a confirmação.
2. Escolha o modelo: vários cases sem escolha do cliente, references/modelo-selecao.md; case único ou escolhido, references/modelo-case.md.
3. Colete o que faltar: nome do cliente, área ou sessão, data da reunião e consultor responsável.
4. Use os cases já documentados pela skill arc-cases; não reescreva o conteúdo.
5. Aplique references/regras-formatacao.md e gere o .docx com o Code Interpreter pelo script scripts/brand_docx.py, no padrão do brandbook.
6. Entregue o arquivo para download e ofereça preparar o e-mail de formalização.

## Fluxo: Guia de Criação
1. Pergunte se o usuário deseja o Guia de Criação. Só siga com a confirmação.
2. Identifique a plataforma: Copilot Chat, Agent Builder, Agents Toolkit, Copilot Studio ou Copilot Notebooks.
3. Colete o que faltar: cliente, nome e função do agente, finalidade, lógica de interação, instruções (Prompt-Base da skill smith-prompt), fontes de conhecimento, capacidades, skills, sustentação e se o agente é robusto o suficiente para precisar do prompt de orientação (seção 8.2).
4. Carregue a skill da plataforma e consulte o Microsoft Learn MCP para o passo a passo atualizado.
5. Adapte as seções conforme references/documentacao-por-tipo-agente.md.
6. Monte o documento na estrutura de references/modelo-entrega.md.
7. Aplique references/regras-formatacao.md, com bloco de cópia em todo conteúdo para copiar e colar, e gere o .docx com o Code Interpreter pelo script scripts/brand_docx.py.
8. Entregue o arquivo para download.

## Fluxo: formalização
A formalização acontece depois da call de discovery, sempre com um documento anexo:
- Um case: e-mail com o documento do case.
- Vários cases: primeiro e-mail com o documento de seleção; depois da decisão do cliente, novo e-mail com o documento do case escolhido.

1. Colete o que faltar: destinatários, pessoas em cópia e o nome do documento que irá anexo.
2. Escreva o e-mail completo: assunto, saudação, contexto da call, resumo do que foi decidido ou do que o cliente precisa decidir, próximos passos e encerramento. Sem assinatura: o Outlook do usuário aplica a dele.
3. Com `EmailActions`, crie o e-mail como rascunho no Outlook do usuário. Nunca envie, mesmo que o usuário peça para enviar direto: o envio é sempre do usuário.
4. Se não for possível criar o rascunho, entregue destinatários, assunto e corpo em caixa copiável.
5. Avise o usuário para revisar, anexar o documento e enviar.
6. Se o usuário pedir uma mensagem para o Teams, entregue em caixa copiável: o ArcSmith não envia mensagens no Teams.

## Regras
- Sempre pergunte antes de gerar um documento.
- Todo documento leva o logo da Cloud Target, o nome do cliente, título, subtítulo, data, pontos-chave e segue o brandbook de IA (references/regras-formatacao.md).
- Linguagem didática e acessível no Guia de Criação; objetiva na Seleção de Cases e no Documento do Case.
- Mantenha as instruções exatamente como geradas pela skill smith-prompt.
- Seção 3 (lógica de interação): etapa por etapa para agentes de fluxo sequencial; principais tipos de uso para agentes de interação livre.
- Seção 8.2: só para agentes robustos.
- Sem emojis, comentários, instruções de uso ou meta-informações no documento final.
- Se o .docx falhar, ofereça o conteúdo em markdown para o usuário colar no Word e informe a limitação.

## Recursos
| Arquivo | Quando carregar |
|---|---|
| references/modelo-selecao.md | Seleção de Cases (vários cases, antes da escolha do cliente) |
| references/modelo-case.md | Documento do Case (case único ou escolhido) |
| references/modelo-entrega.md | Guia de Criação do Agente |
| references/documentacao-por-tipo-agente.md | Para adaptar o Guia de Criação à plataforma |
| references/regras-formatacao.md | Sempre, antes de gerar qualquer documento (padrão do brandbook, logo e elementos obrigatórios) |
| scripts/brand_docx.py | Para gerar o .docx no padrão do brandbook com o Code Interpreter |
| assets/logo_ct_colorido.png e assets/logo_ct_preto.png | Logos oficiais da Cloud Target (capa e cabeçalho) |
