# Klike.AI - Desafio Técnico 
Projeto desenvolvido por Anna Luiza Braga de Albuquerque para o desafio técnico da Klike.AI

## Objetivo
Analisar as características de criativos de vídeo, prever o Klike Score e construir um protótipo de melhoria.

A base fornecida contém 500 campanhas simuladas, inspiradas em dados reais

## Como executar
É necessário ter Python e pip instalados

1. Instale as dependências:
`bash
pip install - r requirements.txt
`

2. Abra o Jupyter
`bash
jupyter notebook
`

3. Abra `analise_klike.ipynb` e execute todas as células em ordem. O CSV deve estar na mesma pasta do notebook.

## Organização da solução
- Parte 1: Qualidade dos dados, análise exploratória e visualizações.
- Parte 2: Preparação das variáveis, regressão linear e avaliação.
- Parte 3: Recomendador funcional e demonstração.
- Parte 4: Visão de produto, apresentada neste README.

## Decisões e resultados
O modelo utiliza características do vídeo e contexto da campanha disponíveis antes da publicação. Métricas posteriores, como CTR e ROAS, não são usadas como entradas.

Os valores numéricos faltantes são preenchidos com medianas calculadas no treino. A ausência de informações sobre legendas é representada separadamente e as categorias são codificadas em identificadores binários (0 e 1) a fim de calcular o Klike Score.

A regressão linear apresentou MAE de 6,15 e RMSE de 7,64 pontos. As referências pela média e mediana do treino apresentaram MAEs de 12,26 e 12,26 pontos. Na validação cruzada do treino, o MAE médio foi 7,03.

O recomendador avalia alterações individuais, ordena os ganhos previstos no Klike Score e apresenta comparações entre campanhas de treino da mesma plataforma e categoria. 

## Limitações 
As recomendações são hipóteses para teste, não são estimativas causais. Ganhos no Klike Score não garantem melhorias em conversões ou ROAS.

O protótipo pode encontrar menos de três alterações com ganho previsto para algumas campanhas. Evidências locais também podem ser insuficientes ou contradizer a previsão do modelo. Essas situações são sinalizadas.