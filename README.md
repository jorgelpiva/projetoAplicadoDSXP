# 🛒 Projeto Aplicado — Previsão de Conversão em E-commerce

## 📌 Descrição do Projeto
Este projeto foi desenvolvido como parte do curso de **Pós-Graduação em Data Science (XP Educação)**, com o objetivo de construir um modelo preditivo capaz de identificar a probabilidade de conversão de clientes em um e-commerce, a partir de dados de navegação coletados no site.

O dataset utilizado foi o **Online Shoppers Purchasing Intention Dataset**, obtido no [Kaggle](https://www.kaggle.com/datasets). Ele contém informações de comportamento de navegação, páginas acessadas e conversões realizadas pelos usuários.

---

## 🎯 Objetivos
- Analisar e tratar os dados de navegação de usuários de e-commerce.  
- Testar diferentes algoritmos de Machine Learning.  
- Lidar com **desbalanceamento de classes** usando técnicas como SMOTE e undersampling.  
- Atingir **mínimo de 0.75 no F1-score** como meta SMART.  
- Implementar rastreamento de experimentos com **MLflow**.  
- Simular predições em produção (holdout temporal).  
- Interpretar resultados com **Feature Importance** e **SHAP**.  
- Gerar recomendações de negócio baseadas nos insights.  

---

## 🏗️ Estrutura das Sprints

### 🔹 Sprint 1 — Preparação e Modelagem Inicial
- Exploração inicial do dataset e criação do **dicionário de dados**.  
- Implementação da função de **pré-processamento híbrido** (`encode_features`).  
- Identificação de outliers relevantes.  
- Divisão temporal dos dados (treino e holdout em dezembro).  

### 🔹 Sprint 2 — Modelagem Avançada e Avaliação
- **Treinamento de mais de 1.300 modelos**, explorando combinações de algoritmos e hiperparâmetros.  
- Rastreio completo dos experimentos com **MLflow**.  
- Modelos com melhor desempenho:  
  - **MLP (undersampling)** → F1=0.821, Recall=0.875  
  - **Random Forest (undersampling)** → F1=0.809, Recall=0.857  
  - **XGBoost (undersampling)** → F1=0.804, Recall=0.857  
- Criação de gráfico radar comparando métricas (Accuracy, Precision, Recall, AUC e F1).  

### 🔹 Sprint 3 — Produção Simulada e Explicabilidade
- Criação de notebook dedicado à **simulação em produção** com o holdout (dezembro).  
- Carregamento dos melhores modelos diretamente do **MLflow**.  
- Resultados em produção simulada: **F1 ≈ 0.50–0.55**, com **recall >0.83**.  
- Análise de interpretabilidade: **PageValues e PageValues_Outlier** como variáveis mais relevantes, além de indicadores de abandono (ExitRates, BounceRates).  

---

## 📊 Principais Resultados
- **Meta SMART alcançada em validação temporal**: F1 > 0.80.  
- **Produção simulada (holdout dezembro)**: F1 caiu para ~0.55, mas recall se manteve elevado.  
- **Insights de negócio**:  
  - PageValues e outliers → fortes preditores de conversão.  
  - ExitRates e BounceRates → indicadores de abandono importantes.  
  - VisitorType (Returning vs. New) → influencia na probabilidade de compra.  

---

## 💡 Recomendações de Negócio
- **Otimizar páginas com alto ExitRate/BounceRate**, reduzindo abandono.  
- **Priorizar clientes com PageValues atípicos** em campanhas de remarketing.  
- Ampliar coleta de dados para incluir **mais anos de histórico**, fortalecendo a sazonalidade.  
- Integrar rastreamento de **navegabilidade web em tempo real**, criando modelos mais robustos.  
- Estimular a integração entre **engenharia de software, ciência de dados e área de negócio** para sistemas inteligentes aplicados a e-commerce.  

---

## 🚀 Próximos Passos
- Implementar **retrain periódico** (mensal ou trimestral).  
- Expandir o uso de **redes neurais** (ex.: LSTMs para sequências temporais).  
- Desenvolver **dashboards em tempo real** para monitorar conversões e métricas de modelo.  
- Testar técnicas de balanceamento alternativas (SMOTE-Tomek, focal loss).  

---

## 🛠️ Tecnologias Utilizadas
- **Linguagem**: Python  
- **Bibliotecas**: Pandas, Numpy, Scikit-learn, XGBoost, TensorFlow/Keras, SHAP  
- **MLOps**: MLflow  
- **Visualização**: Matplotlib, Seaborn  
- **Ambiente**: Jupyter Notebook, VS Code  

---

## 📁 Estrutura do Repositório
📦 projeto-aplicado
┣ 📂 dados
┃ ┣ online_shoppers_intention.csv
┃ ┣ df_holdout.csv
┃ ┗ holdout_dezembro.csv
┣ 📂 notebooks
┃ ┣ sprint1_modelagem_inicial.ipynb
┃ ┣ sprint2_experimentos_avancados.ipynb
┃ ┣ sprint3_producao_simulada.ipynb
┃ ┗ interpretabilidade_features.ipynb
┣ 📂 mlruns
┃ ┗ ... (artefatos dos modelos)
┣ README.md
┗ requirements.txt


---

📌 **Observação final**:  
Apesar de utilizarmos um dataset público limitado (10 meses de histórico), os experimentos mostraram que é possível construir pipelines robustos de ML para prever intenção de compra em e-commerce. Esse projeto pode ser facilmente **replicado em empresas reais**, integrando dados de navegabilidade, engenharia de software e estratégias de marketing digital.  
