# Copilot Notebooks: capacidades e limites

Verificado em 2026-10-20. Confirme nas fontes antes de afirmar ao usuário.

## Licença e criação
- Disponível para usuários licenciados do Microsoft Copilot e do Copilot Chat. A documentação de administração diverge (NB-01): confirme no tenant.
- Criar notebook exige licença (service plan) de SharePoint ou OneDrive.
- O administrador controla a criação pela Cloud Policy "Create and view Copilot Pages and Copilot Notebooks" (habilitada por padrão).

## Referências
| Item | Copilot Chat | Microsoft Copilot |
|---|---|---|
| Quantidade | Até 50, todas usadas no grounding | Mais de 300; só as 300 primeiras usadas no grounding |
| Fontes | Padrão: PDF, Word, Excel, PowerPoint, Pages, imagens, áudio, URLs externas | Também premium: Teams, SharePoint, OneDrive, URLs internas |
| Entidades | Só URL web | E-mails do Outlook, reuniões do Teams, sites e páginas do SharePoint, pastas |

- Tipos de arquivo: .docx, .pptx, .xlsx, .pdf, .loop, .page, .txt e páginas do OneNote; .rtf e .md aparecem em páginas diferentes da documentação (divergência NB-06). Em breve: .csv, .tsv, .png, .jpg e chats do Teams.
- Reuniões do Teams entram com transcrição, chat e conteúdo compartilhado.
- O Copilot só usa o conteúdo das referências que o usuário tem permissão de acessar.

## Instruções personalizadas
- Ficam no menu ao lado do nome do notebook, em "Copilot instructions"; podem ser editadas a qualquer momento.
- Controlam formato, foco e tom das respostas.
- Quem recebe o notebook compartilhado vê e coedita as instruções.
- Limite de caracteres não documentado; o ArcSmith adota 8.000.

## Armazenamento e governança
- Arquivo .pod em contêiner SharePoint Embedded do usuário, compartilhado com Loop My workspace; conta na cota do SharePoint.
- Sem lixeira: notebook excluído não pode ser recuperado.
- Sem transferência em massa de dono: instruções, referências e Pages são recriadas manualmente.
- Information Barriers não suportado.
- Ao compartilhar, os destinatários são convidados aos arquivos vinculados (é preciso ter permissão de compartilhá-los); as conversas com o Copilot continuam privadas.

Fontes: https://learn.microsoft.com/microsoft-365/loop/cpcn-requirements ; https://learn.microsoft.com/microsoft-365/loop/cpcn-admin-configuration ; https://learn.microsoft.com/microsoft-365/loop/cpcn-compliance-summary ; https://learn.microsoft.com/microsoft-365/loop/grant-access ; https://support.microsoft.com/microsoft-365-copilot/add-references-to-your-microsoft-365-copilot-notebook ; https://support.microsoft.com/microsoft-365-copilot/get-answers-and-insights-about-your-microsoft-365-copilot-notebook ; https://support.microsoft.com/topic/763a9536-d459-4f90-8835-c411863d91ce
