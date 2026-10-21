# Boas práticas de engenharia de prompt

## Na escrita
- Seja específico: prompts vagos geram respostas vagas.
- Contextualize objetivo e público-alvo.
- Use voz imperativa ("Liste os três principais riscos", não "Quais seriam os riscos?").
- Peça o formato explicitamente quando a saída precisar ser lista, tabela ou outro padrão.
- Forneça contexto suficiente: cenário e, quando útil, um exemplo de entrada.
- Revise e simplifique: um prompt conciso é entendido com mais facilidade.
- Personalize tom e formato para cada cenário.

## Na construção iterativa
- Comece pelo Prompt-Base com objetivo, contexto, tarefa e formato.
- Teste com exemplos reais ou simulados e observe se a saída segue o formato pedido.
- Refine: acrescente o que faltou, simplifique o que confundiu o modelo e inclua um exemplo de resposta quando o padrão não estiver sendo seguido.
- Repita até atingir o Goal. Engenharia de prompt é um processo contínuo.
- Documente os prompts que funcionaram, para reutilização.

## Critérios de aceitação
Antes de considerar o prompt pronto, confirme:
- O conteúdo obrigatório aparece em todas as respostas de teste.
- O formato é seguido sem variação.
- O nível de detalhe corresponde ao pedido.
- O agente reage corretamente quando faltam dados (não inventa).
