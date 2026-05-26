# ForgeProtocol
### Base de Conhecimento do ArcSmith — Engenharia de Prompt

> Documento de referência para criação, refinamento e padronização de prompts estruturados em JSON para agentes de IA no Microsoft Copilot e Copilot Studio.

## O que é Engenharia de Prompt

Engenharia de Prompt é a habilidade de criar instruções cuidadosamente estruturadas que direcionam a IA a produzir respostas alinhadas aos objetivos do usuário. A abordagem utiliza sintaxe JSON como base, oferecendo estrutura lógica e organizada para comunicar intenções de forma eficaz ao modelo.

O uso de delimitadores e parâmetros bem definidos aumenta o controle sobre o comportamento do LLM, maximizando sua eficiência e previsibilidade. Essa habilidade é especialmente valiosa em cenários onde precisão e personalização são essenciais:

- Criação de documentações técnicas sobre sistemas
- Criação de roteiros de aprendizagem didáticos
- Elaboração de modelos de negócio baseados em IA

---

## Estrutura Principal do Prompt

### Sessão Base

| Componente | Descrição | Exemplo |
|---|---|---|
| Tipo de Conteúdo | Define o formato ou categoria do que se deseja criar | "artigo técnico", "plano de aula", "roteiro de podcast" |
| Público-alvo | Especifica para quem o conteúdo se destina | "desenvolvedores iniciantes", "gestores de marketing" |
| Objetivo Principal | Determina o resultado que se deseja alcançar | "compreender conceitos avançados de programação" |
| Elementos Específicos | Detalha premissas que devem ser contempladas | "estudos de caso", "código comentado", "exercícios práticos" |
| Características Desejadas | Define como os elementos devem ser apresentados | "conciso", "detalhado", "visualmente estruturado" |
| Critérios de Qualidade | Estabelece métricas para avaliar o resultado | "acionável", "mensurável", "alinhado às melhores práticas" |

### Sessão de Refinamento

| Parâmetro | Função | Observações |
|---|---|---|
| Temperature | Controla a aleatoriedade e criatividade das respostas | 0.0–0.3: técnico e preciso; 0.4–0.6: educativo balanceado; 0.7–1.0: criativo e divergente |
| Goal | Detalha o objetivo específico da interação | Deve ser claro, específico e mensurável quando possível |
| Tone | Define o tom de comunicação | Adapte conforme o público e contexto |
| Format | Especifica a estrutura do conteúdo | Determine previamente para garantir organização adequada |
| Use Case | Exemplifica o contexto de utilização | Fornece referência concreta para calibrar a resposta |
| Context | Adiciona informações de fundo relevantes | Amplia a compreensão do sistema sobre o universo da requisição |
| Instructions | Fornece diretrizes específicas | Detalha requisitos não capturados nos outros campos |
| Output | Define o formato de saída do agente criado | Nunca altera o formato do Prompt-Base, que é sempre JSON |

---

## Elementos de Sintaxe e Delimitadores

| Delimitador | Função |
|---|---|
| `{ }` chaves | Indicam parâmetros que configuram o comportamento do sistema |
| `( )` parênteses | Apresentam informações de reforço (uso limitado recomendado) |
| `" "` aspas duplas | Enfatizam texto específico ou isolam termos importantes |
| `[ ]` colchetes | Indicam informação variável que muda conforme o contexto |
| `: ou =` | Estabelecem relação de igualdade para definir variáveis ou termos-chave |

---

## Resumo dos Parâmetros

**Prompt:** Descreva de forma objetiva para resposta assertiva. Inclua tema, contexto, fontes e todas as informações relevantes.

**Temperature:** Controla o nível de criatividade da IA.
- `0.0–0.3` Ideal para conteúdos técnicos e instruções que exigem precisão
- `0.4–0.6` Equilibrado, serve para explicações claras com leve flexibilidade
- `0.7–1.0` Criatividade aberta, ideal para publicidade e conteúdo criativo

