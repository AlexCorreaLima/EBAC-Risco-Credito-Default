# EBAC-Risco-Credito-Default
Mod5Ex_aulas_04a05

# Classificação de Risco de Crédito: Montagem da Variável Resposta (EBAC)

Este repositório contém o exercício prático do Módulo 05 do curso da EBAC, focado na preparação de dados e na construção da variável resposta (`default`) para um projeto de classificação de risco de crédito.

## 📚 Sobre o Projeto

O objetivo principal deste exercício é aprofundar a compreensão sobre a manipulação de dados para a criação de uma variável alvo (ou variável resposta) em um contexto de análise de risco de crédito. A variável `default` é crucial para treinar modelos de Machine Learning que visam prever a inadimplência de clientes.

### Definição de `Default`

Para os propósitos deste estudo, um cliente em `default` é definido da seguinte forma:

* **Maus Pagadores (Default = True):** Clientes que apresentaram atraso de 60 dias ou mais em seus pagamentos (ou equivalente a 'C' / 'X' nos dados fornecidos) em qualquer um dos 24 meses seguintes à aquisição do cartão de crédito.
* **Bons Pagadores (Default = False):** Todos os demais clientes que adquiriram um cartão de crédito e não se encaixaram na definição de mau pagador.
* **Excluídos:** Clientes que não chegaram a adquirir um cartão de crédito (seja por recusa na proposta ou desistência) não foram considerados na análise de risco, pois não há histórico de pagamentos para eles.

## 📊 Conjunto de Dados

Dois arquivos CSV são utilizados neste projeto:

1.  `application_record.csv`: Contém informações sobre as propostas de crédito dos clientes.
2.  `pagamentos_largo.csv`: Contém o histórico de pagamentos dos clientes que adquiriram o cartão, com colunas representando o status de pagamento em cada mês (`mes_0` a `mes_24`). O status de pagamento pode incluir códigos como '0' (sem dívida), '1' (1-29 dias de atraso), 'C' (cobradores) e 'X' (mais de 60 dias de atraso).

## 🚀 Tarefas Realizadas

O exercício foi dividido em 5 tarefas principais para construir a variável `default`:

1.  **Marcar `default` no mês:** Criar uma coluna indicadora de `default` (atraso de 60+ dias, 'C' ou 'X') para cada mês (`mes_0` a `mes_24`) na base de pagamentos.
2.  **'Bons' e 'Maus' ao longo de todos os 24 meses:** Para cada cliente, identificar se houve pelo menos um episódio de `default` (60+ dias de atraso) em qualquer um dos 24 meses, consolidando essa informação em uma única coluna `default`.
3.  **Marcando proponentes expostos ao risco de crédito:** Filtrar a base de propostas (`application_record.csv`) para incluir apenas os clientes que efetivamente adquiriram um cartão de crédito e, portanto, possuem histórico de pagamentos na base `pagamentos_largo.csv`.
4.  **Consolidando as informações:** Unir as informações da base de propostas filtrada com a variável `default` recém-construída, utilizando o `ID` do cliente como chave.
5.  **Verificando:** Realizar uma contagem e calcular as proporções dos clientes classificados como 'bons' e 'maus' pagadores na base final.

## 🛠️ Tecnologias Utilizadas

* `Python`
* `Pandas` (para manipulação e análise de dados)
* `Jupyter Notebook` (ambiente de desenvolvimento - *opcional, mas comum para este tipo de exercício*)





