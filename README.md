# 🧠 Inteligência Artificial e Aprendizado de Máquina

**📚 Pós-graduação em Desenvolvimento de Aplicações Inteligentes**  
**🎯 Disciplina:** Inteligência Artificial e Aprendizado de Máquina  
**📝 Atividade 01:** Regressão  
**👨‍🏫 Professor:** Prof. Dr. Francisco de Assis Boldt

---

## 👤 Informações do Aluno

- **📛 Nome:** Otávio Lube dos Santos
- **🎓 Matrícula:** 20231DEVAI0157

---

## 📋 Descrição da Atividade

Esta é a **primeira atividade prática** da disciplina de **Inteligência Artificial e Aprendizado de Máquina**. O objetivo é implementar os conceitos de regressão utilizando um dataset alternativo, já que o `load_boston` não está mais disponível no scikit-learn.

Os passos principais incluem:

1. 🔄 Substituir o dataset `load_boston` por outro dataset adequado para regressão.
2. 🛠️ Reproduzir as atividades apresentadas nos vídeos em um Jupyter Notebook.
3. 💾 Salvar o notebook em um repositório público no GitHub.
4. 📎 Compartilhar o link do repositório como entrega da atividade.

---

## 📊 Detalhes do Dataset

Como o dataset `load_boston` foi descontinuado, a solução proposta utiliza uma **fonte alternativa para carregar o dataset Boston Housing**. A abordagem alternativa segue os seguintes passos:

- **🌐 Fonte do dataset:**  
  O dataset pode ser obtido de outras fontes públicas, como [Kaggle](https://www.kaggle.com) ou repositórios de exemplos em Python.

- **📥 Carregamento do Dataset:**  
  O código abaixo mostra como carregar o dataset Boston Housing diretamente de outra fonte utilizando pandas:

  ```python
  import pandas as pd

  # URL do dataset (exemplo com link público)
  url = "https://raw.githubusercontent.com/selva86/datasets/master/BostonHousing.csv"

  # Carregar o dataset em um DataFrame
  df = pd.read_csv(url)
  print(df.head())
  ```
