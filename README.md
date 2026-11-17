# Agente de ocorrencias de entrega

Projeto da disciplina: atendimento de ocorrencias de entrega da TransVale, uma operadora logistica ficticia, com agentes baseados em LLM.

A Entrega 1 (`entrega1_agente_ocorrencias.ipynb`) e um agente unico no padrao ReAct. O caso, o problema e a justificativa da abordagem agentica estao no inicio desse notebook.

A Entrega 2 (`entrega2_sistema_multiagente.ipynb`) reorganiza esse agente com LangGraph e depois o divide em um sistema multiagente: um coordenador que conversa com o cliente, um investigador que levanta os fatos do pedido e um analista que aplica a politica de atendimento, ligados por contratos validados nas fronteiras. O notebook explica por que cada agente existe, quais divisoes foram descartadas e compara as duas arquiteturas nos mesmos cenarios.

A entrega final (`entrega3_sistema_governado.ipynb`) acrescenta governanca ao sistema multiagente: guardrails de entrada, execucao e saida, aprovacao humana com pausa e retomada do atendimento para decisoes de maior impacto, audit log encadeado por hash, controles de LGPD (minimizacao, mascaramento de dados pessoais antes do LLM, retencao e direitos do titular) e um painel de metricas calculado a partir do audit log.

## Como rodar

Abra o notebook no Google Colab. Em Secrets, cadastre a chave da API da Anthropic com o nome `ANTHROPIC_API_KEY` e libere o acesso para o notebook. Se preferir, o notebook pede a chave na primeira chamada ao modelo.

Depois e so executar todas as celulas. Os dados, a base de politicas e as transportadoras sao simulados dentro do proprio notebook, entao nao ha outra dependencia externa.

Na Entrega 2, as secoes 5.1 e 7 rodam testes deterministicos que nao usam a API. As secoes 8 e 9 usam o modelo real; a comparacao da secao 9 roda a bateria de cenarios nas duas arquiteturas e faz algumas dezenas de chamadas para cada uma.

Na entrega final, as secoes 1 a 5 nao usam a API. As secoes 6 e 7 usam o modelo real; a avaliacao da secao 7 roda 15 cenarios com um avaliador automatico e faz algumas centenas de chamadas. O audit log de cada execucao fica nos arquivos `audit_log.jsonl` e `audit_avaliacao.jsonl`.