**Goal:** Direcione o resultado final esperado — informar, treinar, orientar, persuadir, simplificar. Isso ajuda a IA a estruturar a resposta de acordo com o propósito.

**Tone:** Defina como o conteúdo deve soar — formal, consultivo, amigável, técnico, persuasivo.

**Persona:** Em cenários corporativos, indicar uma persona (instrutor, consultor, analista) mantém consistência e eleva a qualidade das respostas.

**Format:** Indique o formato exato — markdown, lista estruturada, tabela, introdução–desenvolvimento–conclusão.

**Use Case:** Forneça exemplos ou modelos que representem o estilo desejado. Servem como referência para a IA ajustar a apresentação sem alterar o raciocínio.

**Context:** Descreva o cenário de aplicação, incluindo público-alvo, área envolvida, objetivo e perspectiva. Quanto mais claro o contexto, mais alinhada será a resposta final.

**Instructions:** Inclua orientações adicionais — restrições, preferências, passos específicos ou detalhes que complementem as seções anteriores.

---

## Estrutura Básica do Prompt JSON

```json
{
  "Prompt": "Crie um [tipo de conteúdo] especializado que ajude [público-alvo] a alcançar [objetivo principal]. O conteúdo deve incluir [elementos específicos necessários], garantindo que seja [características desejadas]. Certifique-se de que cada parte seja [critérios de qualidade].",
  "Parameters": {
    "Temperature": "[valor entre 0 e 1]",
    "Goal": "[Descrição detalhada do objetivo a ser alcançado]",
    "Tone": "[Tom desejado: profissional, educativo, motivacional, técnico]",
    "Format": "[Formato do conteúdo: tabela, lista, texto corrido, roteiro]",
    "Use Case": "[Situação em que esse conteúdo será utilizado]",
    "Context": "[Informações adicionais que ajudam a fornecer uma resposta mais precisa]",
    "Instructions": "[Diretrizes específicas: critérios de qualidade, estrutura esperada, elementos obrigatórios]"
  }
}
```

---

## Exemplos

### Exemplo 1 — Treinamento sobre 7 Leis de Uso da IA

```json
{
  "Prompt": "Desenvolva um treinamento completo que ajude profissionais a compreender e apresentar as 7 Leis de Uso da Inteligência Artificial. O conteúdo deve incluir orientações claras sobre cada lei, exemplos aplicados ao contexto corporativo, materiais de apoio visuais, dinâmicas de grupo e estratégias para facilitar discussões. Garanta que o treinamento seja acessível para públicos diversos, incentive o uso responsável da IA e ofereça métricas de avaliação do aprendizado.",
  "Parameters": {
    "Temperature": 0.4,
    "Goal": "Criar um treinamento estruturado que permita apresentar e ensinar as 7 Leis de Uso da IA de forma clara, ética e aplicável",
    "Tone": "Profissional, educativo, motivador",
    "Format": "Roteiro detalhado de treinamento com módulos, objetivos, conteúdos, atividades, materiais e formas de avaliação",
    "Use Case": "Facilitadores utilizarão este roteiro para conduzir formações internas sobre o uso responsável da IA",
    "Context": "Profissionais de diferentes áreas precisam entender como aplicar as leis da IA na prática, evitando riscos e promovendo inovação segura",
    "Instructions": "Inclua pelo menos uma dinâmica colaborativa por módulo, materiais visuais recomendados e sugestões de adaptação para treinamentos online"
  }
}
```

### Exemplo 2 — Guia Jurídico para Estagiários

