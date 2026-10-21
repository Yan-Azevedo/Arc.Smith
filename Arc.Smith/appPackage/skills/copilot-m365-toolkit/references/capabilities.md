# Capabilities do agente declarativo

Schema 1.8, verificado em 2026-10-20. No máximo uma capability de cada tipo.

| Capability | Configuração | Observações |
|---|---|---|
| WebSearch | sites (opcional) | A doc indica até 4 sites; 10 foram provisionados com sucesso no projeto Marchtron. URL com no máximo dois segmentos de caminho e sem parâmetros. Sem sites, pesquisa toda a web. |
| OneDriveAndSharePoint | items_by_url ou items_by_sharepoint_ids | Sem nenhum dos dois, acessa todo o conteúdo que o usuário pode ver. Use o caminho completo do item. |
| GraphConnectors | connections (connection_id e filtros) | Sem connections, acessa todos os conectores da organização. Filtros por KQL, ID, URL, caminho ou contêiner. |
| GraphicArt | sem parâmetros | Gerador de imagens. Indisponível em GCCH. |
| CodeInterpreter | sem parâmetros | Executa Python, gera gráficos e arquivos para download. |
| Dataverse | knowledge_sources (host_name, skill, tables) | O identificador skill é obtido publicando um agente no Copilot Studio e baixando o .zip. |
| TeamsMessages | urls (opcional) | Até 5 URLs de canais, chats ou reuniões. Sem urls, pesquisa todos. |
| Email | shared_mailbox, group_mailboxes, folders | Somente leitura. Até 25 caixas de grupo ou compartilhadas. |
| EmailActions | sem parâmetros | Schema 1.8. Escrita em e-mail (triagem, envio supervisionado, regras, resposta automática, pastas). Não herda o escopo de Email. |
| People | include_related_content | Dados de pessoas; com true inclui documentos, e-mails e mensagens em comum. |
| ScenarioModels | models (id) | Modelos específicos de tarefa. |
| Meetings | items_by_id (opcional) | Até 5 reuniões. Sem itens, pesquisa todas. |
| MeetingActions | sem parâmetros | Schema 1.8. Agendamento, enquetes de horário e insights de agenda. |
| EmbeddedKnowledge | files | Até 10 arquivos de até 1 MB (.doc, .docx, .ppt, .pptx, .xls, .xlsx, .txt, .pdf). Não combina com skills no preview. |

Regra de licença: usuários sem licença só acessam capabilities além de WebSearch com cobrança por consumo habilitada ou com licença.

Fonte: https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-manifest-1.8
