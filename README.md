# 🚀 Aurora-Siger

Atividade integradora da FIAP com foco na aplicação prática dos conceitos aprendidos ao longo do mês.

## 📌 Resumo

O **Aurora-Siger** é um projeto desenvolvido em Python utilizando **Jupyter Notebook** para analisar dados de telemetria e decidir se uma espaçonave deve decolar ou não.

Os dados foram gerados com o auxílio de uma Inteligência Artificial (ChatGPT), simulando diferentes cenários de lançamento.

A partir dessas informações, o notebook realiza a análise e determina se a decolagem é segura ou deve ser abortada.


## 📁 Estrutura do Projeto
```
Aurora-Siger/
├── datasets/           # CSV datasets
├── images/             # images
├── notebooks/          # Jupyter notebooks
│   ├──  aurora_telemetria.ipynb  # Main Notebook
├──  aurora_telemetria.pdf  # PDF report
├── requirements.txt    # Dependencies
└── README.md           # Project documentation
```

## ⚙️ Como executar o projeto
1. Clonar o repositorio

```
git clone https://github.com/ronald-amorim-garcia/Aurora-Siger.git
cd Aurora-Siger
```

2. Criar um ambiente virtual python

```
python3 -m venv venv
source venv/bin/activate
```

3. Instalar as dependencias

```
pip install -r requirements.txt
```

4. Rodar o Jupyter
```
jupyter notebook
```