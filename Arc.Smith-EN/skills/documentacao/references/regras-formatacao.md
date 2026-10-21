# Document formatting rules

Current standard: **Cloud Target Brandbook – Modern Work & AI (2026)**. It applies to the three documents (Case Selection, Case Document and Agent Creation Guide) until the user provides another brandbook. Never use colors, fonts or logos outside this standard.

## How to generate
Generate the .docx with Code Interpreter using this skill's scripts/brand_docx.py script, which already applies the complete standard (cover, header, footer, key points, titles, tables and copy block) and uses the logos in the assets folder. If the script cannot be used, apply the rules below manually, with the same logo files.

## Logo
| File | Use |
|---|---|
| assets/logo_ct_colorido.png | Color (neon) version, preferred, only on a dark background: cover |
| assets/logo_ct_preto.png | Black monochrome version, on a light background: header of inner pages |
- Do not distort, do not recolor and do not place on noisy or low-contrast backgrounds.

## Colors
| Role | Color |
|---|---|
| Deep (section titles, table header) | #3A0E4D |
| Purple (section numbers, cover line, labels) | #7E1C9F |
| Neon (accents: tower label, border of the key points and of the copy block) | #C53DFF |
| Black (cover and copy block background) | #06070B |
| Text | #363636 |
| Secondary text (header, footer, captions) | #808080 |
| Borders and dividers | #D3D3D3 |
| White | #FFFFFF |
Use the neutrals for hierarchy and breathing room, without competing with the tower colors. Avoid too many colors and elements.

## Typography: Poppins family
| Element | Font | Size |
|---|---|---|
| Cover title | Poppins ExtraBold | 26 pt |
| Section titles (H2), numbered 01, 02... | Poppins ExtraBold | 14 pt |
| Subtitles and field labels | Poppins SemiBold | 11 to 12 pt |
| Body | Poppins | 10.5 pt, justified, 1.15 spacing |
| Header, footer and captions | Poppins Light | 7.5 pt |
The computer that opens the document needs the Poppins family installed; without it, Word substitutes the font.

## Mandatory structure
| Element | Rule |
|---|---|
| Cover | Dark background block (#06070B) with the color logo, the tower label "MODERN WORK & IA" in Neon, the title in white, a Purple line, the subtitle, the date and "Prepared by: [consultant] · Cloud Target". |
| Client name | In the cover subtitle and in the footer of every page. |
| Key points | Right after the cover: box with a Neon side border, the KEY POINTS label and 3 to 5 short items. |
| Header (from page 2) | Black logo on the left and "CLOUD TARGET · MODERN WORK & IA" on the right. |
| Footer | "Cloud Target \| [Client]" on the left and the page number on the right. |
| Sections | Numbered (01, 02...), number in Purple and title in Deep. |
| Tables | Header with Deep background and white text; thin #D3D3D3 borders. |
| Copy block | Black background, white text, Neon side border. For all content the user copies and pastes literally. |
| Page | A4, 2.2 cm margins. |

## Complexity indicators (within the palette)
| Level | Color |
|---|---|
| Low | Neon #C53DFF |
| Medium | Purple #7E1C9F |
| High | Deep #3A0E4D |
| Viable as a project | #808080 |

## Tone of voice
Consultative, clear and human: translate technology into business impact, use evidence and avoid jargon without context, alarmism and generic innovation promises.

## Forbidden in the final document
- Emojis.
- Comments, usage instructions or meta-information.
- Unfilled placeholders: every field in brackets must be replaced.
- Solution type (prompt, agent, project) in the case text.
