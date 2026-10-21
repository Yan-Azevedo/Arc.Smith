# Metodologia: identificação e separação de cases

## Identificação, Separação e Priorização de Cases (Módulo Arc)

No coração do processo metodológico está o mapeamento das oportunidades em que a IA pode gerar valor. Nesta fase (Módulo Arc), compila-se tudo o que foi descoberto, identificam-se possíveis cases de IA, separa-se cada caso de uso distinto e então prioriza-se quais valem ser trabalhados primeiro com base em critérios de impacto e viabilidade.

O resultado esperado desta fase é uma lista de cases bem definidos e ordenados por prioridade, dentre os quais um (ou mais) será selecionado para desenvolvimento.

## Identificação de Oportunidades de IA

Com as informações da descoberta em mãos, elabora-se uma lista de potenciais casos de uso em que a IA pode trazer ganhos. Em particular, avaliam-se tarefas ou processos propícios à melhoria por IA, que tendem a apresentar pelo menos algumas das seguintes características:

- **Repetitividade e manualidade:** atividades frequentes executadas de forma repetitiva, consumindo muito tempo dos profissionais de forma operacional.
- **Esforço cognitivo estruturado:** tarefas que envolvem análise ou processamento de dados de maneira padronizada ou baseada em regras definidas (por exemplo, aplicar sempre os mesmos critérios a cada novo documento ou registro).
- **Propensão a erro humano:** atividades longas ou complexas, sujeitas a lapsos humanos por cansaço ou atenção limitada (por exemplo, reentradas manuais de dados, cálculos extensos em planilhas).
- **Longa duração:** processos que exigem muitas horas de trabalho ou têm filas de espera, sugerindo que a automação inteligente poderia acelerar sua conclusão.
- **Conhecimento disperso:** tarefas que requerem consulta a múltiplas fontes de informação ou dependem de conhecimento que está espalhado em vários documentos ou sistemas, uma situação em que a IA pode consolidar e sintetizar dados rapidamente.

## Tabela de Análise de Oportunidades de IA

Para comparar as oportunidades, é útil montar uma tabela resumindo fatores-chave de cada possível case:

| Oportunidade de IA | Frequência | Esforço Manual Atual | Propensão a Erros | Ganho Esperado com IA | Outros Fatores |
|---|---|---|---|---|---|
| **Consolidação mensal de indicadores** (unificar planilhas de várias equipes) | Mensal | Alto (cerca de um dia de trabalho manual) | Moderada (erros de cópia e de fórmula) | Elevado: consolidação em minutos, liberando o time para análise. | Dados já estruturados em planilhas. |
| **Respostas a dúvidas frequentes sobre políticas internas** (assistente de consulta) | Contínua (dezenas de consultas por semana) | Médio (consultas repetidas a especialistas) | Baixa (respostas já padronizadas) | Moderado: resposta imediata e padronizada, liberando especialistas para casos complexos. | Exige base de políticas atualizada e bem estruturada. |
| **Extração de campos de documentos recebidos** (formulários e solicitações em PDF) | Semanal (volume recorrente) | Alto (digitação manual de campos) | Moderada (erros de digitação) | Elevado: menos retrabalho e maior precisão nos dados extraídos. | Documentos precisam estar legíveis e com padrão mínimo. |
| **Resumo de reuniões com decisões e pendências** (registro padronizado) | Semanal | Médio (cerca de 30 minutos por reunião) | Média (pendências esquecidas ou sem responsável) | Moderado: registro rápido e padronizado das decisões. | Exige transcrição ou anotações da reunião. |

> *Tabela: exemplos fictícios de quatro oportunidades, com estimativas qualitativas de impacto e esforço.*

## Separação de Múltiplos Cases

Frequentemente, a fase de descoberta revela diversas ideias de aplicação de IA. Cada ideia identificada deve ser trabalhada como um case independente, mesmo que surja dentro da mesma entrevista ou área.

