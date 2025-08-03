**Modelo Preditivo IBOVESPA**  
Tech Challenge Fase II – FIAP Pós Tech em Data Analytics  
Equipe: [Nome dos Integrantes]  

---

## 📋 Descrição do Projeto
Este repositório reúne todo o trabalho desenvolvido em grupo para o Tech Challenge Fase II da Pós-Tech em Data Analytics da FIAP. O objetivo principal foi construir um modelo preditivo capaz de antecipar se o índice Ibovespa fechará em alta ou baixa no dia seguinte, alcançando ao menos 75% de acurácia no conjunto de teste. Após experimentação com diferentes algoritmos, a Regressão Logística foi selecionada como modelo final por sua simplicidade, interpretabilidade e excelente desempenho sem overfitting.

## 🗂️ Estrutura do Repositório
```
├── data
│   └── Dados Históricos - Ibovespa.csv        # Base de dados raw
├── notebooks
│   └── Modelo_Preditivo_Ibovespa.ipynb        # Pipeline completo em Jupyter Notebook
├── docs
│   └── Documentacao_Tecnica.pdf               # Documentação técnica detalhada
├── requirements.txt                           # Dependências Python
└── README.md                                  # Este arquivo
```

## 🔧 Pré-requisitos e Instalação
1. Clone este repositório:
   ```bash
   git clone https://github.com/seu-usuario/seu-repositorio.git
   cd seu-repositorio
   ```
2. Crie e ative um ambiente virtual (recomendado):
   ```bash
   python -m venv venv
   source venv/bin/activate      # Linux/macOS
   venv\Scripts\activate     # Windows
   ```
3. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   ```

> **Recomendação:** Trabalhar com Python ≥ 3.8.

## 🚀 Como Executar

- **Notebook Jupyter:**

  ```bash
  jupyter notebook
  ```

  Abra `notebooks/Modelo_Preditivo_Ibovespa.ipynb` e execute as células na ordem.

- **Documentação Técnica:**

  Abra `docs/Documentacao_Tecnica.pdf` em qualquer leitor de PDF.

## 🛠️ Pipeline do Projeto
1. **Aquisição e Exploração dos Dados**  
   - Carregamento e limpeza da base histórica do Ibovespa.  
   - Conversão de tipos e tratamento de valores faltantes.  

2. **Engenharia de Atributos**  
   - Cálculo de indicadores técnicos (Médias Móveis, RSI, MACD, Bandas de Bollinger, ATR, OBV).  
   - Features temporais (dia da semana, variação percentual).  

3. **Preparação e Escalonamento**  
   - Escalonamento MinMax das features numéricas.  
   - Remoção de linhas com NaN gerados pelos cálculos de janela.  

4. **Divisão de Dados**  
   - Treino: todos os dados até 30 dias antes do fim da série.  
   - Teste: últimos 30 dias para simulação de previsão.  

5. **Desenvolvimento e Avaliação de Modelos**  
   - CatBoost, LightGBM, RandomForest e Regressão Logística.  
   - Validação temporal (`TimeSeriesSplit`) para otimização de hiperparâmetros.  

6. **Seleção do Modelo Final**  
   - Regressão Logística selecionada por apresentar:  
     - Acurácia de teste de 80%.  
     - Ausência de overfitting (diferença negativa entre treino e teste).  

7. **Resultados e Métricas**  
   - Matriz de Confusão, Curva ROC/AUC, Precisão, Recall e F1-Score.

## 👥 Equipe
- **[Nome Integrante 1]** – Análise de dados e feature engineering
- **[Nome Integrante 2]** – Modelagem e validação
- **[Nome Integrante 3]** – Documentação e apresentação

## 📑 Licença
Este projeto está licenciado sob a [MIT License](LICENSE).

---

> Para dúvidas ou sugestões, abra uma issue ou entre em contato através do e-mail: [seu.email@exemplo.com](mailto:seu.email@exemplo.com)

