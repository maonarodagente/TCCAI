# Notebooks

Todos os notebooks foram executados no Google Colab. Eles leem os dados do Google Drive, então os caminhos precisam ser ajustados para rodar em outro ambiente. O dataset v15 e os splits estão em [`../data/`](../data/).

## Treino dos classificadores (dataset v15, 3.041 registros)

| Notebook | O que faz | Resultado (F1 macro, teste) |
|---|---|---|
| `mao_na_roda_finetuning_bertimbau.ipynb` | Fine-tuning do BERTimbau nos 3 splits (60/20/20, 70/15/15, 80/10/10) | 0,8675 no split 80/10/10 |
| `mao_na_roda_matriz_confusao.ipynb` | Recarrega o modelo e gera o relatório por classe e a matriz de confusão | 0,8675 |
| `mao_na_roda_debertinha_finetuning.ipynb` | Fine-tuning do DeBERTinha | 0,878 |
| `mao_na_roda_bertabaporu_finetuning.ipynb` | Fine-tuning do BERTabaporu | 0,8617 |
| `mao_na_roda_jabuticabert_finetuning.ipynb` | Fine-tuning do JabuticaBERT | 0,839 |

## Pipeline e ablação (fase piloto)

Estes notebooks rodam sobre o dataset da **fase piloto** (`dataset_mao_na_roda_v2.xlsx`, não incluído neste repositório), com 17 relatos de teste e o classificador daquela fase. Eles **não** geram os resultados Likert finais, que estão em [`../Likert/`](../Likert/) (30 relatos, classificador final).

| Notebook | O que faz |
|---|---|
| `03_pipeline_integrado.ipynb` | Pipeline em 4 camadas (regras, classificador, resposta canônica, RAG + LLM) |
| `05_ingest_chromadb.ipynb` | Ingestão dos manuais no ChromaDB |
| `06_experimento_ablacao.ipynb` | Ablação piloto com as configurações A, B, C e D |
| `07_avaliacao_qualitativa.ipynb` | Avaliação Likert piloto |

## Baseline (fase piloto)

| Notebook | Observação |
|---|---|
| `baseline_e_resultados_.ipynb` | Baseline no dataset piloto (F1 ≈ 0,607). Não é o baseline nos splits da v15 |
