# Análise Exploratória de Dados - LICA

Análise Exploratória de Dados da **Carga de Energia Elétrica Diária** dos subsistemas brasileiros, utilizando dados públicos do **Operador Nacional do Sistema Elétrico (ONS)**.

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
- **Arquivo:** `data/raw/CARGA_ENERGIA_2026.csv`
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
│   ├── raw/
│   │   └── CARGA_ENERGIA_2026.csv
│   └── processed/
├── notebooks/
│   └── notebook-eda-lica.ipynb
├── reports/
│   └── figures/
│       ├── anomalias_deteccao.png
│       ├── disparidade_subsistemas.png
│       ├── multivariada_heatmap.png
│       ├── temporal_carga_subsistema.png
│       ├── temporal_perfil_semanal.png
│       └── univariada_distribuicao.png
├── review/
│   └── review.md
├── README.md
├── requirements.txt
└── .gitignore
```

---

## Como Executar

### Pré-requisitos

```bash
pip install -r requirements.txt
```

### Executando localmente

```bash
jupyter notebook notebooks/notebook-eda-lica.ipynb
```

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
- Jupyter Notebook
- pandas, numpy, matplotlib, seaborn
