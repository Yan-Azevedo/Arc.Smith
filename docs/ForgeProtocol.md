# ForgeProtocol
### Base de Conhecimento do ArcSmith — Engenharia de Prompt

> Documento de referência para criação, refinamento e padronização de prompts estruturados em JSON para agentes de IA no Microsoft Copilot e Copilot Studio.

---

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

*ForgeProtocol — ArcSmith Knowledge Base*
*Repositório: github.com/[seu-usuario]/arcsmith*