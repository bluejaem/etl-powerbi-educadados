# Desafio Técnico de ETL com Power Query — Power BI

Repositório com a resolução do desafio técnico de modelagem e transformação de dados (ETL) utilizando o Power Query no Power BI, realizado durante a formação na educadados.

---

## Objetivo do Desafio

Consolidar bases dispersas e estruturar duas tabelas analíticas prontas para modelagem e consumo:
1. **Tabela Fato Vendas** (padronizada e enriquecida com dados cadastrais)
2. **Tabela Metas** (desdinamizada em formato colunar analítico)

Os requisitos originais do desafio podem ser consultados no arquivo [`Qual_Era_O_Desafio.pdf`](Qual_Era_O_Desafio.pdf).

---

## Etapas de Transformação (ETL)

### 1. Consolidação da Tabela Vendas
* **Padronização de Esquema:** Alinhamento dos nomes das colunas e estruturas entre as bases `Parte1` e `Parte2`.
* **Tipagem e Tratamento de Datas:** Correção de formatos misturados e validação de consistência temporal.
* **União de Consultas (Append):** Consolidação dos dois períodos/lotes de vendas em uma única tabela contínua.
* **Limpeza da Base de Clientes:**
  * Remoção de espaços sobressalentes (`Text.Trim`).
  * Padronização de maiúsculas/minúsculas.
  * Correção de erros ortográficos em regiões.
  * Divisão da coluna `cidade_estado` com base em delimitador.
* **Cruzamento de Dados (Merge):** Junção da tabela de Vendas com Clientes via chave `id_cliente` para enriquecer a base com `nome`, `cidade`, `estado` e `região`.
* **Regra de Negócio (Coluna Condicional):** Segmentação de ticket em categorias (*Alto*, *Médio* e *Baixo*) a partir da métrica `valor_total`.

### 2. Modelagem da Tabela de Metas
* **Transformação de Formato:** Aplicação de **Unpivot** (desdinamização de colunas) para converter a tabela de formato largo (*pivotado* por meses) em uma estrutura tabular normalizada.
* **Padronização:** Renomeação das colunas finais para `Mes` e `Meta`, permitindo relacionamentos e filtros analíticos eficazes.

---

## Arquivos do Projeto

* `Desafio_Tecnico_PQ_Modulo2.pbix`: Arquivo completo com todas as etapas aplicadas no editor do Power Query e carregadas no modelo.
* `Qual_Era_O_Desafio.pdf`: Documento com as instruções do desafio.

---

## Habilidades Aplicadas

`Power Query` • `Power BI` • `Linguagem M` • `ETL` • `Tratamento de Dados` • `Modelagem Dimensional`