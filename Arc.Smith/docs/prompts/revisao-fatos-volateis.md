# Prompt: revisão dos fatos voláteis

Cole o bloco abaixo no Copilot Chat (com o Microsoft Learn MCP disponível). Substitua `[HOJE]` pela data atual no formato AAAA-MM-DD.

````text
Você vai revisar as tabelas de fatos voláteis do agente ArcSmith. Data de hoje: [HOJE].

ARQUIVOS
Leia todos os arquivos fatos-volateis.md em:
- appPackage/skills/copilot-chat/references/
- appPackage/skills/copilot-m365-agent-builder/references/
- appPackage/skills/copilot-m365-toolkit/references/
- appPackage/skills/copilot-studio/references/

Cada tabela tem as colunas: ID, Fato, Valor atual, Status, Fonte, Verificado em, Afeta, Revalidar (dias).

LINHAS A REVISAR
Revise apenas as linhas em que:
(a) Verificado em + Revalidar (dias) é anterior a hoje; ou
(b) Verificado em está como "a verificar" ou o Status está como "a verificar".
As demais linhas não são tocadas.

PARA CADA LINHA A REVISAR
1. Consulte a URL da coluna Fonte com o Microsoft Learn MCP (microsoft_docs_fetch; use microsoft_docs_search se a página não cobrir o fato).
2. Compare o Valor atual e o Status com o que a doc diz hoje.
3. Atualize a linha: Valor atual, Status e Verificado em (= hoje). Se a Fonte mudou de URL, atualize a Fonte.
4. Se a doc não permitir confirmar o fato, mantenha o valor, escreva "não confirmado" em Status e não altere Verificado em.
5. Nunca invente valores. Em dúvida entre duas leituras da doc, mantenha o valor e sinalize.

RELATÓRIO DE MUDANÇAS (ao final)
Gere uma tabela com: ID | Valor antigo -> novo | Status antigo -> novo | Impacto (quais skills, coluna Afeta) | Link da doc consultada.
Liste à parte: linhas não confirmadas, linhas sem mudança (só data atualizada) e linhas ignoradas por não estarem vencidas.

REGRAS
- NÃO altere nenhum outro arquivo nem nenhuma outra parte dos arquivos (SKILL.md, references, instruction.txt, manifest, CHANGELOG).
- NÃO reescreva as tabelas inteiras; altere só as linhas revisadas.
- Se o valor de alguma linha mudou, avise no fim: "Mudança de valor detectada: registrar no CHANGELOG e subir a version do manifest.json" (isso é feito por mim, não por você).
````
