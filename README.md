# analise_folha_pagamentos_sp
# Análise Temporal da Folha de Pagamento do Estado de São Paulo

# Sobre o projeto

Este é um projeto independente de Análise de Dados desenvolvido com o objetivo de aplicar conceitos de Engenharia e Análise de Dados a informações públicas da folha de pagamento do Poder Executivo do Estado de São Paulo.

O projeto utiliza dados disponibilizados no Portal da Transparência do Estado de São Paulo e não possui qualquer vínculo institucional com o Governo do Estado. Seu propósito é exclusivamente o desenvolvimento de competências técnicas e a construção de um portfólio em Análise de Dados.

Ao longo do desenvolvimento foram aplicadas práticas de organização, tratamento, modelagem e visualização de dados, buscando reproduzir um fluxo de trabalho semelhante ao utilizado em projetos reais de Business Intelligence.

---

# Objetivo

Os dados da folha de pagamento são disponibilizados mensalmente em arquivos independentes, o que dificulta análises históricas e comparações entre diferentes períodos.

O objetivo deste projeto é consolidar essas bases em um modelo analítico único que permita responder, entre outras, perguntas como:

* Como evoluiu a remuneração média dos órgãos ao longo do tempo?
* Quais órgãos apresentam as maiores despesas com pessoal?
* Como variam os gastos entre diferentes competências?
* Quais tendências podem ser identificadas na evolução da folha de pagamento?

Para isso, foi desenvolvido um pipeline de tratamento de dados utilizando Python (Pandas), seguido da modelagem dimensional das informações para análise no Power BI.

---

# Fonte dos dados

Todos os dados utilizados são públicos e foram obtidos no Portal da Transparência do Estado de São Paulo.

As bases são disponibilizadas mensalmente em formato CSV e contêm informações referentes à folha de pagamento dos servidores do Poder Executivo Estadual.

Este projeto utiliza exclusivamente dados públicos e possui finalidade educacional e de desenvolvimento profissional.

---

# Visão geral da arquitetura

O projeto foi estruturado em uma arquitetura de camadas inspirada em Data Warehouses modernos.

```text
Portal da Transparência
            │
            ▼
      Arquivos CSV
            │
            ▼
     Camada Bronze
 (Conversão para Parquet)
            │
            ▼
      Camada Silver
(Limpeza e Padronização)
            │
            ▼
       Camada Gold
(Modelagem Analítica)
            │
            ▼
         Power BI
```

