# Verificação de recursos na criação do agente

A disponibilidade de recursos por nível (Copilot Basic e Copilot Premium) e por plataforma muda com frequência, às vezes em semanas. Por isso o Smith nunca trata essa disponibilidade como fixa: verifica no início de cada novo agente.

## Quando
- No primeiro passo de todo novo agente, antes da escolha do modo.
- De novo, se o usuário mudar o nível, a plataforma ou pedir um recurso que não foi verificado.

## O que verificar
| Item | Exemplos |
|---|---|
| Skills | Disponíveis no nível? Na plataforma? Preview ou GA? Exige Frontier Program? Limites? |
| Fontes de conhecimento | SharePoint, OneDrive, arquivos enviados, e-mail, Teams, pessoas, conectores, sites |
| Capacidades | Code Interpreter, geração de imagens, criação de documentos |
| Ações e integrações | Conectores, fluxos, MCP, plugins |
| Limites | Caracteres de nome, descrição e instruções; quantidade de fontes e arquivos |

## Como verificar
1. Pesquise no Microsoft Learn MCP (microsoft_docs_search) pelo recurso, pelo nível e pela plataforma. Exemplos: "Agent Builder skills license", "Copilot Chat agents capabilities licensing", "Copilot Studio knowledge sources limits".
2. Abra a página mais relevante (microsoft_docs_fetch) quando o trecho não for conclusivo.
3. Compare com os arquivos fatos-volateis.md das skills de plataforma. Eles são ponto de partida, não verdade final: em conflito, o Learn prevalece.
4. Se a documentação não cobrir o ponto, ou se fontes divergirem, diga isso e peça ao usuário para confirmar no tenant. Nunca preencha a lacuna por conta própria.

## Como apresentar
Uma tabela curta, antes da pergunta do modo:

| Recurso | Disponível para [nível] em [plataforma] | Status | Fonte | Verificado em |
|---|---|---|---|---|

- Status: GA, Preview, Em implantação, Não documentado ou Divergente.
- Fonte: título da página do Learn (sem link nas instruções do agente criado; aqui, na conversa, o link pode aparecer).
- Use só os recursos confirmados nas camadas seguintes da criação. O que estiver Não documentado ou Divergente entra como ponto a testar no tenant, não como certeza.
