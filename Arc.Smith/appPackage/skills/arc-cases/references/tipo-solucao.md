# Decisão do tipo de solução

O tipo de solução (prompt, agente ou projeto) é raciocínio interno: orienta a classificação e a escolha da plataforma, mas nunca aparece no texto do case. A plataforma de destino é confirmada com a skill da plataforma e com o Microsoft Learn MCP.

## Decisão do Tipo de Solução

Não existe um formato único de solução de IA — pode ser desde um prompt isolado e bem calibrado até um agente completo interagindo com múltiplas ferramentas. A escolha depende das características do case:

- **Prompt estruturado:** quando a necessidade pode ser atendida através de uma interação direta com o modelo de IA generativa. Exemplo: um comando que, dado um texto de entrada, retorna um resumo, uma sugestão de resposta ou uma lista reformatada.
- **Agente integrado:** quando a solução exige vários passos, contexto ou consultas a fontes de dados. Nesse caso, desenvolve-se uma solução de IA integrada a outras ferramentas, como por exemplo um agente no ecossistema de produtividade (e-mail, chat corporativo, etc.), que interaja com o usuário e possivelmente com dados internos antes de gerar o resultado.
- **Projeto dedicado:** se o case selecionado demanda um esforço muito além do tempo ou recursos imediatos (por exemplo, um desenvolvimento de software sob medida ou integração complexa em sistemas corporativos de grande escala), considera-se tratá-lo como um projeto de longo prazo. Nesse caso, o papel do protótipo pode ser validar alguns conceitos e delinear um roadmap para implementação completa futura.

**Critérios técnicos Prompt vs. Agente:**

- **Complexidade da interação:** uma interação pontual (ex.: uma resposta textual única) tende a ser resolvida via prompt; já fluxos com múltiplas perguntas e respostas, ou que necessitam memorizar contexto e interagir ao longo de um diálogo, requerem um agente.
- **Integração com sistemas:** se a solução precisa ler e escrever em sistemas existentes (e-mail, arquivos, banco de dados), um agente (por exemplo, usando serviços de automação) será mais adequado do que somente um prompt.
- **Controle de formato e ações adicionais:** prompts podem produzir textos ou estruturados simples. Se a saída precisa ser pós-processada ou se a solução deve tomar ações concretas (como enviar automaticamente um e-mail), um agente será necessário para encapsular essas funções.
