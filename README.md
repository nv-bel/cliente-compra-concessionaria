# Análise do perfil de Compras x Clientes - Concessionaria de Automóveis

Projeto de integracao e analise de dados utilizando SQLite e Pandas, com foco no perfil de compra de clientes de uma concessionaria de automóveis.

## Sobre

Este projeto trabalha com um banco de dados SQLite (`Car_Database.db`) projetado para lidar com as operacoes diarias de uma empresa automobilistica. O banco fornece funcionalidades para visualizar transacoes de concessionarios, rastrear inventario de carros e manter modelos e opções disponíveis.

A partir desse banco, duas tabelas são combinadas via INNER JOIN utilizando IDs em comum, e os dados resultantes são exportados para CSV. Em seguida, o CSV é carregado com Pandas para limpeza, pré-processamento e análise estatística, com visualizacões geradas via Matplotlib e Seaborn.

## Estrutura do Projeto

```
.
├── Car_Database.db                           # Banco de dados SQLite original
├── clientes_concessionaria.csv               # CSV gerado a partir da juncão das tabelas
├── descricao_projeto.pdf                     # Documento de descrição do projeto
├── integracao-analise-sqlite-pandas_.ipynb   # Notebook principal com toda a analise
└── README.md
```

## Tecnologias e Bibliotecas

- **Python 3**
- **SQLite3** - conexão e consultas ao banco de dados
- **Pandas** - manipulacao e analise de dados
- **Matplotlib** - visualizacao de dados
- **Seaborn** - visualizacoes estatisticas avancadas
- **Scikit-learn** - encoding de variaveis categoricas (LabelEncoder)
- **SciPy** - analise de correlacao

## Etapas do Projeto

### 1. Integracao de Dados (SQL + CSV)

- Conexao ao banco SQLite (`Car_Database.db`)
- Identificacao das tabelas disponiveis: `Customers`, `Customer_Ownership`, `Car_Vins`, `Models`, `Brands`
- Consulta SQL com INNER JOIN entre multiplas tabelas usando IDs em comum
- Exportacao dos dados combinados para o arquivo `clientes_concessionaria.csv`

### 2. Enriquecimento dos Dados

Como o banco original retornou poucos registros (apenas 5 clientes com compras), foram inseridos dados sintéticos adicionais no DataFrame para viabilizar analises mais significativas. O banco de dados original permaneceu intacto.

### 3. Analise Exploratoria e Estatistica

As analises realizadas incluem:

- **Media de compra por genero**: homens gastam, em media, mais do que mulheres
- **Media de renda familiar por genero**: mulheres possuem, em media, renda familiar maior
- **Renda vs. Preco de compra**: a maioria dos clientes comprou carros de ate $50.000; pessoas com salarios mais altos tenderam a comprar carros mais baratos
- **Renda vs. Preco de compra por genero**: pequena quantidade de homens com menor renda gastou mais, mas sem volume significativo para conclusoes concretas
- **Matriz de correlacao**: analise de correlacao entre renda, preco de compra e genero usando heatmap
- **Modelos mais vendidos**: A4 (Audi), Altima (Nissan) e Expedition (Ford) lideraram com 3 unidades cada
- **Marcas mais vendidas**: Ford liderou as vendas, seguida por Audi, Volkswagen e Hyundai
- **Preferencia por genero**: modelos mais comprados por homens vs. mulheres

### 4. Visualizacoes

- Graficos de barras (media de compra e renda por genero, modelos e marcas mais vendidos)
- Graficos de dispersao (renda vs. preco de compra, geral e segmentado por genero)
- Pairplot (Seaborn) para visao multivariada
- Heatmap da matriz de correlacao

## Como Executar

1. Clone o repositorio
2. Abra o notebook `integracao-analise-sqlite-pandas_.ipynb` no [Google Colab](https://colab.research.google.com/) ou Jupyter Notebook
3. Faca upload dos arquivos `Car_Database.db` e `clientes_concessionaria.csv` para o ambiente
4. Execute as celulas sequencialmente


## Conclusao

O banco de dados original continha poucos registros para a abordagem escolhida, o que limitou as analises. Mesmo com a insercao de dados sinteticos, o conjunto permaneceu pequeno. Ainda assim, foi possivel extrair insights sobre o perfil de compra por genero, relacao entre renda e gasto, e preferencias por modelos e marcas.

---

> Projeto desenvolvido em 2024 no contexto da disciplina de Linguagem de Programacao III (LP3) - Universidade do Estado da Bahia.
