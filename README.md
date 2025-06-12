# Previsão de Churn e Comportamentos de Desligamento Silencioso em Colaboradores
---
**Todas as análises detalhadas, gráficos interativos e etapas de modelagem estão disponíveis no notebook .ipynb. Recomenda-se sua leitura para uma compreensão completa dos resultados.**
---
#Introdução

Nos últimos 3 anos, diversas tendências com resultados negativos têm se popularizado entre jovens da geração Z e Millenial, termos como "Quiet Quitting" , "Rage Applying" e "Revenge Quitting" descrevem um comportamento silencioso de revolta relacionados a desconexão emocional e motivacional com o trabalho, esgotamento, falta de reconhecimento ou baixa qualidade de vida, por exemplo:

1. Quiet Quitting
Ocorre quando profissionais deixam de se engajar além do mínimo necessário, cumprindo apenas as responsabilidades básicas do cargo sem assumir tarefas extras ou demonstrar envolvimento adicional.

2. Revenge Quitting
Ocorre quando funcionários se demitem impulsivamente de uma empresa motivados por frustrações ou ressentimento acumulado dentro do ambiente de trabalho.

3. Rage Applying
Define funcionários que buscam novas oportunidades de emprego não por estarem pragmaticamente buscando novas oportunidades, mas por estarem frustrados com o atual ambiente de trabalho.

Eventualmente, todas esses termos convergem para o mesmo ponto: desligamentos abruptos do ambiente de trabalho, causando queda de produtividade, desmotivação em cadeia e reputação negativa da empresa. Uma empresa que investe anos de recurso capacitando um profissional por exemplo, pode se deparar no dia seguinte com a perda de um talento estratégico que poderia ter sido evitado.

Assim, esse projeto tem por objetivo avaliar uma base de dados de uma pesquisa realizada com funcionários, visando obter insights sobre a satisfação de profissionais e ambiente de trabalho de diferentes áreas e evitar os comportamentos acima citados, além disso, criar um modelo capaz de prever a probabilidade de um funcionário se demitir abruptamente.

---

# Etapas

1. Entendimento dos Dados
2. Análise Exploratória dos Dados
3. Conclusões Parciais
4. Criação de variáveis de risco
5. 5.Seleção de variáveis relevantes
6. Treinamento de modelos: Random Forest, Logistic Regression e XGBoost
7. Avaliação e comparação dos modelos
8. Visualizações de análise (scatterplots)
9. Conclusões e implicações práticas
    
---

#Ferramentas
- Python 
- Pandas, Scikit-learn, XGBoost
- Seaborn, Matplotlib
- Jupyter Notebook

---

#Exemplos de Visualizações

---

#Resultados e Discussão

A análise preditiva sobre o risco de churn (rotatividade voluntária) revelou padrões comportamentais e emocionais relevantes, que foram capturados tanto pelas análises estatísticas quanto pelos modelos de machine learning.

1. Insights Exploratórios
Durante a análise exploratória, observamos que a maioria dos colaboradores com alta propensão ao churn é composta por jovens com pouca ou nenhuma experiência prévia, muitos dos quais estão em seus primeiros empregos. Isso reforça o alinhamento com tendências de mercado em que membros das Gerações Z e Millennials são os que mais pedem demissão voluntária.
Variáveis como horas de sono e atividade física apresentaram distribuição aproximadamente normal, sugerindo influência limitada no risco de saída. No entanto, fatores como satisfação no trabalho, nível de estresse, equilíbrio trabalho-vida (WLB) e carga de trabalho mostraram-se muito mais relevantes.

2. Clusterização de Perfis
- A aplicação de algoritmos de clusterização permitiu segmentar a população em três grupos distintos, com o Grupo 0 sendo o mais crítico, composto por colaboradores com:
- Baixa satisfação no trabalho
- Alto nível de estresse
- Baixo equilíbrio entre vida pessoal e profissional
- Alta carga de treinamentos, mas sem impacto positivo claro
- 
Essa configuração indica alto risco de churn, muitas vezes relacionado a comportamentos como rage applying ou revenge quitting.
Por outro lado, o Grupo 2 apresentou o melhor cenário, com boa satisfação, baixo estresse e bom WLB, servindo como referência para as condições ideais de retenção.

3. Desempenho dos Modelos Preditivos
Foram utilizados três modelos de classificação:
- Random Forest
- XGBoost
- Regressão Logística

Os modelos de Random Forest e XGBoost alcançaram 100% de acurácia nos dois targets (ChurnRisk_cluster e ChurnRisk_regra), sugerindo que os padrões nos dados são altamente discerníveis.
A Regressão Logística, modelo linear mais simples, teve desempenho competitivo, especialmente no target ChurnRisk_regra (F1-score ≈ 0.97), mas com desempenho mais modesto para ChurnRisk_cluster (F1-score ≈ 0.7 na classe de churn alto).

Isso indica que o risco de churn não é totalmente linear, mas ainda assim previsível com base nas variáveis selecionadas.

#Conclusão

O modelo de previsão de churn, que classifica os colaboradores com maior risco (valor 1) baseado em variáveis como estresse, equilíbrio trabalho-vida (WLB), satisfação no trabalho e horas de treinamento, apresentou alta capacidade de identificar grupos vulneráveis à rotatividade.

Essa segmentação nos permite conectar o risco de churn com comportamentos emergentes no ambiente de trabalho:

**Quiet Quitting:** colaboradores com baixa satisfação e equilíbrio trabalho-vida ruim, mas que ainda permanecem no emprego, possivelmente realizando apenas o mínimo necessário, indicados pelos grupos de risco do modelo.

**Rage Applying:** colaboradores estressados e insatisfeitos podem buscar ativamente outras oportunidades, aumentando o risco de saída, comportamento previsto pelo modelo em grupos com alto estresse e baixa satisfação.

**Revenge Quitting:** o abandono motivado por frustrações acumuladas, possivelmente sinalizado por baixos índices de WLB e alta carga de trabalho, características também captadas pelo modelo.

Portanto, a variável ChurnRisk_cluster = 1 identifica colaboradores que apresentam características compatíveis com esses comportamentos prejudiciais à empresa, oferecendo uma ferramenta valiosa para ações preventivas de retenção, como intervenções focadas em melhorar a satisfação, reduzir o estresse e promover o equilíbrio trabalho-vida.



