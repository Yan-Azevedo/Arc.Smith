# Changelog

Todas as mudanças relevantes do **ArcSmith** são documentadas neste arquivo.

O formato é baseado em [Keep a Changelog](https://keepachangelog.com/pt-BR/1.0.0/), e o projeto adere a um versionamento semântico adaptado:

- **MAJOR / MINOR** — novas capacidades, fontes de conhecimento ou features significativas
- **PATCH** — ajustes de instrução, configuração e correções pontuais

> A partir da versão 1.6.0, este changelog passa a ser mantido de forma contínua. As versões anteriores foram reconstruídas a partir dos marcos macro da evolução do projeto.

---

## [1.7.0]

### Adicionado
- **Instruções do agente atualizadas** para reconhecer e operar com os templates de entrega — agora o ArcSmith sabe quando e como acionar Template_Cases e Template_Entrega.
- Nova seção "Templates de Entrega — Geração de Documentos" nas instruções, orientando consulta aos knowledge sources, solicitação de dados ao usuário e geração de arquivos `.docx`.
- Novos comandos especiais:
  - `gerar discovery` — inicia geração do documento de Formalização Discovery (Template_Cases).
  - `gerar entrega` — inicia geração do Guia de Criação do Agente (Template_Entrega).
- Identificação de ação ampliada para cobrir os cinco fluxos do agente: Arc, Smith, Code Interpreter, Template_Cases e Template_Entrega.
- **Proteção do repositório** — criação do arquivo `.github/CODEOWNERS` definindo propriedade dos arquivos de identidade autoral (README, LICENSE, CHANGELOG).
- **Branch Protection** ativada na branch `main`, exigindo Pull Requests e aprovação de Code Owners para alterações.

### Modificado
- Reposicionamento textual do agente de "workshop de adoção" para "desenvolvimento estruturado de soluções de IA".
- Seção de identidade e regra fundamental enxugada para acomodar as novas capacidades dentro do limite de 8000 caracteres.

### Removido
- Detalhamento dos critérios de complexidade nas instruções (Baixa, Média, Alta, Projeto) — agora consultado dinamicamente no SolutionKnowledge, evitando duplicação e liberando caracteres.

---

## [1.6.0]

### Adicionado
- **Template de Entrega** (`Template_Entrega`) publicado como quarta fonte de conhecimento WebSearch — guia completo de criação do agente para entrega ao cliente.
- Cobertura de múltiplas plataformas no guia de criação: Copilot Chat, Agent Builder (M365) e Copilot Studio.
- Estrutura de prompts sugeridos em duas camadas: prompts padrão configuráveis e prompt de orientação para agentes robustos.
- Orientação de criação assistida via Microsoft Learn MCP em tempo real, garantindo passo a passo atualizado conforme a plataforma escolhida.
- Seção de lógica de interação para agentes que seguem fluxo sequencial.
- Regras de formatação embutidas no template para geração do documento final em `.docx`, incluindo blocos de citação destacados para conteúdo a ser copiado.

### Modificado
- Slots de WebSearch atingem capacidade máxima (4 de 4): ForgeProtocol, SolutionKnowledge, Template_Cases e Template_Entrega.

---

## [1.5.0]

### Adicionado
- **Template de Cases** (`Template_Cases`) publicado como terceira fonte de conhecimento WebSearch — documento de Formalização Discovery para registro estruturado dos cases identificados em sessão.
- Estrutura de documento com apresentador e área por case, suportando sessões com múltiplas áreas.
- Campo "Responsável pelo Discovery" com placeholders dinâmicos (consultor, cargo, empresa), permitindo uso por diferentes consultores e consultorias.
- Regras de formatação embutidas no template (tipografia, cores neutras e indicadores fixos de complexidade) para geração do documento final em `.docx`.
- **LICENSE** Creative Commons BY-NC-ND 4.0 — proteção de propriedade intelectual com atribuição obrigatória, sem uso comercial e sem derivações.

### Modificado
- **README principal** reposicionado para "desenvolvimento estruturado de soluções de IA", removendo referências a workshop de adoção e a processos de empresa específica.
- **README técnico** atualizado com identidade visual consistente (logo, badges e imagens).
- Documentação reforça o posicionamento de arquitetura como grounding sofisticado multi-fonte, não RAG técnico.
- Tabela de origem do projeto (Casetron + Prompt Smith) adicionada ao README.
- Imagens do projeto organizadas em ambos os READMEs.

---

## [1.4.0]

### Adicionado
- **SolutionKnowledge** publicado como segunda fonte de conhecimento WebSearch — metodologia autoral completa de construção de soluções de IA, cobrindo critérios fundamentais, fundamentos, condução de entrevistas, identificação e priorização de cases, construção e validação, e documentação final.
- Regra fundamental de foco na entrega de valor incorporada às instruções do agente.
- Propósito explícito do módulo Smith: entregar instrução para o correto funcionamento da solução em IA, aplicando arquitetura e engenharia de prompt adequadas.

### Modificado
- **Migração para schema v1.7** do Declarative Agent.
- Ativação do modo de resposta `Think deeper` (raciocínio profundo) via `behavior_overrides`, alinhado aos princípios de Chain of Thought.
- Ativação de `discourage_model_knowledge` para priorizar o conhecimento curado e o retrieval via MCP sobre o conhecimento genérico do modelo.
- Reestruturação do módulo Smith: os campos `title` e `agent` deixam de compor o JSON gerado e passam a ser apresentados em texto (Nome do Agente, Título resumido, Descrição).

### Removido
- Bloco `config` do output do módulo Smith (language, dateFormat, timeFormat, tone, reasoning, placeholders_style, formatting) — informações desnecessárias que consumiam caracteres e poluíam o resultado.

---

## [1.3.0]

### Adicionado
- **Integração com Microsoft Learn MCP** (Model Context Protocol) via action `ai-plugin`, estabelecendo a camada de retrieval dinâmico externo do agente.
- Ferramentas `microsoft_docs_search` (busca semântica) e `microsoft_docs_fetch` (recuperação de páginas completas) para consulta em tempo real à documentação oficial Microsoft.
- Configuração do MCP server em `.vscode/mcp.json` apontando para o endpoint público `https://learn.microsoft.com/api/mcp`.

### Modificado
- Arquitetura do agente consolidada em três camadas de conhecimento: conhecimento curado (WebSearch), retrieval dinâmico externo (MCP) e grounding nativo do tenant (M365).

---

## [1.2.x]

### Adicionado
- Capabilities nativas de grounding no tenant M365: OneDriveAndSharePoint, TeamsMessages e Email — permitindo a localização de cases por cliente em múltiplas fontes (documentos, conversas e e-mails).
- **ForgeProtocol** publicado como primeira fonte de conhecimento WebSearch — metodologia de engenharia de prompt com estrutura JSON, parâmetros de refinamento e boas práticas.

### Modificado
- Sucessivos ajustes de instrução e configuração (versões PATCH) para refinamento de comportamento dos módulos Arc e Smith.
- Ajustes na estrutura do Prompt-Base e nos critérios de classificação de complexidade dos cases.

---

## [1.0.x]

### Adicionado
- Configuração inicial de assets e ícones do agente (`color.png` 192x192 e `outline.png` 32x32 com fundo transparente).
- Identidade visual do personagem ArcSmith.

### Modificado
- Ajustes pontuais de ícones e metadados do manifesto do aplicativo.

---

## [1.0.0]

### Adicionado
- **Versão inicial do ArcSmith** — Declarative Agent para Microsoft 365 Copilot.
- Consolidação de dois agentes autorais anteriores em um único fluxo coeso:
  - **Casetron** — transformação de entrevistas em cases de valor.
  - **Prompt Smith** — engenharia e refinamento de prompts.
- Três módulos operacionais:
  - **Módulo Arc** — documentação e classificação de cases por complexidade (Baixa, Média, Alta, Projeto).
  - **Módulo Smith** — engenharia de prompt estruturado em JSON.
  - **Módulo Code Interpreter** — análise de dados e geração de artefatos em Python (sandbox).
- Comandos especiais: `encerrar` (reset do módulo Smith) e `novo case` (reset do módulo Arc).
- Estrutura base do projeto no Microsoft 365 Agents Toolkit.

### Notas técnicas
- O Module Code Interpreter apresenta limitação conhecida na leitura nativa de arquivos `.xlsx` e `.docx` em Declarative Agents (limitação de plataforma). Workaround adotado: conversão para CSV antes do anexo.
- Decisão arquitetural consciente de **não** adotar RAG técnico (vector store + embeddings). O volume e a natureza curada da base de conhecimento tornam o grounding sofisticado multi-fonte mais adequado ao escopo do projeto.

---

[1.7.0]: https://github.com/Yan-Azevedo/Arc.Smith/compare/v1.6.0...v1.7.0
[1.6.0]: https://github.com/Yan-Azevedo/Arc.Smith/compare/v1.5.0...v1.6.0
[1.5.0]: https://github.com/Yan-Azevedo/Arc.Smith/compare/v1.4.0...v1.5.0
[1.4.0]: https://github.com/Yan-Azevedo/Arc.Smith/compare/v1.3.0...v1.4.0
[1.3.0]: https://github.com/Yan-Azevedo/Arc.Smith/compare/v1.2.9...v1.3.0
[1.2.x]: https://github.com/Yan-Azevedo/Arc.Smith/compare/v1.0.2...v1.2.9
[1.0.x]: https://github.com/Yan-Azevedo/Arc.Smith/compare/v1.0.0...v1.0.2
[1.0.0]: https://github.com/Yan-Azevedo/Arc.Smith/releases/tag/v1.0.0