```json
{
  "Prompt": "Crie um guia detalhado que ajude estagiários do setor jurídico a elaborar relatórios de casos no âmbito imobiliário seguindo um formato oficial padronizado. O conteúdo deve incluir explicação clara de cada seção obrigatória do relatório, além de exemplos práticos, orientações de boas práticas e alertas sobre erros comuns. Certifique-se de que cada parte seja replicável, objetiva e juridicamente precisa.",
  "Parameters": {
    "Temperature": 0.2,
    "Goal": "Capacitar estagiários jurídicos a produzir relatórios padronizados, consistentes e tecnicamente adequados sobre casos imobiliários",
    "Tone": "Formal, instrutivo, técnico",
    "Format": "Guia passo a passo com modelo de relatório, explicações de cada seção e exemplos aplicados ao direito imobiliário",
    "Use Case": "Estagiários que precisam redigir relatórios jurídicos para advogados responsáveis",
    "Context": "Relatórios jurídicos são documentos essenciais para acompanhamento de casos, tomada de decisão e comunicação interna em departamentos jurídicos",
    "Instructions": "Inclua um modelo estrutural baseado em padrões oficiais, exemplos comentados, alertas de riscos jurídicos e orientações para adaptação a contextos administrativos e processuais diferentes"
  }
}
```

---

## Boas Práticas

- Seja específico — prompts vagos geram respostas vagas
- Contextualize objetivo e público-alvo
- Use voz imperativa nas instruções
- Ajuste a Temperature conforme o tipo de conteúdo
- Itere com base no resultado — engenharia de prompt é um processo contínuo
- Personalize tom e formato para cada cenário
- Documente prompts eficazes para reutilização
- Mantenha instruções enxutas — resuma e priorize

---

## Processo Iterativo

1. Criação inicial do prompt
2. Avaliação do resultado gerado
3. Ajuste de parâmetros (Temperature, Tone, Format)
4. Refinamento de contexto e instruções
5. Iteração contínua até alcançar o objetivo

---

## Diretrizes de Operação do ArcSmith

O ArcSmith opera com as seguintes diretrizes comportamentais ao aplicar este protocolo:

**Extreme Ownership:** Assuma responsabilidade pelo resultado final. Não atue como assistente passivo — atue como sócio estratégico sênior.

**Anti-Sycophancy:** Lute ativamente contra o viés de concordância. Se o usuário sugerir algo que comprometa o resultado, discorde e proponha algo melhor. A lealdade é para com a eficiência e o resultado, não com o ego do usuário.

**Chain of Thought:** Recuse respostas superficiais. Quebre solicitações complexas em etapas. Force o usuário a pensar. Faça perguntas difíceis quando necessário.

**Elevação de Nível:** Jamais permita que um input fraco resulte em um output fraco. Compense a falta de clareza do usuário com expertise, frameworks teóricos e lógica rigorosa.

**Obsessão pelo Objetivo:** O sucesso absoluto do projeto é o único objetivo. Use este documento, cruze com conhecimento de mercado e molde o comportamento para ser o consultor mais assertivo e eficaz possível.

---

## Apêndice: Diretrizes para Instruções de Agentes Declarativos

### Objetivo
Fornecer um padrão claro e reutilizável para criar instruções de agente que sejam letais para a ambiguidade, estáveis entre modelos e fáceis de auditar.

### Princípios Gerais
- Use linguagem acionável e direta. Priorize verbos como **perguntar**, **procurar**, **enviar**, **marcar** e **utilizar**.
- Concentre-se no que o agente deve fazer, não no que deve evitar.
- Evite frases vagas como “tratar”, “verificar” ou “lidar com”; prefira ações observáveis.
- Defina termos específicos da organização, abreviações e fórmulas no próprio texto.
- Use Markdown para estruturar a instrução com clareza.

### Estrutura Recomendada
- `##` para seções principais
- `###` para subgrupos de tarefas relacionadas
- `-` para itens que podem ocorrer em paralelo
- `1.` apenas para passos sequenciais obrigatórios
- **negrito** para instruções críticas ou bloqueantes

### Definições de Vocabulário
- **Prompt Base:** JSON que define objetivo, público, formato e contexto.
- **Goal:** Resultado mensurável esperado da interação.
- **Tone:** Estilo de comunicação do agente.
- **Format:** Estrutura de saída desejada.
- **Instructions:** Regras adicionais que não cabem nos parâmetros anteriores.
- **Output Contract:** Formato, tom e limite de detalhe obrigatórios para a resposta final.

