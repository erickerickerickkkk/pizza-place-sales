# Pizza Place Sales Analysis - Business Intelligence

![Status do Projeto](https://img.shields.io/badge/Status-Concluído-green)
![Power BI](https://img.shields.io/badge/Power%20BI-Desktop-yellow)
![DAX](https://img.shields.io/badge/DAX-Avançado-orange)

## Visão Geral do Projeto

Este projeto consiste em uma análise estratégica ponta a ponta das operações de uma pizzaria, transformando dados transacionais em indicadores de performance (KPIs) claros para suporte à tomada de decisão. O objetivo principal foi responder a perguntas fundamentais sobre faturamento, comportamento de consumo e eficiência operacional.

O maior desafio técnico residiu na gestão e validação do modelo de dados para garantir que métricas como faturamento e ranking de sabores fossem calculadas corretamente, considerando diferentes tamanhos e categorias de produtos.

### Fonte dos Dados
Os dados foram extraídos do dataset público **[Pizza Place Sales](https://mavenanalytics.io/data-playground/pizza-place-sales)**, disponibilizado pela Maven Analytics. O conjunto de dados contém registros detalhados de vendas de um ano inteiro, incluindo datas, horários, tipos de pizza, tamanhos e preços.

### Objetivos
* Validar e gerir um modelo de dados relacional complexo para análise de vendas.
* Desenvolver medidas DAX para extração de faturamento bruto e volume de pedidos.
* Identificar padrões de sazonalidade e janelas de horários de pico.
* Criar um Dashboard interativo e padronizado em inglês para visualização executiva.

---

## Tecnologias e Ferramentas Utilizadas

* **Power BI Desktop:** Utilizado para a ingestão, modelagem, cálculos e design dos visuais.
* **DAX (Data Analysis Expressions):** Elaboração de medidas complexas como faturamento total utilizando iteradores (`SUMX`) e funções de relacionamento (`RELATED`).
* **Power Query (ETL):** Padronização de strings (limpeza de nomes de produtos), tratamento de datas para ordenação cronológica e configuração de localidade para o idioma inglês.

---

## Etapas do Projeto

### 1. Gestão e Validação do Modelo Relacional
Embora os dados já tivessem uma estrutura pré-definida, foi realizada a implementação e validação de um **Snowflake Schema** dentro do Power BI.
* **Integridade de Dados:** Verificação das chaves primárias e estrangeiras entre a tabela de fatos (`order_details`) e as dimensões (`pizzas` e `pizza_types`).
* **Cardinalidade:** Garantia de relações "Um para Muitos" (1:*) para evitar a duplicação de valores em cálculos de soma e contagem.

| Esquema de Dados (Snowflake Schema) |
| :---: |
| <img src="Images/01-modelo.png" width="800"> |


### 2. Desenvolvimento de Inteligência de Negócio (DAX)
A lógica de negócio foi aplicada para extrair insights além do óbvio:
* **Faturamento Dinâmico:** Cruzamento de tabelas de vendas e preços para gerar o `Total Revenue`.
* **Métricas de Volume:** Cálculo da média de pizzas por pedido (2,32), identificando o perfil de consumo compartilhado do estabelecimento.
* **Ordenação Cronológica:** Criação de colunas de suporte via DAX para garantir que os meses em inglês fossem exibidos na ordem correta do calendário, superando limitações de ordenação alfabética.

### 3. Visualização e Design de Dashboard
Construção de uma interface "clean", focada na redução de ruído visual (remoção de termos repetitivos) e na clareza dos eixos.

| Dashboard Final |
| :---: |
| <img src="Images/02-dashboards.png" width="900"> |

---

## 📈 Insights e Descobertas de Negócio

A análise dos dados permitiu identificar padrões críticos para a operação:

1. **Janelas de Pico Bimodal:**
   * O fluxo de clientes apresenta dois picos claros: ao **meio-dia (almoço)** e às **18h (jantar)**. 
   * **Insight:** Há uma oportunidade de otimização da equipe de cozinha e entregadores para cobrir essas duas janelas específicas, minimizando custos em horários de baixo movimento.

2. **Dominância da Sexta-feira:**
   * A sexta-feira é o dia de maior movimento (média de **71 clientes**), enquanto o domingo apresenta o menor volume (50 clientes). 
   * **Ação Recomendada:** Campanhas de marketing ou promoções específicas para os domingos podem ajudar a equilibrar a ocupação da pizzaria ao longo da semana.

3. **Mix de Produtos e Favoritismo:**
   * A pizza "The Classic Deluxe" é o carro-chefe, com mais de **2.500 unidades vendidas**. 
   * **Conclusão:** O cardápio possui sabores "âncora" muito fortes. A média de **2,32 pizzas por pedido** confirma que a maioria das vendas é voltada para grupos ou famílias.

4. **Estabilidade de Receita:**
   * O faturamento mensal mantém-se estável entre **$64k e $73k**, demonstrando uma base de clientes fiel e uma operação previsível.

---

## 👤 Autor

**Erick Andrade**
* Estudante de Análise e Desenvolvimento de Sistemas (ADS)
* Foco em Análise de Dados e Business Intelligence

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/erickmichelandrade/)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:erick.machado0600@gmail.com)