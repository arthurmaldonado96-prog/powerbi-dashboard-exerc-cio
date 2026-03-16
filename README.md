# powerbi-dashboard-exerc-cio
Exercício - dasboard com dados de salários e faturamento com contratos
# Dashboard de Vendas - Power BI

##  Visão Geral

Este projeto apresenta um dashboard desenvolvido no Power BI como resolução de um exercício do curso da plataforma Hashtag Treinamentos.  
O objetivo é demonstrar habilidades em modelagem de dados, análise de métricas e visualização de dados aplicadas a um cenário corporativo.

O dashboard permite acompanhar indicadores importantes como salários, faturamento e quantidade de contratos fechados por área ao longo do tempo.

---

# Tecnologias Utilizada

- Power BI Desktop (modelagem e visualização)

---

# Estrutura do Modelo de Dados

O modelo foi desenvolvido seguindo o padrão **Star Schema**, muito utilizado em projetos de Business Intelligence.

### Tabela Fato
**BaseServicosPrestados**
- ID Funcionário
- ID Cliente
- Data da Contratação
- Idade

### Tabelas Dimensão

**CadastroCargos**
- Cargo
- Nível
- Área

**CadastroClientes**
- ID Cliente
- Cliente
- Valor Contrato Anual

**CadastroFuncionarios**
- ID Funcionário
- Estado Civil
- Nome Completo
- Salario Base
- Impostos
- Beneficios
- VT
- VR
- Cargo
- Salario Total

### Medidas
- Faturamento Total = SUMX(BaseServicosPrestados, BaseServicosPrestados[Idade] * RELATED(CadastroClientes[Valor Contrato Anual]))
- Qtd de Funcionários = COUNTROWS(CadastroFuncionarios)
- Qtd de Contratos = COUNTA(BaseServicosPrestados[ID Cliente])
- Média dos valores dos contratos = AVERAGE(CadastroClientes[Valor Contrato Anual])
- Soma de salários = SUM(CadastroFuncionarios[Salário Total])

---

# 📊 Indicadores (KPIs)

O dashboard apresenta os seguintes indicadores principais:

### Faturamento Total
Valor total faturado considerando a quantidade de contratos fechados e suas respectivas idades.

### Média dos Valores dos Contratos
Valor anual médio dos contratos fechados.

### Primeiro Cliente
Cliente com o contrato anual de maior valor.

### Qtd de Funcionários por Área
Gráfico de árvore comparando a quantidade relativa de funcionários por área.

### Soma de Salário Total por Área
Gráfico de funil mostrando a soma dos salários dos funcionários por área.

### Faturamento Total e Qtd de Contratos por Área
Gráfico de colunas e linha indicando o faturamento total e a quantidade de contratos fechados por área.

---

# Objetivo do exercício

- Demonstrar habilidades em **Business Intelligence**
- Criar visualizações orientadas à tomada de decisão
- Construir um **projeto de portfólio para análise de dados**


Arthur  

Analista de Dados | SQL | Python | Power BI  
MBA em Data Science e Analytics
