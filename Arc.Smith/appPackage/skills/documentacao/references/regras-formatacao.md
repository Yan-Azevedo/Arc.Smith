# Regras de formatação dos documentos

Padrão vigente: **Brandbook Cloud Target – Modern Work & IA (2026)**. Vale para os três documentos (Seleção de Cases, Documento do Case e Guia de Criação do Agente) até o usuário informar outro brandbook. Nunca use cores, fontes ou logos fora deste padrão.

## Como gerar
Gere o .docx com o Code Interpreter usando o script scripts/brand_docx.py desta skill, que já aplica o padrão completo (capa, cabeçalho, rodapé, pontos-chave, títulos, tabelas e bloco de cópia) e usa os logos da pasta assets. Se o script não puder ser usado, aplique manualmente as regras abaixo, com os mesmos arquivos de logo.

## Logo
| Arquivo | Uso |
|---|---|
| assets/logo_ct_colorido.png | Versão colorida (neon), preferencial, só sobre fundo escuro: capa |
| assets/logo_ct_preto.png | Versão monocromática preta, sobre fundo claro: cabeçalho das páginas internas |
- Não distorcer, não recolorir e não aplicar sobre fundos ruidosos ou de baixo contraste.

## Cores
| Papel | Cor |
|---|---|
| Deep (títulos de seção, cabeçalho de tabela) | #3A0E4D |
| Purple (números de seção, linha da capa, rótulos) | #7E1C9F |
| Neon (acentos: rótulo da torre, borda dos pontos-chave e do bloco de cópia) | #C53DFF |
| Black (fundo da capa e do bloco de cópia) | #06070B |
| Texto | #363636 |
| Texto secundário (cabeçalho, rodapé, legendas) | #808080 |
| Bordas e divisões | #D3D3D3 |
| Branco | #FFFFFF |
Use os neutros para hierarquia e respiro, sem competir com as cores da torre. Evite excesso de cores e elementos.

## Tipografia: família Poppins
| Elemento | Fonte | Tamanho |
|---|---|---|
| Título da capa | Poppins ExtraBold | 26 pt |
| Títulos de seção (H2), numerados 01, 02... | Poppins ExtraBold | 14 pt |
| Subtítulos e rótulos de campo | Poppins SemiBold | 11 a 12 pt |
| Corpo | Poppins | 10,5 pt, justificado, espaçamento 1,15 |
| Cabeçalho, rodapé e legendas | Poppins Light | 7,5 pt |
O computador de quem abre o documento precisa ter a família Poppins instalada; sem ela, o Word substitui a fonte.

## Estrutura obrigatória
| Elemento | Regra |
|---|---|
| Capa | Bloco de fundo escuro (#06070B) com o logo colorido, o rótulo da torre "MODERN WORK & IA" em Neon, o título em branco, linha Purple, o subtítulo, a data e "Elaborado por: [consultor] · Cloud Target". |
| Nome do cliente | No subtítulo da capa e no rodapé de todas as páginas. |
| Pontos-chave | Logo após a capa: caixa com borda lateral Neon, rótulo PONTOS-CHAVE e 3 a 5 tópicos curtos. |
| Cabeçalho (a partir da página 2) | Logo preto à esquerda e "CLOUD TARGET · MODERN WORK & IA" à direita. |
| Rodapé | "Cloud Target \| [Cliente]" à esquerda e o número da página à direita. |
| Seções | Numeradas (01, 02...), número em Purple e título em Deep. |
| Tabelas | Cabeçalho com fundo Deep e texto branco; bordas finas #D3D3D3. |
| Bloco de cópia | Fundo Black, texto branco, borda lateral Neon. Para todo conteúdo que o usuário copia e cola literalmente. |
| Página | A4, margens de 2,2 cm. |

## Indicadores de complexidade (dentro da paleta)
| Nível | Cor |
|---|---|
| Baixa | Neon #C53DFF |
| Média | Purple #7E1C9F |
| Alta | Deep #3A0E4D |
| Viável em projeto | #808080 |

## Tom de voz
Consultivo, claro e humano: traduza tecnologia em impacto de negócio, use evidências e evite jargão sem contexto, alarmismo e promessas genéricas de inovação.

## Proibido no documento final
- Emojis.
- Comentários, instruções de uso ou meta-informações.
- Placeholders sem preencher: todo campo entre colchetes precisa ser substituído.
- Tipo de solução (prompt, agente, projeto) no texto dos cases.