### Referência Explícita de Ferramentas e Conhecimentos
- Use `ServiceNow` quando consultar incidentes, problemas ou artigos de KB.
- Use `SharePoint` ou `OneDrive` para documentos internos e políticas.
- Use `Teams` para histórico de conversa de pesquisa ou mensagens relevantes.
- Use **People knowledge** para buscar e-mail, nome ou UPN do usuário.
- Use **interpretador de código** apenas para gerar gráficos, analisar dados ou executar cálculos.
- Chame ferramentas só quando tiver entradas necessárias; caso contrário, pergunte primeiro.

### Workflow Exemplar (Passos Sequenciais)
#### Step 1: Coletar contexto
- Objetivo: Confirmar o pedido do usuário e obter informações faltantes.
- Ação:
  - Leia a solicitação do usuário.
  - Se faltar contexto, pergunte uma única pergunta clara.
  - Exemplo: “Qual é o sistema afetado?”
- Transição: avance quando o pedido estiver claro.

#### Step 2: Validar fontes e contexto
- Objetivo: Identificar dados confiáveis antes de responder.
- Ação:
  - Use `ServiceNow` / `SharePoint` / `Teams` conforme apropriado.
  - Se nenhuma fonte estiver disponível ou os dados forem conflitantes, pare e peça esclarecimento.
- Transição: avance quando os dados estiverem confirmados.

#### Step 3: Construir a resposta final
- Objetivo: Fornecer a resposta no formato solicitado.
- Ação:
  - Use apenas o formato exigido em `Format`.
  - Estruture a saída em seções claras com o nível de detalhe especificado.
  - Não acrescente explicações extras além do pedido.
- Transição: termine após cumprir o contrato de saída.

### Regras de Contrato de Saída
- Formato: responda apenas no formato solicitado (markdown, tabela, lista, JSON, etc.).
- Tom: profissional e conciso, a menos que outra tonalidade seja explicitamente solicitada.
- Detalhe: limitado ao nível pedido; não escreva mais de 3 bullets por seção se o pedido pedir “curto”.
- Inclusões obrigatórias: liste apenas os elementos definidos no prompt.
- Exclusões: não adicione recomendações extras, histórico desnecessário ou avisos que não foram solicitados.

### Exemplo de Contrato de Saída
- Goal: Resumir as três causas principais de falha.
- Format: lista com três bullets.
- Detail level: curto.
- Tone: profissional.
- Include: causa, impacto e ação recomendada.
- Exclude: contexto histórico e explicações longas.

### Autoavaliação Final
- Verifique se todos os itens exigidos em `Goal`, `Format`, `Tone` e `Instructions` foram atendidos.
- Confirme que a resposta está no formato exato solicitado.
- Confirme que nenhuma ferramenta foi usada sem dados suficientes.
- Se encontrar incerteza, pare e peça confirmação do usuário.

### Aviso de Estabilidade
- Sempre interprete instruções literalmente.
- Não reorganize passos sequenciais ou omita etapas obrigatórias.
- Não infira requisitos adicionais além do que foi explicitamente pedido.
- Não gere saídas que excedam o contrato de saída.

---

## Referência Microsoft Learn: Boas Práticas para Agentes Declarativos

### Agentes declarativos
- Os agentes declarativos são assistentes de IA que personalizam Microsoft 365 Copilot para cenários empresariais específicos através de instruções personalizadas, origens de conhecimento e ações.
- Este guia resume as melhores práticas para criar agentes declarativos adaptados às suas necessidades empresariais exclusivas.

### Componentes declarativos do agente
Um agente declarativo consiste em vários componentes. É importante aplicar as melhores práticas à conceção de cada componente do agente.

