# Priorização de cases

A priorização escolhe quais cases seguem para construção agora e quais ficam registrados para depois. Ela combina dois eixos, impacto (valor) e esforço (viabilidade), avaliados com a mesma régua para todos os cases.

## Princípios da priorização
- Valor de negócio primeiro: nenhum case é priorizado sem impacto evidente.
- Decisão baseada em dados: use fatos e estimativas do que foi relatado, não impressões.
- Transparência: os critérios e o motivo da escolha ficam claros para os envolvidos.
- Responsabilidade ética: considere privacidade, conformidade e impacto humano de cada case.

## Critérios de avaliação

### Impacto (valor)
| Critério | O que avaliar |
|---|---|
| Impacto de negócio | Ganho em eficiência, redução de custo, mitigação de riscos e alinhamento estratégico. Cases que tocam indicadores ou dores principais têm impacto alto. |
| Frequência e volume | Quantas vezes o problema ocorre. Processos diários ou de alto volume geram impacto maior quando melhorados. |
| Esforço manual atual | Quanto tempo e quantas pessoas o processo consome hoje. Quanto maior a carga, maior o alívio da automação. |
| Qualidade e erros | Melhoria de qualidade esperada: eliminar erro humano crítico ou padronizar entregas tem impacto alto. |

### Esforço (viabilidade)
| Critério | O que avaliar |
|---|---|
| Viabilidade técnica | Os dados de entrada existem e estão acessíveis em formato utilizável? A plataforma disponível atende? |
| Complexidade de implementação | Quantidade de integrações, necessidade de customização e esforço de construção (ver complexidade.md). |
| Tempo de implementação | Cases que podem ser prototipados em dias ou semanas têm preferência sobre os que exigem meses. |
| Adoção e cultura | Os usuários adotariam a solução? Eliminar uma tarefa maçante facilita a adoção; mudar radicalmente o fluxo gera resistência. |
| Riscos e conformidade | Implicações regulatórias, dados sensíveis e falhas críticas. Riscos inaceitáveis removem o case ou exigem mitigação robusta. |

### Como avaliar
- Atribua a cada case uma qualificação em cada critério: Alta, Média ou Baixa. Se o usuário preferir, use pontuação de 1 a 5.
- Consolide em dois resultados: Impacto (combinação dos critérios de valor) e Esforço (combinação dos critérios de viabilidade).
- Quando faltar informação para avaliar um critério, registre a lacuna em vez de supor.
- Sempre que possível, valide os pesos de impacto com os responsáveis pelo negócio.

## Matriz impacto x esforço
| Quadrante | Leitura | Ação |
|---|---|---|
| Alto impacto / Baixo esforço | Vitória rápida: grande valor com pouco trabalho | Prioridade máxima para construção imediata |
| Alto impacto / Alto esforço | Estratégico, porém exigente | Prototipar uma parte ou planejar como projeto |
| Baixo impacto / Baixo esforço | Melhoria incremental | Executar se couber, sem desviar o foco |
| Baixo impacto / Alto esforço | Pouco ganho e muito trabalho | Não recomendar agora; manter registrado no relatório |

A matriz orienta, mas a decisão final considera também o interesse e o apetite da organização: um case de impacto muito alto e esforço médio pode superar uma vitória rápida de impacto médio, se for estrategicamente mais relevante. A regra geral é privilegiar vitórias rápidas para dar tração inicial.

## Case bom, case viável e case certo
- **Case bom:** existe um problema claro e relevante e uma hipótese crível de solução com IA.
- **Case viável:** além de bom, é possível implementar com os dados, a tecnologia, os recursos e o tempo disponíveis.
- **Case certo para o momento:** bom e viável, com complexidade compatível com o prazo e alto impacto, para servir como prova de valor.

## Decisão
1. Apresente todos os cases no relatório de seleção, com a classificação de cada um (Aderente ou Viável em projeto) e, nos aderentes, as complexidades de construção e de sustentação.
2. Use a matriz impacto x esforço para recomendar, entre os aderentes, o case com melhor relação entre valor e esforço, explicando as trocas.
3. A escolha é do cliente: aguarde a aprovação antes de documentar o case escolhido.
4. Os cases não escolhidos permanecem no relatório como registro para iniciativas futuras.

## Quando não recomendar um case aderente
- Falta de alinhamento estratégico: não endereça um problema prioritário.
- Dependências indisponíveis: dados inexistentes ou inacessíveis, ou infraestrutura indisponível.
- Sustentação que o cliente não conseguirá assumir (sem responsável ou sem tempo para manter).
- Baixa adesão dos envolvidos: resistência de quem precisaria adotar a solução.

## Oportunidades não escolhidas
O relatório de seleção registra todos os cases, inclusive os viáveis em projeto, com dor, o que resolve, impacto e valor. O registro valoriza as contribuições dos participantes e cria um acervo para iniciativas futuras. Revise a recomendação quando o contexto mudar, mas mantenha o foco no case escolhido durante a construção.

## Checklist antes de fechar a priorização
- Todos os cases relevantes foram identificados.
- Cada case tem as informações-chave descritas; o que não pôde ser estimado está anotado.
- Os critérios foram aplicados com a mesma régua para todos; pesos diferentes foram declarados.
- Os responsáveis pelo negócio estão alinhados com a escolha.
- O case selecionado tem escopo delimitado e não depende de resolver outro problema antes.
- O relatório de seleção registra todos os cases, inclusive os viáveis em projeto.

## Armadilhas na priorização
- Decidir por intuição, sem dados ou estimativas que sustentem a escolha.
- Ignorar quem executa o processo e priorizar só pela visão da liderança.
- Selecionar cases demais ao mesmo tempo e diluir o foco.
- Classificar como Baixa complexidade algo que parece simples no papel, sem avaliar integrações, qualidade dos dados e o esforço de sustentação.
- Descartar cases de alto impacto só por serem complexos, em vez de registrá-los como viáveis em projeto ou fatiar o problema.
