# Agent Builder: capacidades e limites

Valores verificados em 2026-10-19. Confirme no Microsoft Learn MCP antes de afirmar ao usuário.

## Campos do agente (aba Configurar)
| Campo | Regra |
|---|---|
| Nome | Até 30 caracteres. Descritivo e único. |
| Ícone | PNG, até 192 x 192 pixels e 1 MB. Pode ser gerado por IA, escolhido na biblioteca ou enviado. |
| Model (modo de resposta) | Auto (padrão), Quick response ou Think deeper. O usuário pode trocar ao usar o agente. |
| Descrição | Até 1.000 caracteres. Ajuda o modelo a identificar quando usar o agente e aparece para os usuários. Curta, precisa e simples. |
| Instruções | Até 8.000 caracteres. Na aba Descrever, são geradas automaticamente. |
| Conhecimento | Sites públicos, conteúdo de trabalho, arquivos enviados e conectores. Limites por tipo abaixo. |
| Prompts sugeridos | Cada um com nome e descrição. Sem mínimo documentado. |

## Fontes de conhecimento (limite por agente)
| Fonte | Limite e regras |
|---|---|
| Sites públicos | 4 URLs. No máximo dois níveis de caminho e sem parâmetros de consulta. Para usar qualquer site, ative "Search all websites". |
| SharePoint (arquivos, pastas, sites) | 100 arquivos. URL com o caminho do site (/sites/nome) e sem parâmetros. Um site não inclui as listas dele. |
| Listas do SharePoint | 1 lista, até 20.000 itens e 50 MB de texto. Anexos da lista não são usados. |
| OneDrive | 50 arquivos, por link compartilhável. |
| Teams | 5 chats e 5 reuniões, ou "My Teams chats and meetings" (todo o histórico e o calendário). |
| Outlook | "My emails": todo o e-mail da caixa, sem escopo. Quem recebe o agente compartilhado não acessa o e-mail de quem criou. |
| Arquivos enviados (embedded) | 20 arquivos. .doc, .docx, .pdf, .ppt, .pptx e .txt até 512 MB; .xls e .xlsx até 30 MB. Não aceita pastas, arquivos com senha, com Double Key Encryption ou rótulos com permissões definidas pelo usuário. |
| Conectores do Copilot | Sem limite numérico documentado. O administrador precisa habilitar. |
| Dynamics 365 e Power Apps | Sem limite numérico documentado. Exige "Business Applications in Work IQ" habilitado. Somente leitura. |

Observações:
- "Only use specified sources" prioriza as fontes informadas nas perguntas de busca, mas não bloqueia o conhecimento geral do modelo. Para controle mais rígido, use o Copilot Studio.
- Arquivos recém-enviados ao SharePoint ou OneDrive ficam em "Preparing" por alguns minutos e só entram nas respostas quando prontos.
- Excel funciona melhor com os dados em uma única planilha.
- A pesquisa restrita do SharePoint (Restricted SharePoint Search), se habilitada, impede usar o SharePoint como fonte.

## Capacidades
| Capacidade | Como ativar |
|---|---|
| Code Interpreter | "Create documents, charts, and code" |
| Gerador de imagens | "Create images" |
| Skills (preview) | Disponibilidade por nível em mudança: confirmar na verificação de recursos. Na última verificação, a página do Learn citava licença ou cobrança por consumo e Frontier Program. Pela descrição em linguagem natural (modo Assistente) ou por pacote .zip de até 50 MB na aba Configurar, Skills, Add (modo Detalhado). Até 8 por agente, 25 MB por arquivo, 350 arquivos no total e profundidade 3. Não combina com arquivos enviados (embedded) nem funciona com Purview Information Barriers. |

Não disponível no Agent Builder: ações que integram serviços externos. Para isso, copie o agente para o Copilot Studio.

## Níveis
- **Copilot Premium** (licença do Microsoft 365 Copilot ou cobrança por consumo ativa): todas as fontes acima. Exceção documentada: e-mail, pessoas, chats e reuniões do Teams como fonte exigem a licença do Microsoft 365 Copilot; só a cobrança por consumo não libera essas fontes.
- **Copilot Basic** (Copilot Chat sem licença): ver a skill copilot-chat.

## Disponibilidade
- A experiência em linguagem natural (aba Descrever) aceita os idiomas suportados pelo Microsoft 365 Copilot, inclusive português do Brasil.
- Disponível em GCC e GCCH, com restrições (em GCC não há arquivos enviados como fonte).

Fontes: https://learn.microsoft.com/microsoft-365/copilot/extensibility/agent-builder-build-agents ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/agent-builder-add-knowledge ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/agent-builder-regional-availability ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/prerequisites