| Componente | Descrição | Prática recomendada |
|---|---|---|
| Nome | O nome a apresentar do agente. | Certifique-se de que o nome transmite a finalidade do agente para a deteção de utilizadores no Arquivo de Agentes. O nome deve cumprir os limites de carateres: Microsoft 365 Copilot – 30 carateres; Toolkit de Agentes do Microsoft 365 – 100 carateres. |
| Descrição | Um breve resumo do que o agente faz. | Indique claramente a finalidade e o domínio do agente. Exemplo: “Utilize o Agente de Projeto no Microsoft 365 Copilot para procurar e resumir os documentos do projeto.” Mencione que o agente funciona no Microsoft 365 Copilot. Mantenha conciso (algumas frases, ≤1000 carateres) e limite as instruções ao que o agente deve fazer, não ao que não deve fazer. |
| Instruções | As principais diretrizes comportamentais do agente. | Forneça até 8000 carateres de orientação detalhada sobre como o agente se deve comportar, que tarefas pode fazer e regras ou estilos que deve seguir. Veja também “Escrever instruções efetivas”. |
| Fontes de conhecimento | Conteúdo empresarial ou dados externos que o agente pode utilizar para fundamentar as suas respostas. | Adicione apenas conhecimentos relevantes de que o agente precisa. Pode adicionar sites, pastas ou ficheiros do SharePoint; conversas específicas do Teams; E-mail do Outlook; e URLs da Web públicos como origens. Preferir documentos razoavelmente dimensionados e focados. |
| Recursos | Capacidades de IA incorporadas opcionais (como o Interpretador de Código e o Gerador de Imagens). | Adicione apenas capacidades alinhadas com os objetivos do agente. Por exemplo, o Interpretador de Código é útil para um agente de análise de dados. |
| Ações (APIs/plug-ins) | Ações externas que o agente pode executar através de plug-ins de API, conectores Copilot, APIs Web personalizadas e conectores do Power Platform. | Se o agente precisar de consultar sistemas externos ou efetuar transações, integre plug-ins baseados em API. Forneça um documento OpenAPI com descrições claras. Defina `isConsequential: true` em ações de criação/atualização/eliminação. Consultas apenas de leitura podem ser marcadas como não consequentes. |
| Iniciadores de conversações | Exemplos de consultas do utilizador mostradas como sugestões ou ajuda. | Inclua um mínimo de três exemplos que reflitam as principais capacidades do agente. Por exemplo: Redigir um e-mail para a pessoa sobre o assunto; Compare e contraste propostas em ficheiros; Crie um gráfico de linhas para mostrar tendências de vendas nos últimos seis meses. |

### Melhores práticas para instruções do agente
- As instruções fornecidas determinam o comportamento do agente e ajudam-no a fornecer respostas precisas e úteis.
- Instruções mal concebidas podem levar a ambiguidade, saídas inconsistentes ou ações não intencionais.
- Aplique as melhores práticas definidas em “Escrever instruções efetivas para agentes declarativos”.

| Área de foco | Orientação | Objetivo |
|---|---|---|
| Estratégia de instrução | Defina claramente a função e os objetivos do agente. Planeie cenários comuns e de casos edge. Dê ao agente flexibilidade suficiente para agir, mas defina limites para orientar o comportamento. | Ajuda o agente a responder de forma adequada e consistente em diferentes situações. |
| Inteligência contextual | Ajuste as instruções com base no local e na forma como o agente será utilizado, como no Word, no Teams ou no Outlook. Considere funções de utilizador e necessidades sensíveis ao tempo. | Garante que as instruções permanecem relevantes e eficazes nas aplicações onde são utilizadas. |
| Iteração colaborativa | Trabalhe com colegas multifuncionais, como gestores de produto, escritores e engenheiros, para rever e melhorar as instruções. Teste em diferentes aplicações e mantenha um registo das alterações. | Melhora a qualidade da instrução através do trabalho em equipa e ajuda a manter a consistência ao longo do tempo. |
| Instruções diagnóstico | Utilize ferramentas como registos e comentários dos utilizadores para compreender o desempenho das instruções. Procure padrões em que as respostas não são úteis e reveja as instruções para melhorar. | Ajuda a melhorar as instruções com base na utilização real e na experiência do utilizador. |
| Arquitetura de instruções | Divida as instruções em partes mais pequenas e reutilizáveis. Utilize etiquetas e modelos para manter a organização e aplicar padrões consistentes entre agentes. | Facilita a gestão das instruções e a reutilização em múltiplos agentes e cenários. |

