# EDA_LICA

Análise Exploratória de Dados da **Carga de Energia Elétrica Diária** dos subsistemas brasileiros, utilizando dados públicos do **Operador Nacional do Sistema Elétrico (ONS)**.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/JhonatanMotaDev/EDA_LICA/blob/main/EDA_LICA2.ipynb)

---

## Objetivo

Investigar o comportamento da carga de energia elétrica nos subsistemas brasileiros ao longo do tempo.

**Pergunta principal:** Quais padrões temporais e diferenças regionais podem ser observados na carga de energia elétrica dos subsistemas brasileiros?

O foco da análise está na identificação de:

- Padrões temporais e tendências
- Sazonalidade
- Diferenças entre subsistemas (Norte, Nordeste, Sul, Sudeste/Centro-Oeste)
- Anomalias e outliers

---

## Dataset

- **Fonte:** [Operador Nacional do Sistema Elétrico (ONS)](https://dados.ons.org.br/)
- **Arquivo:** `CARGA_ENERGIA_2026.csv`
- **Período analisado:** 01/01/2026 a 10/05/2026 (130 dias por subsistema)
- **Total de registros:** 520 (4 subsistemas × 130 dias)

### Variáveis principais

| Variável | Tipo | Descrição |
|---|---|---|
| `din_instante` | datetime | Data do registro |
| `nom_subsistema` | categórica | Subsistema (Norte, Nordeste, Sul, Sudeste/Centro-Oeste) |
| `val_cargaenergiamwmed` | numérica | Carga média de energia em MWmed |
| `dia_semana` | categórica | Dia da semana (Segunda a Domingo) |
| `mes` / `ano` | temporal | Mês e ano extraídos para agrupamentos |
| `is_weekend` | booleana | Indica se o registro é de fim de semana |

---

## Principais Insights

- **Amplitude:** A carga varia de ~7.500 a ~52.500 MWmed entre os subsistemas
- **Distribuição assimétrica:** Skewness de 1.08 — a maioria do tempo a carga está em níveis baixos/médios, com picos extremos ocasionais
- **Disparidade regional:** O subsistema Sudeste/Centro-Oeste concentra a maior demanda energética
- **Padrão semanal:** Queda de consumo nos fins de semana, refletindo menor atividade industrial
- **Dataset balanceado:** 130 registros por subsistema, sem valores ausentes ou duplicados

---

## Estrutura do Repositório

```
EDA_LICA/
├── data/
│   ├── raw/              # Dados originais (não versionados)
│   └── processed/        # Dados tratados
├── notebooks/
│   └── EDA_LICA2.ipynb   # Notebook principal da análise
├── reports/
│   └── figures/          # Gráficos exportados
├── review/
│   └── review.md         # Feedback técnico da análise
├── README.md
├── requirements.txt
└── .gitignore
```

> **Nota:** O dataset não está incluído no repositório. Veja as instruções de execução abaixo para obtê-lo.

---

## Como Executar

### Pré-requisitos

```bash
pip install -r requirements.txt
```

### Obtendo os dados

1. Acesse o portal de dados abertos do ONS: [https://dados.ons.org.br/](https://dados.ons.org.br/)
2. Baixe o arquivo de **Carga de Energia Diária**
3. Salve em `data/raw/CARGA_ENERGIA_2026.csv`

### Executando localmente

```bash
jupyter notebook notebooks/EDA_LICA2.ipynb
```

### Executando no Google Colab

Clique no badge no topo deste README ou acesse o link direto do notebook.

> Ao usar o Colab, ajuste o caminho do arquivo no notebook para apontar para o seu Google Drive ou faça upload direto do arquivo.

---

## Dependências

```
pandas
numpy
matplotlib
seaborn
```

---

## Tecnologias

- Python 3.x
- Jupyter Notebook / Google Colab
- pandas, numpy, matplotlib, seaborn
