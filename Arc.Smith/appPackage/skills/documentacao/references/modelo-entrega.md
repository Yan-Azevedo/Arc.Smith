# Modelo: Guia de Criação do Agente

Documento didático, completo e voltado a pessoas leigas, para o cliente recriar e usar a solução no próprio ambiente.

## Capa
- Logo da Cloud Target (cabeçalho).
- Título: Guia de Criação do Agente [Nome do Agente]
- Subtítulo: [Função do agente] | [Cliente]
- Data e Elaborado por: [consultor] | Cloud Target

## Pontos-chave
- O que o agente faz, em uma frase.
- Plataforma e nível: [plataforma] | [Copilot Basic ou Copilot Premium].
- O que é preciso para criar: [licença, permissões, arquivos].
- Sustentação: [nível] e o principal cuidado de manutenção.

## Estrutura

**1. Objetivo deste documento**
O que o guia orienta e quais garantias a solução entrega, em linguagem acessível. Exemplo: "Este documento orienta a criação do agente [Nome] voltado a [função], garantindo:" seguido de 3 a 4 garantias.

**2. Finalidade do agente**
- O que o agente faz, para que serve e que problema resolve.
- O que o agente utiliza: fontes e recursos.
- O que o agente não faz: limites explícitos; o agente apoia, mas não substitui, a decisão e a validação humana.

**3. Lógica de interação com o agente**
Para agentes de fluxo sequencial, cada etapa com:
- O que o usuário deve fazer.
- O que o agente faz.
- Retorno esperado.
- Ação do usuário (confirmação ou próximo passo).
Para agentes de interação livre, os principais tipos de uso.

**4. Criação do agente: passo a passo**
- Plataforma utilizada: [plataforma].
- Etapas de acesso, início da criação e definição de nome e descrição, conforme a plataforma (documentacao-por-tipo-agente.md) e confirmadas no Microsoft Learn MCP.
- Nome e descrição em bloco de cópia.

**5. Instruções do agente**
"Cole integralmente o conteúdo abaixo no campo de Instruções do agente", seguido do Prompt-Base em bloco de cópia, exatamente como gerado pela skill smith-prompt.

**6. Conexão com documentos e fontes de conhecimento**
- 6.1 Fontes internas (prioridade): cada documento com nome e finalidade.
- 6.2 Fontes externas: escopo de busca na web, ou a indicação explícita de que o agente não consulta fontes externas.

**7. Capacidades do agente**
Capacidades a ativar e o benefício prático de cada uma.

**8. Prompts sugeridos**
- 8.1 Prompts padrão: prompts curtos configuráveis como sugestões iniciais; valem para todos os agentes.
- 8.2 Prompt de orientação (só agentes robustos): orientação de uso (quando usar: a cada execução ou na configuração inicial) e o prompt longo em bloco de cópia.

**9. Boas práticas de uso**
Checklist de uso responsável adaptado à solução, por exemplo:
- confirmar as informações apresentadas pelo agente;
- validar manualmente itens críticos;
- usar apenas fontes e documentos oficiais;
- tratar o resultado como apoio, nunca como decisão final;
- registrar evidências quando aplicável.

**10. Resultado esperado**
O que a organização terá ao final (3 a 4 resultados concretos).

**11. Sustentação da solução**
O que manter depois da criação (fontes, instruções, skills, fluxos, permissões, custo), com que frequência e quem é o responsável sugerido.

**12. Responsabilidade e uso responsável**
A responsabilidade final é sempre humana. O agente opera conforme as regras documentadas, sem assumir decisões ou validações finais, em conformidade com os princípios de uso responsável de IA da Microsoft.