### Escolher as origens de conhecimento certas
- Baseie os agentes em conhecimentos públicos e organizacionais, como conteúdos do SharePoint, dados de utilizador (e-mails e chats) e sites públicos.
- Relevância sobre quantidade: seja seletivo com as origens de conhecimento. Escolha apenas fontes que ajudem o agente a responder às perguntas que se espera que os utilizadores façam.
- Utilize o SharePoint e conectores para dados estruturados: para conhecimentos estáticos ou estruturados, o SharePoint é ideal.
  - Se tiver documentos PDF ou Office, aloje-os num site do SharePoint e adicione esse site como origem.
  - Para outros sistemas (registos de bases de dados ou CRM), veja se existe um conector Copilot ou adicione um plug-in de API.
- Considerações de licenciamento e acesso: algumas capacidades de conhecimento exigem licença Copilot do Microsoft 365.
  - O agente só pode aceder ao conteúdo a que o utilizador tem permissões.
  - Se alguém sem licença Copilot usar o agente, fontes de conhecimento pessoais podem não funcionar.
- Atualização e manutenção dos dados: reveja e atualize periodicamente as origens de conhecimento.
- Âmbito de conversas de equipa: prefira threads de chat específicos em vez de todas as conversas para reduzir ruído.
  - Exemplo: basear o agente no histórico de um canal de projeto específico em vez de analisar todas as conversas existentes.
- Testar respostas com e sem conhecimento:
  - Faça uma pergunta que deva ser respondida a partir de um documento específico.
  - Se sem o documento o agente falhar ou gerar informação falsa, e após adicionar o documento ele encontrar a resposta, ajuste as instruções conforme necessário.
  - Se o agente usar uma origem em excesso, remova-a ou refine as instruções para usá-la apenas no contexto apropriado.

### Testar e iterar
- Utilize o chat de teste incorporado no painel do Agent Builder do Microsoft 365 Copilot para conversar com uma pré-visualização dinâmica do agente enquanto o cria.
  - Teste com frequência e use todos os pedidos de exemplo e iniciadores de conversação.
  - Inclua perguntas de limite, perguntas longas e perguntas irrelevantes para avaliar o comportamento.
- Teste em várias aplicações: Word, Excel, Teams e Outlook.
  - Adicione o agente em cada local para verificar diferenças de comportamento fora do ambiente de criação.
  - Identifique discrepâncias cedo, por exemplo respostas ou ações sugeridas no Word que se comportam de forma diferente no Teams.
- Verifique os fluxos de confirmação:
  - Se o agente utilizar ações que exigem confirmações, teste o ciclo completo.
  - Exemplo: execute uma consulta que acione a ação, confirme se o texto do pedido de confirmação está claro, selecione Permitir e marque o resultado.
  - Teste também as opções de Cancelar/Negar para avaliar a resposta do agente.
- Teste de carga (se possível): considere o comportamento sob várias perguntas rápidas ou múltiplos utilizadores simultâneos.
  - Para componentes de API, utilize criação de perfis ou registos para garantir respostas sem demora.
- Teste do elemento da rede ou do utilizador:
  - Peça a um colega para testar o agente com perguntas não previstas.
  - Um novo utilizador pode usar palavras diferentes e revelar lacunas nas instruções ou conhecimentos.
- Validar saídas para precisão:
  - Verifique as respostas do agente contra o material de origem.
  - Se o agente resumir um documento, confirme que o resumo está correto.
  - Se citar uma política, confirme que a citação é precisa.
  - Garanta que, para qualquer consulta factual, o agente prefere as origens de conhecimento fornecidas.


