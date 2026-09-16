# 📁 05-python-poo-
# Sistema de Conversão de Moedas e Análise Gráfica

Este projeto foi desenvolvido como parte das aulas da disciplina de **Sistemas de Informação**, utilizando a linguagem **Python** com conceitos de desenvolvimento modular, Programação Orientada a Objetos (POO) e integração com APIs web.

O objetivo do sistema é consumir dados financeiros em tempo real para realizar a conversão de moedas estrangeiras e gerar análises visuais por meio de gráficos.

---

## 📌 Estrutura do Projeto

O sistema é estruturado de forma modular e composto pelos seguintes arquivos originais:

### 1. `01-conversão.py`
Implementa a interface de linha de comando (CLI) para que o usuário interaja com o menu de conversão. Ele importa o módulo de cálculo e permite escolher moedas pré-definidas (Dólar, Euro e Libra) ou digitar moedas personalizadas de origem e destino via terminal.

### 2. `02-moedas.py`
Este módulo é responsável por fazer a integração com a **ExchangeRate-API**. Ele realiza as requisições HTTP para buscar as taxas de câmbio atualizadas em formato JSON e implementa a lógica matemática necessária para converter os valores de forma dinâmica.
*   **Principais funções:** `get_cotacao()` e `converter_cotacao()`.

### 3. `03-graficos.py`
Módulo focado na visualização estatística de dados utilizando a biblioteca `matplotlib`. Ele recebe as listas de moedas e seus respectivos valores calculados para gerar e renderizar as telas visuais de análise.
*   **Principais funções:** `grafico_barra()`, `grafico_pizza()` e `grafico_dispersao()`.

### 4. `04- index_grafico.py`
Gerencia a exibição visual das moedas em relação ao Real Brasileiro (BRL). Ele consome o módulo de cotações, calcula os valores inversos para o cenário econômico do momento e monta os gráficos de forma interativa baseando-se na escolha do menu do usuário.

---

## 🌐 Integração com a API

O projeto utiliza a **ExchangeRate-API**, uma API que fornece taxas de câmbio de moedas atualizadas em tempo real.

*   **URL Base utilizada:** `https://api.exchangerate-api.com/v4/latest/`
*   **Funcionamento:** O sistema envia uma requisição informando a moeda base desejada. A API retorna uma estrutura de dados estruturada em JSON contendo o valor dessa moeda mapeado contra mais de 160 moedas globais. O código faz o tratamento desse dicionário para calcular o valor inverso exato e exibir o resultado final na tela.

---

## ⚙️ Pré-requisitos e Instalação

Para executar o projeto, você precisa ter o Python instalado e as seguintes bibliotecas de terceiros:

```bash
# Instalar a biblioteca de requisições HTTP
pip install requests

# Instalar a biblioteca de geração de gráficos
pip install matplotlib
```

## 🚀 Como Executar

Para realizar conversões de moedas via terminal:
```bash
python 01-conversão.py
```

Para visualizar a análise gráfica das moedas frente ao Real:
```bash
python "04- index_grafico.py"
```
*(Nota: Lembre-se de utilizar aspas ao executar o arquivo 04 no terminal devido ao caractere de espaço contido no nome do arquivo).*
