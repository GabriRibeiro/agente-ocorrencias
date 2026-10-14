# Agente de ocorrencias de entrega

Primeira entrega do projeto da disciplina: um agente unico baseado em LLM que atende ocorrencias de entrega da TransVale, uma operadora logistica ficticia. O caso, o problema e a justificativa da abordagem agentica estao no inicio do notebook.

## Como rodar

Abra `entrega1_agente_ocorrencias.ipynb` no Google Colab. Em Secrets, cadastre a chave da API da Anthropic com o nome `ANTHROPIC_API_KEY` e libere o acesso para o notebook. Se preferir, o notebook pede a chave na primeira chamada ao modelo.

Depois e so executar todas as celulas. Os dados, a base de politicas e as transportadoras sao simulados dentro do proprio notebook, entao nao ha outra dependencia externa.

A secao 9.1 roda testes deterministicos que nao usam a API. A secao 9.2 roda os cenarios de comportamento com o modelo real e faz algumas dezenas de chamadas.
