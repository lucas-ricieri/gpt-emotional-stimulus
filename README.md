# GPT Emotional Stimulus

Este é um projeto de replicação desenvolvido para a disciplina de Engenharia de Software Experimental da UTFPR, campus Campo Mourão.

A replicação usou como base o artigo **[Can ChatGPT emulate humans in software engineering surveys?](https://dl.acm.org/doi/10.1145/3674805.3690744)**. As alterações realizadas nos prompts e a criação dos novos prompts com estímulos emocionais foram inspiradas no artigo **[Large Language Models Understand and Can Be Enhanced by Emotional Stimuli](https://arxiv.org/abs/2307.11760)**.

## Organização dos Arquivos

- `paper/`: contém o artigo base utilizado na pesquisa.
- `prompts/`: contém os prompts usados no estudo, incluindo o prompt original sem estímulo emocional e os prompts modificados com diferentes estímulos emocionais.
- `prompts/emotional_stimulus/`: contém o arquivo com os estímulos emocionais usados como referência para a criação dos prompts.
- `original_answers/`: contém a planilha com as respostas do prompt vanilla, usada como baseline da comparação.
- `stimulus_answers/`: contém a planilha com as respostas obtidas a partir dos prompts com estímulos emocionais.
- `scripts/`: contém o notebook principal da análise e o dataset agregado gerado a partir das respostas.

## Arquivos Principais

- `scripts/main.ipynb`: notebook usado para carregar os dados, agregar os resultados e gerar os gráficos comparativos.
- `scripts/1_results_stimulus_aggregated.csv`: dataset agregado com baseline e prompts emocionais, usado nas análises finais.
