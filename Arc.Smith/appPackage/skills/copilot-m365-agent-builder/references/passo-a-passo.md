# Agent Builder: passo a passo

## Modo Detalhado (configuração manual)
1. No Microsoft 365 Copilot, selecione New agent.
2. Selecione Skip to configure. A aba Configurar abre.
3. Preencha Nome, Descrição e Instruções com as caixas geradas pela skill smith-prompt.
4. Escolha o ícone e, em Model, o modo de resposta.
5. Em Knowledge, adicione as fontes: Search (e-mail, mensagens do Teams), Enter URL (site público, SharePoint ou link do OneDrive), Browse (arquivos, pastas ou listas do SharePoint e OneDrive) ou Upload (arquivos do computador).
6. Ative as capacidades necessárias: "Create documents, charts, and code" e "Create images".
7. Defina "Only use specified sources", se o agente deve priorizar as fontes informadas.
8. Cadastre os prompts sugeridos (nome e descrição).
9. Se o agente tiver skills, em Skills, selecione Add e suba o pacote .zip de cada skill gerado pelo ArcSmith. Revise nome, descrição, instruções e arquivos.
10. Teste na aba Try it e selecione Create.

## Modo Assistente (conversa de criação)
1. No Microsoft 365 Copilot, selecione New agent.
2. Na caixa de mensagem do Agent Builder (aba Describe), cole o briefing gerado (references/criacao-assistida.md).
3. Anexe as fontes específicas pelo botão +.
4. Siga o checklist pós-criação.

## A partir de um modelo
1. Em New agent, escolha um modelo em Start with a template.
2. Refine em linguagem natural ou na aba Configurar e adicione as fontes.

## Teste
- A aba Try it fica disponível quando o agente tem nome, descrição e instruções.
- Ela se comporta como o agente final, exceto por recursos como compartilhar prompts, enviar feedback ou mencionar outros agentes.
- Teste com os prompts sugeridos, com perguntas fora deles e com perguntas cuja resposta está em cada fonte.

## Depois de criado
- O agente pode ser refinado em linguagem natural ou na aba Configurar.
- Para compartilhamento e gestão, consulte o Microsoft Learn MCP (Share and manage agents built in Agent Builder).
- Para adicionar ações, conectores ou fluxos, copie o agente para o Copilot Studio.
