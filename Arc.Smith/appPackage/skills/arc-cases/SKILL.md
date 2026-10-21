---
name: arc-cases
description: "Transforma transcrições, anotações e resumos de reuniões de discovery em cases de IA, classifica cada case como Aderente (com complexidade de construção e de sustentação) ou Viável em projeto e conduz a seleção: um case é documentado direto; vários cases geram o relatório de seleção para aprovação do cliente. Use quando o usuário enviar texto de reunião ou pedir para identificar, documentar, classificar ou selecionar cases."
---

# Arc: seleção e documentação de cases

## Objetivo
Interpretar o conteúdo de uma reunião de discovery, identificar os casos de uso de IA, classificar cada um e levar o cliente até a decisão: qual case será construído.

## Quando usar
- O usuário envia texto de reunião, transcrição, anotações ou resumo.
- O usuário pede para identificar, documentar, classificar ou selecionar cases.
- O usuário digita o comando novo case.

Não use esta skill para criar o agente (skill smith-prompt) nem para gerar os documentos e o e-mail de formalização (skill documentacao).

## Regra absoluta
Nunca invente sistemas, integrações, participantes, áreas ou números que não foram mencionados. Se faltar uma informação essencial, registre [não informado] no campo e, ao final da resposta, pergunte numa única mensagem.

## Fluxo
1. Leia o conteúdo inteiro antes de estruturar.
2. Identifique todos os casos de uso, inclusive os fragmentados (references/metodologia-identificacao.md). Trate cada um como unidade independente.
3. Reconstrua o processo atual sem IA, destacando os gargalos.
4. Classifique cada case (references/complexidade.md): Aderente, com complexidade de construção e de sustentação, ou Viável em projeto.
5. Siga o caminho conforme a quantidade de cases:
   - **Um case:** documente o case completo (references/estrutura-case.md) e pergunte se o usuário deseja o Documento do Case. Se sim, siga a skill documentacao, que também prepara o e-mail de formalização.
   - **Vários cases:** monte o relatório de seleção (references/estrutura-case.md, formato resumido) e pergunte se o usuário deseja o documento de Seleção de Cases. Se sim, siga a skill documentacao. Aguarde a aprovação do cliente.
6. Depois da aprovação, documente o case escolhido no formato completo e pergunte se o usuário deseja o Documento do Case.

## Regras
- Proponha soluções simples e viáveis, que o cliente consiga sustentar depois da entrega.
- Deixe claro, em cada case aderente, que quanto maior a complexidade de sustentação, maior a dedicação do cliente para manter a solução.
- Case que passa do escopo de uma construção breve é Viável em projeto, nunca descartado em silêncio.
- Resolva ambiguidades com bom senso, sem exagerar o valor.
- Os tipos de solução (Prompt, Agente, Projeto) são raciocínio interno: orientam a classificação, mas nunca aparecem no texto do case (references/tipo-solucao.md).

## Comando
- novo case: inicia um novo fluxo, descartando o contexto anterior.

## Recursos
| Arquivo | Quando carregar |
|---|---|
| references/estrutura-case.md | Sempre que documentar um case ou montar o relatório de seleção |
| references/complexidade.md | Sempre que classificar um case |
| references/metodologia-identificacao.md | Para identificar, separar e mapear cases (AS-IS, TO-BE) |
| references/priorizacao.md | Para apoiar a decisão do cliente entre vários cases aderentes |
| references/tipo-solucao.md | Para decidir internamente entre prompt, agente ou projeto |
| references/metodologia-fundamentos.md | Para os critérios fundamentais e conceitos (ideia, case, POC, prompt, agente, projeto) |
| references/metodologia-entrevistas.md | Quando o usuário pedir apoio para preparar ou conduzir entrevistas de descoberta |
| references/metodologia-validacao.md | Para planejar testes e validação com usuários |
| references/metodologia-entrega.md | Para orientar entrega, handover e sustentação da solução |
| references/metricas-valor.md | Para definir ou estimar métricas de valor e impacto |
| references/antipadroes.md | Para revisar riscos, armadilhas e sinais de alerta |
