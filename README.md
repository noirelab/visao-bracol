# BRACOL: ML clássico versus YOLO

Projeto final de Visão Computacional. Classificação de estresses bióticos em folhas de café arábica (saudável, bicho-mineiro, ferrugem, phoma, cercospora) com duas soluções sobre o mesmo dataset:

| Solução | F1 macro (teste) | Acurácia |
|---|---|---|
| ML clássico: SVM RBF com atributos de cor, LBP e Haralick | 0,832 | 0,836 |
| Deep Learning: YOLO26-s em modo classificação | 0,954 | 0,955 |

Integrantes: Kaíque Medeiros Lima e Erick Bonruque.

## Conteúdo

- `bracol_ml_vs_dl.ipynb`: notebook completo (dataset, ML clássico, YOLO, comparação), já executado.
- `results/`: métricas (`metricas.json`), figuras e o modelo clássico (`ml_classico.joblib`).
- `runs/yolo26s-cls/`: treino do YOLO, com `weights/best.pt`.
- `relatorio/`: proposta em PDF e o HTML que a gera.

## Como reproduzir

Requer [uv](https://docs.astral.sh/uv/) e GPU NVIDIA (PyTorch CUDA 12.8).

```bash
uv sync
mkdir -p data
uvx gdown "https://drive.google.com/uc?id=15YHebAGrx1Vhv8-naave-R5o3Uo70jsm" -O data/bracol.zip
unzip -q data/bracol.zip -d data/
uv run jupyter nbconvert --to notebook --execute --inplace bracol_ml_vs_dl.ipynb
```

O zip publicado no Mendeley Data está truncado (sem o subconjunto de sintomas). O link acima é o indicado pelos autores em [esgario/lara2018](https://github.com/esgario/lara2018).

## Dataset

BRACOL, Krohling, Esgario e Ventura (2019), Mendeley Data, doi:[10.17632/yy2k5y8mxg.1](https://doi.org/10.17632/yy2k5y8mxg.1), licença CC BY 4.0. O dataset não está neste repositório.
