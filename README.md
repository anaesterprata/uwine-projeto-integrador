# 🍷 UWine – Clube de Vinhos da UVV | Projeto Integrador (Parte 1)

**Autora:** Ana Ester Prata
**Curso:** Ciência de Dados – Universidade Vila Velha (UVV)
**Disciplina:** Projeto Integrador (TCC)

📓 **Notebook no Colab:** [[abrir no Google Colab](COLE_AQUI_O_LINK_DO_COLAB)](https://colab.research.google.com/drive/1NriVmCjVx_HvEXyTZutuZVdnXElt8887#scrollTo=s-dQrFY-kr0r)
🎥 **Vídeo de apresentação:** [assistir no YouTube](COLE_AQUI_O_LINK_DO_YOUTUBE)

---

## Sobre o projeto

O UWine é um clube de vinhos universitário fictício. Como consultora em Ciência de Dados, analisei uma base com **1.120.000 notas fiscais (~350 MB)**, que recebe cerca de **5.000 novas notas por dia**.

**Pergunta principal da Parte 1:** *qual é o tamanho ideal da amostra para estimar o gasto dos clientes (TOTAL R$)?*

## Resposta

> **O tamanho ideal da amostra é de 50.300 notas fiscais** (cerca de 4,5% da base), distribuídas entre os tipos de conta ESSENTIAL, VIP e PRIME pela alocação ótima de Neyman.

## O que foi feito

| Atividade | Descrição | Principais resultados |
|---|---|---|
| **A1.1** Tamanho ideal da amostra | Estabilização marginal do erro-padrão (procedimento empírico) e erro-padrão estratificado com otimização de Neyman, validados por bootstrap | n ideal = 50.300; a média real da população ficou dentro do IC 95% do bootstrap |
| **A1.2** Outliers | Boxplot e regra 1,5 × IQR, calculada dentro de cada tipo de conta | Outliers removidos por inflarem o desvio-padrão |
| **A1.3** Testes de hipóteses | Duas amostras independentes do tamanho ideal (SAMPLE 1 e SAMPLE 2) | Ver tabela abaixo |
| **A2** Estatística descritiva | Medidas de resumo, histogramas, Pareto e boxplots | O tipo da conta é a variável que mais diferencia o gasto |
| **A3** Pesquisa de satisfação | 25 opiniões discretizadas em notas de 1 a 5, com bootstrap, geral e por sexo | 80% satisfeitos e 5% insatisfeitos, sem diferença entre os sexos |

### Testes de hipóteses (SAMPLE 1 × SAMPLE 2)

| Teste | BEST FIT | p-value | Conclusão |
|---|---|---|---|
| Normalidade | Anderson-Darling | — | Dados **não** normais |
| Independência | Spearman | 0,0579 | Independentes |
| Mesma distribuição | Kolmogorov-Smirnov | 0,9134 | Mesma distribuição |
| Médias amostrais | t de Student | 0,5445 | Médias iguais (R$ 1.232,83 × R$ 1.228,63) |

### Pesquisa de satisfação (geral)

| Nota | Classificação | % |
|---|---|---|
| 5 | Muito Satisfeito | 3% |
| 4 | Satisfeito | 77% |
| 3 | Indiferente | 15% |
| 2 | Insatisfeito | 4% |
| 1 | Muito Insatisfeito | 1% |

## Arquivos do repositório

| Arquivo | Conteúdo |
|---|---|
| `Ana_Ester_Prata_WORKFLOW_PARTE_1.ipynb` | Notebook completo, com código, gráficos e respostas |
| `requirements.txt` | Bibliotecas Python utilizadas |
| `README.md` | Esta descrição |

> A base de dados (`table1.csv`, ~350 MB) **não** está no repositório, porque o GitHub não aceita arquivos acima de 100 MB. Ela foi fornecida pela disciplina.

## Como executar

1. Abra o notebook no Google Colab pelo link acima.
2. Envie o arquivo `table1.csv` para o Colab (painel de arquivos) ou monte o Google Drive.
3. Ajuste o caminho do arquivo na célula de carregamento, se necessário.
4. Clique em **Ambiente de execução → Executar tudo** (leva cerca de 2 minutos).

## Tecnologias

Python · pandas · NumPy · SciPy · Matplotlib · Seaborn · Google Colab
