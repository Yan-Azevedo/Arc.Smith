# Skills do agente criado

Verificado em 2026-10-21. Confirme no Microsoft Learn MCP: as skills estão em preview.

## Quando propor uma skill
- Uma tarefa que se repete sempre com os mesmos passos, como gerar um relatório, montar um documento ou aplicar um checklist.
- Um procedimento longo que não cabe nas 8.000 caracteres das instruções sem perder qualidade.
- Um conjunto de modelos, dados de referência ou scripts que precisam ir junto com o procedimento.
Não proponha skill para regras gerais de comportamento: elas ficam nas instruções.

## Requisitos
A disponibilidade de skills por nível e por plataforma muda rápido: confirme sempre com a verificação de recursos (references/verificacao-recursos.md). Pontos de partida, verificados em 2026-10-21:
- Skills em agentes do Agent Builder: a página do Learn cita licença do Microsoft 365 Copilot ou cobrança por consumo e o Frontier Program (preview).
- Skills no Copilot Chat: em implantação mundial (GA) entre outubro e meados de novembro de 2026 (mensagem MC1493223), sem o nível de licença especificado na mensagem. Confirme se já valem para agentes do Copilot Basic.
- Não disponível em tenants com Microsoft Purview Information Barriers (suporte anunciado para novembro de 2026 no Copilot Chat).
- Agente sem arquivos embedded: skills e arquivos embedded ainda não podem ser combinados.
- Copilot Studio e Copilot Notebooks: sem custom skills documentadas até a última verificação.

## Limites
| Item | Agent Builder | Agents Toolkit |
|---|---|---|
| Skills por agente | 8 | 8 |
| Pacote | .zip de até 50 MB | Pasta da skill; não aceita .zip |
| Tamanho por arquivo | 25 MB | Sem limite por skill; pacote do app até 10 MB |
| Arquivos | 350 somando todas as skills | 350 somando todas as skills |
| Profundidade de pastas | 3 | 3 |
| Reuso entre agentes | Não | Não |

Tipos de arquivo aceitos: .md, .txt, .json, .xml, .yaml, .yml, .csv, .tsv, .html, .docx, .pdf, .pptx, .xlsx, imagens e outros documentos do Office. Scripts: .py, .js, .mjs, .cjs, .ts, .mts, .sh e .bash.

Scripts rodam em sandbox: sem rede, sem instalar pacotes, sem chamadas autenticadas e sem acesso a conectores, plugins ou MCP. Use só pacotes já presentes no sandbox.

## Estrutura de uma skill
```
nome-da-skill/
|-- SKILL.md            # obrigatório
|-- references/         # opcional: modelos, dados, definições
`-- scripts/            # opcional
```

SKILL.md:
- Front matter YAML com name (minúsculas e hífens, igual ao nome da pasta) e description entre aspas. A description diz o que a skill faz e quando usar: é ela que faz o agente escolher a skill.
- Instruções com menos de 20.000 caracteres, nesta ordem: Objetivo, Quando usar, Fluxo (passos numerados com transição clara entre eles), Regras, Formato de saída e Recursos (tabela de arquivos e quando carregar).
- Regras de comportamento ficam no SKILL.md; os arquivos de referência trazem só conteúdo descritivo (modelos, dados, definições).

## Instruções do agente com skills
- Cite cada skill em alto nível, pelo nome, dizendo quando usar.
- Não repita nas instruções o passo a passo que está no SKILL.md.

## Entrega por modo
- **Assistente (Agent Builder):** descreva cada skill no briefing, em linguagem natural: nome, objetivo, passos fixos, formato de saída e arquivos de apoio. O Agent Builder cria a skill a partir da descrição; confira na aba Configurar, em Skills. Se não for criada, oriente o modo Detalhado (pacote .zip).
- **Detalhado no Agent Builder:** entregue o SKILL.md em caixa copiável e gere com o Code Interpreter um .zip com o SKILL.md na raiz e as pastas de apoio. Upload: aba Configurar, Skills, Add. Suba o .zip completo, nunca o SKILL.md sozinho.
- **Detalhado no Agents Toolkit:** entregue o SKILL.md em caixa copiável e gere um .zip para o usuário extrair em appPackage/skills/nome-da-skill/. Inclua em caixa copiável a entrada de agent_skills ({"folder": "skills/nome-da-skill"}) e lembre os requisitos do Toolkit (schema v1.9 e a variável TEAMSFX_AGENT_SKILLS=true; skill copilot-m365-toolkit).
- O download de .zip gerado pelo Code Interpreter não está documentado: se falhar, entregue cada arquivo da skill em caixa copiável, com o caminho de cada um.

Fontes: https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/agent-builder-add-skills ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-instructions
