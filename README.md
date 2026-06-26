
# IMC, Tabagismo e Custos de Saúde: uma Análise de Regressão

Esse repositório contém o trabalho final da disciplina de **Análise de Regressão** (IMECC/UNICAMP, 2026), que desenvolvi em grupo com mais três colegas: Arthur Agostinho Furlan Teixeira, João Eduardo Pastori Garcia e Luiz Eduardo Costa Martins Rodrigues.

## Sobre o trabalho

O objetivo foi aplicar as técnicas de regressão linear vistas ao longo do semestre a um problema real. Escolhemos o [Medical Cost Personal Dataset](https://www.kaggle.com/datasets/mirichoi0218/insurance), que reúne dados de 1.338 beneficiários de planos de saúde privados nos EUA, e nos propusemos a responder: **quais características individuais determinam o custo médico anual cobrado pelo plano, e em que medida o IMC e o tabagismo contribuem para isso?**

O achado central é uma **interação entre IMC e tabagismo**: entre não fumantes, o IMC praticamente não altera o custo; entre fumantes, o custo dispara à medida que o IMC aumenta acima de 30 (faixa de obesidade). Esse padrão foi captado pelo modelo final:

```
log(charges) ~ age + bmi + children + sex + smoker + region + smoker:bmi
```

O modelo explica cerca de 78% da variabilidade do log-custo (R² ajustado = 0,782).

## Estrutura do repositório

- `TF.Rmd` — relatório principal em R Markdown (fonte para gerar o PDF)
- `TF.pdf` — relatório compilado
- `referencia.bib` — referências bibliográficas
- `imagens/` — logos institucionais usados na capa
- `analises_extras.Rmd` — rascunho exploratório usado durante o desenvolvimento (não faz parte do relatório final)
- `2026_TF.Rproj` — projeto RStudio

## Como reproduzir

Abra `2026_TF.Rproj` no RStudio e compile `TF.Rmd`. O dataset é baixado automaticamente de um espelho público no GitHub, sem necessidade de arquivo local.

Pacotes necessários: `tidyverse`, `knitr`, `GGally`, `lmtest`, `broom`, `bookdown`, `gridExtra`.

