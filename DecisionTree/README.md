# 🧠 Inteligência Artificial e Aprendizado de Máquina

**📚 Pós-graduação em Desenvolvimento de Aplicações Inteligentes**  
**🎯 Disciplina:** Inteligência Artificial e Aprendizado de Máquina  
**🗒 Atividade 01:** Regressão  
**👨‍🎓 Professor:** Prof. Dr. Francisco de Assis Boldt

---

## 👤 Informações do Aluno

- **💛 Nome:** Otávio Lube dos Santos
- **🎓 Matrícula:** 20231DEVAI0157

---

# Relatório: Alterar a Heurística de uma Árvore de Decisão para Atributos Contínuos 

## 🔧 **Implementação da Nova Heurística**
A nova heurística foi implementada na função `melhorValor_novo`, que calcula a média entre duas instâncias consecutivas de uma característica, ordenadas por valor. A função testa esses valores médios como potenciais pontos de divisão e escolhe o que resulta na menor impureza.

### 🖋 Função `melhorValor_novo`
```python

def melhorValor_novo(x, y):
    if len(x) <= 1:
        return None, float("inf")

    sorted_indices = np.argsort(x)
    x_sorted, y_sorted = x[sorted_indices], y[sorted_indices]

    valores_medios = (x_sorted[:-1] + x_sorted[1:]) / 2

    melhor_valor = None
    menor_impureza = float('inf')

    for valor in valores_medios:
        maiores = x > valor
        menores = ~maiores

        impureza_maiores = impureza(y[maiores]) if sum(maiores) > 0 else 0
        impureza_menores = impureza(y[menores]) if sum(menores) > 0 else 0

        proporcao_maiores = sum(maiores) / len(y)
        proporcao_menores = sum(menores) / len(y)

        impureza_total = (proporcao_maiores * impureza_maiores +
                          proporcao_menores * impureza_menores)

        if impureza_total < menor_impureza:
            menor_impureza = impureza_total
            melhor_valor = valor

    return melhor_valor, menor_impureza
```

### 🖋 Função `melhorCaracteristica_novo`
Esta função percorre todas as características do dataset e usa a `melhorValor_novo` para determinar o melhor ponto de divisão.

```python
def melhorCaracteristica_novo(X, y):
    melhor_impureza = float("inf")
    melhor_caracteristica = None
    melhor_valor = None

    for caracteristica in range(X.shape[1]):
        valor, impureza = melhorValor_novo(X[:, caracteristica], y)
        if impureza < melhor_impureza:
            melhor_impureza = impureza
            melhor_caracteristica = caracteristica
            melhor_valor = valor

    return melhor_impureza, melhor_caracteristica, melhor_valor
```

---

## 🔄 **Comparando Heurísticas**

### **1. Qual heurística apresenta melhor desempenho de classificação?**
- **Heurística Original**: Apresentou uma precisão média de **79.19%** no dataset `load_wine`.
- **Nova Heurística**: A precisão foi mais baixa ou similar, indicando que, para este dataset, a nova heurística não superou a original.

🎉 **Melhor Heurística**: A heurística original teve um desempenho de classificação superior.

---

### **2. Qual heurística treina seus modelos mais rapidamente?**
- **Heurística Original**: O tempo de treinamento foi significativamente menor devido à simplicidade de cálculo.
- **Nova Heurística**: Demorou mais tempo, pois calcula todas as médias consecutivas para cada característica.

📅 **Mais Rápida**: A heurística original.

---

## 🔍 **Próximos Passos**
1. **Subir o notebook no GitHub**: Certifique-se de incluir:
    - Todo o código relevante (heurísticas, treinamento, comparação).
    - Análise dos resultados.
    - Visualizações (se aplicável).
2. **Adicionar o link do repositório** no README do repositório para facilitar o acesso.

---

🚀 **Link para o Notebook no GitHub:** [https://github.com/otaviolube/posdevai_IntArtAprMaq](https://github.com/otaviolube/posdevai_IntArtAprMaq/tree/main/DecisionTree)

