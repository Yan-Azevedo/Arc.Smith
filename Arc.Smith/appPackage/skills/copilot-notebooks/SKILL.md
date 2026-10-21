---
name: copilot-notebooks
description: "Orienta a criação de Copilot Notebooks completos: nome, instruções personalizadas (Copilot instructions), referências recomendadas (arquivos, sites, pastas, Pages, reuniões e e-mails), estrutura de uso, saídas geradas e governança. Use quando o usuário pedir um notebook do Copilot ou quando a solução for organizar conhecimento de um projeto ou tema para consultar com o Copilot, sem criar um agente."
---

# Copilot Notebooks

## Objetivo
Entregar um notebook pronto para montar: nome, instruções personalizadas, referências recomendadas e orientação de uso, funcionando quase como um agente focado no conteúdo do notebook.

## Quando usar
- O usuário pede um Copilot Notebook.
- A necessidade é reunir conhecimento de um projeto, tema ou cliente e conversar com o Copilot sobre esse conteúdo, sem configurar um agente.

## Regra absoluta
Consulte o Microsoft Learn MCP e a documentação de suporte antes de afirmar limites e recursos (references/fatos-volateis.md). Limites não documentados, como o tamanho das instruções, não devem ser inventados. Não recomende referências que o usuário não indicou como existentes: peça os arquivos, sites ou pastas reais, ou deixe placeholder.

## Fluxo
1. Entenda o objetivo do notebook, o público e a licença de quem vai usar (Copilot Chat ou Microsoft Copilot).
2. Proponha o nome do notebook.
3. Gere as instruções personalizadas com a skill smith-prompt (Prompt-Base de 7 parâmetros, até 8.000 caracteres, padrão do ArcSmith).
4. Monte a lista de referências recomendadas (references/referencias-recomendadas.md), respeitando o limite e as fontes da licença.
5. Oriente a estrutura de uso e as saídas (references/estrutura-notebook.md).

## Entrega (caixas copiáveis)
- Nome do notebook.
- Copilot instructions (Prompt-Base).
- Referências recomendadas: tabela com referência, tipo e para que serve.
- Perguntas sugeridas para o chat do notebook (orientação de uso; o notebook não tem campo de prompts iniciais).
- Passo a passo de montagem (references/estrutura-notebook.md).

## Regras
- Respeite o limite de referências: 50 no Copilot Chat; mais de 300 no Microsoft Copilot, mas só as 300 primeiras entram no grounding.
- Sem licença do Microsoft Copilot, use só fontes padrão (arquivos, Pages, imagens, áudio e URLs públicas).
- URLs externas precisam ser públicas (sem login, paywall ou subpáginas).
- Avise que notebook excluído não pode ser recuperado e que não há transferência automática de dono.

## Recursos
| Arquivo | Quando carregar |
|---|---|
| references/capacidades-limites.md | Para licença, limites, governança e armazenamento |
| references/estrutura-notebook.md | Para montar o notebook e orientar o uso e as saídas |
| references/instrucoes-modelo.md | Para escrever as Copilot instructions do notebook |
| references/referencias-recomendadas.md | Para escolher e recomendar as referências |
| references/fatos-volateis.md | Ponto de partida para limites; confirmar nas fontes |
