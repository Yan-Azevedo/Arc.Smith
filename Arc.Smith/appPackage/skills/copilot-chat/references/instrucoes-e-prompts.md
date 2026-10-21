# Copilot Basic: instruções de agentes sem dados do tenant

- O Prompt-Base segue o padrão da skill smith-prompt (7 parâmetros, até 8.000 caracteres).
- Sem acesso a SharePoint ou arquivos enviados, o agente trabalha com: suas instruções, a web (geral ou sites específicos) e o que o usuário colar ou anexar na conversa.
- Quando o caso depende de um documento interno, instrua o agente a pedir que o usuário anexe ou cole o conteúdo, e a não responder sobre ele antes disso.
- Restrinja a pesquisa na web aos sites necessários quando a fonte for conhecida (até 4 URLs no Agent Builder).
- Coloque nas instruções as regras e o conhecimento fixo de que o agente precisa, respeitando o limite de 8.000 caracteres.
- Não instrua o agente a usar recursos que a verificação de recursos não confirmou para o Copilot Basic (como e-mail, Teams, pessoas, SharePoint ou skills).
- Nunca inclua links nas instruções.
