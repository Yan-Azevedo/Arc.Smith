# Método de atualização dos fatos voláteis

Objetivo: manter as skills do ArcSmith corretas enquanto a plataforma (em preview) muda. Os fatos que mudam rápido ficam nas tabelas `fatos-volateis.md` de cada skill de plataforma. O resto do conteúdo das skills é metodologia e muda pouco.

## 1. Gatilhos

Rode a revisão quando ocorrer qualquer um destes:

- saiu nova versão de schema (declarativeAgent, plugin ou manifest do app);
- o Microsoft Learn publicou nota de preview, GA ou mudança de limite;
- o Provision, o `atk validate` ou o upload deu erro que o conteúdo das skills não previa;
- venceu o prazo da coluna **Revalidar (dias)** de alguma linha (Verificado em + Revalidar < hoje);
- antes de qualquer release (subida de versão do `manifest.json`);
- a linha está marcada "a verificar".

## 2. Execução

1. Abra o Copilot Chat com o Microsoft Learn MCP disponível.
2. Cole o prompt de `docs/prompts/revisao-fatos-volateis.md`.
3. Leia o relatório de mudanças que ele devolve e confira os links citados.

## 3. Registro

Para cada fato revisado:

- atualize **Valor atual**, **Status** e **Verificado em** na linha da tabela;
- se o valor ou o status mudou, adicione uma entrada no `CHANGELOG.md` e suba a `version` do `manifest.json`;
- se a mudança afetar outra skill (coluna **Afeta**), revise o texto dessa skill.

Se o valor não mudou, atualize só **Verificado em**.

## 4. Regra de precedência

No runtime, em conflito entre uma skill e o Microsoft Learn, **o Learn prevalece**. As skills não devem repetir números de plataforma fora das tabelas de fatos voláteis; devem apontar para a linha (ID FV-xx) correspondente.

## Limites deste método

- Ele só revisa o que está nas tabelas. Fato novo precisa ganhar uma linha primeiro.
- A revisão depende da doc do Learn estar atualizada; em preview ela pode atrasar em relação ao produto.
