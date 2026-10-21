# Copilot Studio: pipeline de captura de dados

Padrão validado em projetos do autor (Notedy e Lessons Learned), combinado com a documentação oficial dos fluxos de agente. Confirme no Microsoft Learn MCP os pontos de plataforma.

## Arquitetura padrão
1. Conversa livre com o usuário, guiada pelas instruções do agente.
2. O agente apresenta um PREVIEW do registro e pergunta se pode registrar, e para nessa resposta.
3. Em um turno separado, após a confirmação, o agente responde iniciando com a frase de registro.
4. Um tópico captura a resposta gerada e chama o fluxo de agente.
5. O fluxo extrai os campos em JSON com um prompt (modelo com saída em esquema JSON) e grava em SharePoint (Criar item) ou Dataverse.

## Regras críticas
- Confirmação e registro em turnos separados: se aparecerem na mesma resposta, a captura quebra.
- Tópico de início da captura: gatilho por descrição explícita da confirmação; ao confirmar, define uma variável global (exemplo: Global.CanCapture = true).
- Tópico de captura: gatilho "Resposta gerada por IA" com condição na variável global; captura Response.FormattedText, zera a variável e chama o fluxo.
- Só String, Number e Boolean passam entre o agente e o fluxo.
- Prompt com saída em esquema JSON dispensa o nó Parse JSON.
- O fluxo precisa responder em até 100 segundos; para aprovações longas, use padrão assíncrono.
- Crie o fluxo a partir do tópico ("Adicionar ferramenta", "novo fluxo do agente") para já nascer conectado.

## Limitações conhecidas
- Não existe variável de sistema com o histórico completo da conversa.
- System.LastMessage.Text traz só a última mensagem do usuário.
- Frases de gatilho disparam só com mensagens do usuário.
- O nó "Criar respostas generativas" é baseado em busca (RAG), não usa o histórico da conversa e pode salvar a resposta em variável (Avançado, "Save bot response as").

## Custos
- Prompt e fluxo consomem Copilot Credits para usuários sem licença do Microsoft 365 Copilot (references/licenciamento-creditos.md). Documente esse custo na entrega.

Fontes: https://learn.microsoft.com/microsoft-copilot-studio/flow-agent ; https://learn.microsoft.com/microsoft-copilot-studio/advanced-use-flow ; https://learn.microsoft.com/microsoft-copilot-studio/nlu-prompt-node ; https://learn.microsoft.com/microsoft-copilot-studio/nlu-boost-node
