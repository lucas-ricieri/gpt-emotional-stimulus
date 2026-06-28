# GPT Emotional Stimulus

Este é um projeto de replicação desenvolvido para a disciplina de Engenharia de Software Experimental da UTFPR, campus Campo Mourão.

A replicação usou como base o artigo **[Can ChatGPT emulate humans in software engineering surveys?](https://dl.acm.org/doi/10.1145/3674805.3690744)**. As alterações realizadas nos prompts e a criação dos novos prompts com estímulos emocionais foram inspiradas no artigo **[Large Language Models Understand and Can Be Enhanced by Emotional Stimuli](https://arxiv.org/abs/2307.11760)**.

## Objetivo

O projeto compara respostas geradas por diferentes variações de prompt para avaliar o quanto elas se aproximam das respostas humanas do estudo original. A análise usa o delta absoluto em relação ao percentual humano de referência (`Perc_Baseline`) e gráficos de ganho relativo para comparar os prompts emocionais com os cenários de controle.

## Organização dos Arquivos

- `paper/`: contém o artigo base utilizado na pesquisa.
- `prompts/`: contém os prompts usados no estudo, incluindo o prompt original, o prompt simples (`plain`) e os prompts com estímulos emocionais.
- `prompts/emotional_stimulus/`: contém o arquivo com os estímulos emocionais usados como referência para a criação dos prompts.
- `original_answers/`: contém a planilha com as respostas do prompt vanilla, usada como `Baseline` da comparação.
- `plain_answers/`: contém a planilha com as respostas do prompt simples (`Plain`), usada como cenário de comparação sem estímulo emocional.
- `stimulus_answers/`: contém a planilha com as respostas obtidas a partir dos prompts com estímulos emocionais (`EP01` a `EP11`).
- `scripts/`: contém o notebook principal da análise e o dataset agregado gerado a partir das respostas.

## Arquivos Principais

- `scripts/main.ipynb`: notebook usado para carregar os dados, agregar os resultados, calcular os deltas absolutos e gerar os gráficos comparativos.
- `scripts/1_results_stimulus_aggregated.csv`: dataset agregado gerado pelo notebook, com as colunas de identificação do prompt, questão, resposta, percentual e delta absoluto.
- `prompts/prompt-study1-plain.txt`: prompt simples usado para gerar as respostas armazenadas em `plain_answers/`.
- `prompts/prompt-study1-ep01.txt` a `prompts/prompt-study1-ep11.txt`: prompts com estímulos emocionais.

## Analises Geradas

O notebook `scripts/main.ipynb` gera:

- boxplot do delta absoluto por prompt;
- gráfico de ganho relativo médio dos prompts emocionais versus `Baseline`;
- quando a base `Plain` está incluída na agregação, gráfico de ganho relativo médio dos prompts emocionais versus `Plain`.

## Execução

Para atualizar o dataset agregado e regenerar os gráficos, execute:

```bash
python -m jupyter nbconvert --to notebook --execute scripts/main.ipynb --inplace --ExecutePreprocessor.timeout=300
```

O arquivo `scripts/1_results_stimulus_aggregated.csv` é sobrescrito a partir dos dados carregados pelo notebook.