Por exemplo, numa conversa com um analista financeiro, ele pode mencionar tanto a automação da conciliação de pagamentos quanto a melhoria de um relatório mensal — dois potenciais cases revelados simultaneamente. É crucial separá-los em descrições distintas, cada qual com seu próprio conjunto de informações (contexto, atores envolvidos, problemas). Essa separação permite avaliar o mérito de cada case individualmente e decidir de forma objetiva quais seguirão adiante.

## Mapeamento do Processo Atual (AS-IS)

Para cada case, documenta-se primeiro como o processo funciona hoje — o chamado cenário AS-IS. Liste todas as etapas atuais, quem as executa, quais ferramentas são usadas, e quais informações entram e saem em cada passo.

O mapeamento AS-IS deve refletir o mundo real, não apenas o procedimento "oficial" descrito em manuais ou normas. Dessa forma, o mapa incluirá também as práticas informais, os gargalos (pontos de lentidão ou fila) e os pontos críticos que surgiram nas entrevistas.

Esse mapeamento ajuda a visualizar onde a IA pode fazer diferença. Preste atenção especial aos pontos de dor no fluxo atual — aquelas etapas onde há lentidão, erros ou insatisfação. Entender essas dores é essencial para planejar onde a IA agregará mais valor.

## Captura de Exceções e Variações

Durante a documentação do AS-IS, é importante incluir exceções e variações do processo. Poucos processos seguem rigorosamente um único fluxo; geralmente existem desvios ou casos especiais. Para identificá-los:

- Pergunte ativamente sobre situações incomuns: *"O que vocês fazem se a informação X não está disponível?"* ou *"Como lidam com um pedido fora do padrão Y?"*.
- Anote caminhos alternativos ou informais que os usuários descrevem (por exemplo, uso de planilhas auxiliares ou procedimentos manuais quando o sistema oficial falha).
- Indique esses cenários de exceção como ramificações ou observações no mapeamento AS-IS. Assim, o processo fica devidamente representado.

## Desenho do Processo Futuro (TO-BE)

De posse de um bom AS-IS, conceba como o processo funcionará com a IA integrada — o cenário TO-BE. Nesse design futuro:

- **Mantenha iterações simples:** planeje a primeira versão com mudanças minimamente necessárias para atingir o ganho principal. Evite tentar automatizar 100% de uma só vez (risco de sobrecarga).
- **Defina papéis de IA vs humanos:** explicite que etapas serão feitas pela solução de IA e quais permanecerão sob responsabilidade humana (por segurança, validação ou tomada de decisão). Isso manterá a confiança e o controle.
- **Considere integrações e dados:** identifique se a solução IA precisará se conectar a outros sistemas ou bases de dados. Mesmo que a POC use dados de exemplo, planeje o que seria necessário para uma futura integração real.

O resultado do TO-BE deve evidenciar claramente o que muda em relação ao AS-IS: quais atividades serão automatizadas, modificadas ou eliminadas. Essa comparação servirá mais tarde para comunicar o valor da melhoria atingida.

## Apresentação e Alinhamento dos Cases

Depois de mapeados e analisados, os cases identificados devem ser apresentados aos responsáveis pela decisão (gestores ou líderes envolvidos no processo) para validação. Nessa apresentação, é recomendável iniciar recapitulando sucintamente o processo atual e seus principais problemas, conectando-os com as oportunidades de IA levantadas. Em seguida, relacionar cada case identificado com um título e descrição breve, incluindo comentários sobre valor esperado e complexidade, e destacar o(s) case(s) proposto(s) para seguir adiante.

Obter a concordância e aprovação dos sponsors ou tomadores de decisão para o case selecionado é fundamental. Esse alinhamento formal garante que todos estejam de acordo com o foco escolhido e entendam o motivo da seleção. A partir daí, prossegue-se com confiança para a fase de construção da solução (Módulo Smith), sabendo que se está atendendo a um objetivo validado e prioritário.
