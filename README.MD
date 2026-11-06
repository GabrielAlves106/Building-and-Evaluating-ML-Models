# Comparação de Modelos de Regressão Linear para Previsão de Vendas

## Sobre o projeto

Este projeto tem como objetivo desenvolver e comparar dois modelos de **Regressão Linear** utilizando Python e bibliotecas de análise de dados e Machine Learning.

O experimento busca avaliar se a inclusão da variável **desconto**, além do investimento em publicidade, contribui para melhorar a previsão da quantidade de vendas de uma loja.

Para isso, são desenvolvidos dois modelos:

- **Modelo A:** utiliza exclusivamente o investimento em publicidade como variável de entrada.
- **Modelo B:** utiliza o investimento em publicidade e o percentual de desconto como variáveis de entrada.

Ambos são treinados com os mesmos dados e avaliados utilizando o Erro Absoluto Médio (MAE).

## Tecnologias utilizadas

- **Python:** linguagem utilizada no desenvolvimento.
- **Pandas:** manipulação e análise dos dados.
- **Matplotlib:** geração de gráficos e visualizações.
- **Scikit-learn:** implementação e avaliação dos modelos de regressão linear.

## Estrutura do projeto

```text
projeto/
│
├── exercicio.py
├── vendas_loja.csv
├── requirements.txt
│
└── resultados/
    ├── 01_dados_treino.png
    ├── 02_comparacao_validacao.png
    ├── comparacao_validacao.csv
    └── resultado_teste.csv
```

## Base de dados

O projeto utiliza o arquivo `vendas_loja.csv`, composto por 60 registros simulados para fins didáticos.

A base possui quatro colunas:

| Coluna | Descrição |
|---|---|
| dia | Identificador do período, de 1 a 60. |
| publicidade | Investimento em publicidade, em reais. |
| desconto | Percentual de desconto aplicado. |
| vendas | Quantidade de unidades vendidas. |

A variável `vendas` representa o objetivo da previsão, enquanto as demais variáveis são utilizadas conforme a configuração de cada modelo.

## Preparação do ambiente

### 1. Pré-requisitos

- Python instalado.
- Arquivos do projeto disponíveis localmente.
- Acesso à internet para instalação das dependências.

### 2. Instalação das dependências

Com o terminal aberto na pasta do projeto, execute:

```bash
python -m pip install -r requirements.txt
```

O arquivo `requirements.txt` contém as seguintes bibliotecas:

- pandas
- matplotlib
- scikit-learn

### 3. Execução

Para executar o programa:

```bash
python exercicio.py
```

Também é possível executar sem abrir janelas de gráficos, salvando diretamente os resultados:

```bash
python exercicio.py --sem-janelas
```

Os gráficos e arquivos CSV serão armazenados automaticamente na pasta `resultados/`.

## Desenvolvimento do experimento

O experimento foi dividido em nove etapas:

1. **Carregamento dos dados:** leitura do CSV e verificação da integridade da base.
2. **Separação dos períodos:** divisão dos 60 registros em treinamento (40), validação (10) e teste (10).
3. **Treinamento do modelo A:** utilização da variável publicidade.
4. **Treinamento do modelo B:** utilização das variáveis publicidade e desconto.
5. **Geração das previsões:** aplicação dos modelos sobre os dados de validação.
6. **Cálculo dos erros:** comparação entre previsões e valores reais utilizando MAE.
7. **Comparação dos modelos:** escolha do modelo com menor erro na validação.
8. **Avaliação final:** aplicação do modelo escolhido sobre os dados de teste.
9. **Nova previsão:** estimativa de vendas para um cenário hipotético.

## Visualização dos resultados

### 1. Dados de treinamento

Gráfico de dispersão representando a relação entre o investimento em publicidade e a quantidade de vendas nos 40 registros utilizados para treinamento.

![Dados de treinamento](resultados/01_dados_treino.png)

### 2. Comparação dos modelos na validação

Comparação entre as vendas reais e as previsões realizadas pelos modelos A e B nos 10 registros de validação.

![Comparação dos modelos](resultados/02_comparacao_validacao.png)

## Resultados obtidos

Após o treinamento e a avaliação dos modelos, foram obtidos os seguintes resultados:

| Métrica | Modelo A | Modelo B |
|---|---:|---:|
| MAE na validação | 14,40 | 5,22 |
| Modelo selecionado | Não | Sim |

O Modelo B apresentou um desempenho superior na validação, com um erro absoluto médio de aproximadamente **5,22 unidades**, contra 14,40 unidades do Modelo A.

Com base nesse resultado, o Modelo B foi selecionado para a avaliação final.

### Avaliação no conjunto de teste

O modelo escolhido apresentou um MAE de aproximadamente **6,23 unidades** no conjunto de teste, composto pelos 10 registros finais.

### Nova previsão

Após a avaliação, foi realizada uma previsão para o seguinte cenário hipotético:

| Variável | Valor |
|---|---:|
| Investimento em publicidade | R$ 300,00 |
| Desconto | 10% |
| Vendas estimadas | 129,71 unidades |

## Arquivos gerados

Ao executar o programa, são gerados automaticamente:

| Arquivo | Descrição |
|---|---|
| `01_dados_treino.png` | Visualização dos dados utilizados no treinamento. |
| `02_comparacao_validacao.png` | Comparação entre vendas reais e previsões. |
| `comparacao_validacao.csv` | Tabela de previsões e erros dos modelos na validação. |
| `resultado_teste.csv` | Resultados do modelo escolhido no conjunto de teste. |

## Considerações e limitações

O experimento demonstra como a inclusão de novas variáveis pode contribuir para melhorar o desempenho de um modelo de Machine Learning.

Entretanto, os resultados devem ser interpretados considerando algumas limitações:

- A base de dados é simulada e possui apenas 60 registros.
- A divisão entre treinamento, validação e teste é fixa.
- A análise utiliza exclusivamente modelos de regressão linear.
- Os resultados não garantem o mesmo desempenho em cenários comerciais reais.
- A melhoria observada não comprova, por si só, uma relação de causalidade entre descontos e aumento das vendas.

O objetivo principal é compreender o processo de construção, treinamento, comparação e avaliação de modelos preditivos.

## Autor

**Gabriel Rodrigues Alves**

- GitHub: [@GabrielAlves106](https://github.com/GabrielAlves106)
- LinkedIn: [Gabriel Alves](https://www.linkedin.com/in/gabriel-alves111)