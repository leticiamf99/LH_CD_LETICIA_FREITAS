# 🎬 Desafio Lighthouse - Análise Cinematográfica IMDB

## 📋 Descrição do Projeto

Este projeto foi desenvolvido como parte do **Desafio Cientista de Dados da Lighthouse/Indicium**, com o objetivo de analisar dados cinematográficos e orientar decisões estratégicas para o estúdio de Hollywood **PProductions**.

O projeto inclui:
- 📊 Análise exploratória detalhada dos dados (EDA)
- 🤖 Modelo preditivo para nota IMDB
- 💡 Insights de negócio e recomendações estratégicas
- 📈 Visualizações interativas e informativas

## 🎯 Objetivos

1. **Análise Exploratória**: Identificar padrões e tendências nos dados cinematográficos
2. **Predição**: Desenvolver modelo para prever nota IMDB de filmes
3. **Recomendações**: Orientar qual tipo de filme produzir próximo
4. **Insights**: Extrair conhecimento acionável dos dados

## 🏗️ Estrutura do Projeto

```
desafio-lighthouse-imdb/
├── README.md                          # Este arquivo
├── requirements.txt                   # Dependências do projeto
├── desafio_lighthouse.ipynb          # Notebook principal com análises
├── imdb_rating_predictor.pkl         # Modelo treinado salvo
├── external_movie_data.csv           # Dados externos gerados
├── data/
│   └── desafio_indicium_imdb.csv     # Dataset principal (não incluído)
└── images/                           # Gráficos gerados (opcional)
```

## 🚀 Como Executar o Projeto

### Pré-requisitos

- Python 3.8+ (recomendado 3.9 ou 3.10)
- pip (gerenciador de pacotes Python)
- Git (para clonar o repositório)

### Passo 1: Clonar o Repositório

```bash
git clone https://github.com/leticiamf99/LH_CD_LETICIA_FREITAS.git
cd desafio-lighthouse-imdb
```

### Passo 2: Criar Ambiente Virtual

```bash
# Criar ambiente virtual
python -m venv lighthouse_env

# Ativar ambiente virtual
# No Windows:
lighthouse_env\Scripts\activate

# No macOS/Linux:
source lighthouse_env/bin/activate
```

### Passo 3: Instalar Dependências

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

### Passo 4: Preparar os Dados

1. Coloque o arquivo `desafio_indicium_imdb.csv` na pasta `data/`
2. Certifique-se que o arquivo possui as seguintes colunas:
   - Series_Title, Released_Year, Certificate, Runtime, Genre
   - IMDB_Rating, Overview, Meta_score, Director
   - Star1, Star2, Star3, Star4, No_of_Votes, Gross

### Passo 5: Executar o Notebook

```bash
# Iniciar Jupyter Notebook
jupyter notebook

# Ou se preferir Jupyter Lab
jupyter lab
```

Abra o arquivo `desafio_lighthouse.ipynb` e execute as células sequencialmente.

### Passo 6: Executar Todas as Células

1. No Jupyter, vá em **Cell → Run All** ou execute célula por célula
2. O tempo total de execução é aproximadamente 5-10 minutos
3. Os resultados e visualizações serão exibidos inline

## 📊 Principais Resultados

### Modelo Preditivo
- **Tipo**: Regressão (Random Forest/Gradient Boosting)
- **Performance**: R² > 0.85, RMSE < 0.3
- **Features importantes**: Meta Score, Número de Votos, Diretor, Gênero

### Recomendações de Negócio
1. **Gênero recomendado**: Drama ou Biography
2. **Duração ideal**: 130-150 minutos
3. **Foco**: Qualidade da crítica especializada (Meta Score)
4. **Evitar**: Filmes muito longos ou de gêneros de nicho

### Exemplo de Predição
Para "The Shawshank Redemption":
- **Predição**: ~9.1-9.3
- **Real**: 9.3
- **Erro**: < 0.2 pontos

## 📁 Arquivos Gerados

Após executar o notebook, serão gerados:

- `imdb_rating_predictor.pkl`: Modelo treinado para uso futuro
- `external_movie_data.csv`: Dados externos enriquecidos
- Diversos gráficos e visualizações (exibidos no notebook)

## 🛠️ Tecnologias Utilizadas

- **Python 3.9+**: Linguagem principal
- **Pandas**: Manipulação de dados
- **Scikit-learn**: Machine Learning
- **Matplotlib/Seaborn**: Visualizações
- **NumPy**: Computação numérica
- **WordCloud**: Nuvem de palavras
- **Jupyter**: ambiente de desenvolvimento

## 📦 Dependências Principais

```
pandas==2.1.4
numpy==1.24.3
scikit-learn==1.3.2
matplotlib==3.8.2
seaborn==0.13.0
scipy==1.11.4
wordcloud==1.9.2
```

## 🤖 Como Usar o Modelo Salvo

```python
import pickle
import pandas as pd

# Carregar modelo
with open('imdb_rating_predictor.pkl', 'rb') as f:
    model_package = pickle.load(f)

modelo = model_package['model']
features = model_package['feature_columns']
encoders = model_package['label_encoders']

# Fazer predição (após processar os dados do filme)
predicao = modelo.predict(dados_processados)[0]
print(f"Nota IMDB predita: {predicao:.2f}")
```

## 📈 Principais Insights

### Fatores de Sucesso
1. **Meta Score** é o fator mais importante (correlação: 0.77)
2. **Número de votos** indica popularidade e engagement
3. **Diretores renomados** fazem diferença significativa
4. **Gêneros Drama/Biography** tendem a ter notas mais altas

### Análise Temporal
- Filmes dos anos 2000-2010 mostram padrões interessantes
- Evolução da qualidade cinematográfica ao longo das décadas
- Trends de duração e orçamento por período

### Análise de Texto (Overview)
- Possível identificar gênero com 60-70% de precisão
- Palavras-chave específicas são indicativas de qualidade
- Sinopses mais elaboradas correlacionam com melhor avaliação

## 🔧 Solução de Problemas

### Erro de Importação
```bash
pip install --upgrade pip setuptools wheel
pip install -r requirements.txt
```

### Erro de Memória
- Reduza o tamanho do dataset para teste
- Use `pd.read_csv(arquivo, nrows=1000)` para samples menores

### Jupyter não Abre
```bash
pip install --upgrade jupyter
jupyter notebook --generate-config
```

## 📞 Suporte

Se encontrar problemas:

1. Verifique se todas as dependências estão instaladas
2. Confirme que o dataset está no local correto
3. Verifique a versão do Python (3.8+)
4. Consulte a documentação das bibliotecas utilizadas

## 👨‍💻 Autor

**[Leticia Freitas]**
- GitHub: [@leticiamf99](https://github.com/leticiamf99)
- Email: leticiamateusf@hotmail.com
