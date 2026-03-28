# Impacto da IA no Mercado de Trabalho de Desenvolvimento de Software

**Projeto em Business Intelligence e Analytics — Fase 2**  
**Autor:** Carlos Eduardo Graf  
**Instituição:** PUCRS  
**Data:** Março de 2026  

---

## Descrição

Este projeto investiga se o avanço das ferramentas de Inteligência Artificial, em especial a IA generativa a partir de 2023, está associado a mudanças no mercado de trabalho de desenvolvimento de software

A hipótese central é testada por meio de análise de séries temporais, modelagem preditiva e correlação estatística entre o índice de vagas de software (FRED) e o desempenho do setor de IA (ETF AIQ).

---

## Estrutura do Repositório
```
📁 pucrs/
├── 📄 README.md
├── 📄 project.ipynb
├── 📁 data/
│   ├── 📁 fred/
│   │   └── fred_raw.csv
│   ├── 📁 market/
│   │   └── aiq_raw.csv
│   ├── 📁 google_trends/
│   │   ├── trend_ai_coding_raw.csv
│   │   └── trend_developer_demand_raw.csv
│   └── 📁 stanford/
│       ├── stanford_ai_job_posting_raw.csv
│       ├── stanford_productivity_raw.csv
│       ├── stanford_employee_change_raw.csv
│       └── stanford_reskilled_raw.csv
└── 📁 output/
    ├── fred_clean.csv
    ├── fred_trend.csv
    ├── fred_forecast.csv
    ├── aiq_clean.csv
    ├── trend_ai_coding.csv
    ├── trend_developer_demand.csv
    ├── stanford_ai_job_posting.csv
    ├── stanford_productivity.csv
    ├── stanford_employee_change.csv
    └── stanford_reskilled.csv
```

---

## Fontes de Dados

| Fonte | Descrição | Coleta |
|---|---|---|
| FRED / Indeed | Índice de vagas de software nos EUA | CSV manual |
| Yahoo Finance (yfinance) | ETF AIQ — preço de fechamento mensal | API Python |
| Google Trends | Volume de buscas: "AI Coding" e "Developer Job" | CSV manual |
| Stanford AI Index 2025 | Vagas com IA, produtividade, expectativas de emprego | CSV manual |

---

## Pipeline
```
Coleta → Seleção → Limpeza → Modelagem → Dashboard (Power BI)
```

1. **Coleta:** download via API (yfinance) e exportação manual (FRED, Google Trends, Stanford)
2. **Seleção:** apenas dados relevantes ao tema central são escolhidos
3. **Limpeza:** padronização de colunas, conversão de tipos, remoção de nulos, resampling mensal
4. **Modelagem:** regressão linear com scikit-learn — tendência e projeção 60 meses (±2σ)
5. **Dashboard:** visualizações interativas publicadas no Microsoft Power BI

---

## Principais Resultados

- Tendência de queda consistente no FRED Jobs Index a partir de jan/2023
- Correlação de Pearson **r = −0,69** entre o ETF AIQ e o FRED Jobs Index
- Crescimento contínuo de vagas que mencionam IA (Stanford AI Index)
- Maioria dos trabalhadores relata ganho de produtividade de 0–20% com uso de IA
- Aumento da proporção de respondentes que antecipa redução no quadro de funcionários em 2024 vs 2023

---

## Dependências
```bash
pip install pandas numpy scikit-learn matplotlib yfinance scipy
```

**Python:** 3.10+  
**Dashboard:** Microsoft Power BI Desktop

---

## Dashboard

Acesso ao dashboard interativo publicado no Power BI:  
🔗 *[link]*

---

## Como Executar

1. Clone o repositório:
```bash
git clone https://github.com/Cegraf/pucrs
```
2. Instale as dependências:
```bash
pip install pandas numpy scikit-learn matplotlib yfinance scipy
```
3. Abra e execute o notebook:
```bash
jupyter notebook project.ipynb
```
4. Os arquivos de output serão gerados automaticamente na pasta `output/`

---

*PUCRS — 2026*
