# Atividade 01 (ATIV-01) - Conceitos Básicos de Machine Learning

### 1. Explique, com suas palavras, o que é machine learning?
Para mim, Machine Learning é uma forma de fazer com que os computadores aprendam a resolver problemas e tomar decisões a partir de dados históricos, sem que a gente precise programar regras estáticas (como um monte de `if/else`) para cada cenário. Em vez de ditar o caminho exato, nós alimentamos um algoritmo com exemplos. Ele analisa essa base, encontra padrões ocultos que humanos dificilmente veriam de primeira, e cria um modelo capaz de classificar ou prever novos resultados quando receber dados que nunca viu antes.

---

### 2. Explique o conceito de conjunto de treinamento, conjunto de validação e conjunto de teste em machine learning.
Para garantir que o modelo realmente aprendeu a lógica do problema (e não apenas decorou as respostas), nós dividimos a base de dados em três partes:
* **Conjunto de Treinamento:** É a maior parte dos dados. É aqui que o algoritmo "estuda". Ele usa esses registros para ajustar seus parâmetros internos e entender a relação entre as variáveis.
* **Conjunto de Validação:** Funciona como um simulado durante o desenvolvimento. Usamos essa parte para testar diferentes configurações do algoritmo (hiperparâmetros) e monitorar se ele não está sofrendo de *overfitting* (quando ele fica bom demais nos dados de treino, mas erra em qualquer outra coisa).
* **Conjunto de Teste:** É o teste final do "mundo real". Esses dados ficam totalmente separados e o modelo nunca os vê durante o treino ou validação. Só usamos essa base no final de tudo para medir a real capacidade de generalização do sistema.

---

### 3. Explique como você lidaria com dados ausentes em um conjunto de dados de treinamento.
A abordagem depende muito da quantidade de dados faltantes e do impacto que eles têm no problema. Eu adotaria as seguintes estratégias:
* **Eliminação:** Se forem pouquíssimas linhas com valores ausentes em uma base gigante, o mais simples e seguro é deletar esses registros. Se uma coluna inteira estiver praticamente vazia e não for crucial, eu removeria a coluna.
* **Imputação Estatística:** Preencher os vazios usando a própria distribuição dos dados. Para variáveis numéricas, usaria a **mediana** (para evitar distorções por valores extremos) ou a **média**. Para variáveis categóricas, preencheria com a **moda** (o valor mais frequente).
* **Imputação Preditiva (Avançada):** Usar um algoritmo auxiliar (como o KNN ou uma regressão simples) para prever qual seria o valor daquele campo que está faltando, baseando-se no comportamento das outras colunas da mesma linha.
* **Uso de Modelos Tolerantes:** Optar por algoritmos baseados em árvores de decisão (como XGBoost ou LightGBM), que conseguem lidar nativamente com valores nulos sem quebrar o treinamento.

---

### 4. O que é uma matriz de confusão e como ela é usada para avaliar o desempenho de um modelo preditivo?
A matriz de confusão é uma tabela que cruza as previsões feitas pelo modelo com os resultados reais do conjunto de teste. Ela divide os resultados em quatro cenários fundamentais: Verdadeiros Positivos (acertou o positivo), Verdadeiros Negativos (acertou o negativo), Falsos Positivos (deu alarme falso) e Falsos Negativos (deixou passar o que era importante).

Em vez de olhar só para a acurácia geral (que engana muito se os dados forem desbalanceados), usamos a matriz para extrair métricas direcionadas:
* **Precisão:** De tudo que o modelo disse que era positivo, quanto ele realmente acertou? (Essencial quando um alarme falso custa caro).
* **Recall (Sensibilidade):** De todos os casos positivos reais que existiam, quanto o modelo conseguiu capturar? (Essencial em cenários como detecção de fraudes ou diagnósticos médicos).
* **F1-Score:** Um balanço (média harmônica) entre precisão e recall, ótimo para avaliar o modelo de forma única.

---

### 5. Em quais áreas (tais como construção civil, agricultura, saúde, manufatura, entre outras) você acha mais interessante aplicar algoritmos de machine learning?
Acho mais interessante aplicar Machine Learning no próprio ecossistema de **Tecnologia** e em melhorias de **Automação de Sistemas** que já existem. O potencial de otimizar o desenvolvimento e a infraestrutura de software usando inteligência me chama muito a atenção:

* **Automação do Ciclo de Desenvolvimento (AIOps e Ferramentas de Código):** A evolução de ferramentas que já usavam automações simples (como linters e scripts de CI/CD) para sistemas que usam Machine Learning é gigante. Aplicar modelos para prever falhas em servidores antes que elas aconteçam, analisar logs de infraestrutura em tempo real para detectar anomalias, ou usar modelos preditivos para otimizar a alocação de recursos em nuvem (como instâncias AWS/Azure) reduz custos de forma inteligente e dinâmica.
* **Sistemas de Recomendação e Hiperpersonalização:** Aprimorar engenharias de busca e algoritmos de recomendação em plataformas existentes. Usar modelos avançados para entender o comportamento do usuário em tempo real e automatizar a entrega de conteúdos, produtos ou APIs específicas melhora drasticamente a experiência digital sem a necessidade de intervenção humana manual.
