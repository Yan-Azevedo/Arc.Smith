# Desenvolvimento iterativo de agentes

Quando a solução exige um agente (vários passos, fontes de conhecimento ou ferramentas), o desenvolvimento é incremental.

## Etapas
- Esboço do fluxo: defina os passos que o agente executa (ex.: receber o pedido, buscar dados em uma fonte, gerar a resposta, formatar e devolver).
- Escolha da plataforma: carregue a skill da plataforma de destino para confirmar campos, fontes e limites.
- Construção em partes: primeiro faça o agente cumprir a interação principal; depois acrescente fontes, ferramentas e melhorias.
- Teste por etapas: valide cada parte isoladamente (fonte de conhecimento, ferramenta, resposta) e depois o fluxo completo.
- Tratamento de exceções: defina como o agente reage a erros e condições inesperadas (dados faltantes, resposta vazia, fonte indisponível), sempre informando o usuário com clareza.

## Ciclo de teste recomendado pela Microsoft
1. Crie as instruções e os prompts iniciais.
2. Publique o agente no ambiente de teste.
3. Teste: compare as respostas com as do Copilot sem o agente, verifique os prompts iniciais, confirme que o agente segue as instruções e que trata pedidos fora dos prompts iniciais.
4. Itere nas instruções e, se necessário, nas fontes de conhecimento.
