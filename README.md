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
# Pipeline de Dados

O desenvolvimento do projeto foi dividido em etapas sequenciais, seguindo uma arquitetura em camadas para garantir organização, rastreabilidade e reutilização dos dados.

## 1. Inventário e validação das bases

A primeira etapa consistiu no levantamento e validação dos arquivos disponibilizados pelo Portal da Transparência.

Foram identificadas as competências disponíveis, verificada a consistência dos layouts e conferida a integridade das bases antes do início do processamento.

Essa etapa permitiu garantir que todas as competências utilizassem a mesma estrutura de dados e que eventuais inconsistências fossem identificadas antes das transformações.

---

## 2. Camada Bronze

Os arquivos originais em formato CSV foram convertidos para o formato Parquet, preservando integralmente as informações disponibilizadas pelo Portal da Transparência.

Essa camada representa uma cópia estruturada dos dados de origem, servindo como base para todas as etapas posteriores de tratamento.

Principais atividades:

* Conversão dos arquivos CSV para Parquet;
* Padronização da estrutura das bases;
* Preservação dos dados originais sem alterações de conteúdo.

---

## 3. Camada Silver

Na camada Silver foram realizadas as transformações necessárias para tornar os dados consistentes e adequados para análise.

Entre as principais atividades destacam-se:

* Padronização dos tipos de dados;
* Conversão de campos monetários;
* Tratamento de valores ausentes;
* Padronização de datas;
* Inclusão da competência de cada registro;
* Preparação das informações para modelagem analítica.

Essa etapa concentrou o processo de limpeza e organização dos dados.

---

## 4. Camada Gold

Com os dados padronizados, foi construída a camada analítica do projeto.

Nessa etapa foram criadas as tabelas dimensionais e a tabela fato utilizadas no modelo de Business Intelligence.

As principais estruturas desenvolvidas foram:

* Dimensão Competência;
* Dimensão Órgão;
* Dimensão Cargo;
* Dimensão Grupo;
* Tabela Fato de Remuneração.

A separação entre fatos e dimensões permitiu a construção de um modelo otimizado para consultas analíticas.

---

# Modelagem Dimensional

Os dados foram organizados utilizando o modelo Star Schema, amplamente empregado em soluções de Business Intelligence.

Essa abordagem simplifica os relacionamentos entre as tabelas, melhora o desempenho das consultas e facilita a construção de indicadores e dashboards no Power BI.

A modelagem permite realizar análises temporais, comparações entre órgãos, cargos e grupos, além de suportar diferentes níveis de agregação das informações.

---

# Dashboard

Após a construção da camada analítica, os dados foram importados para o Power BI, onde foram desenvolvidos indicadores e visualizações voltados à análise da folha de pagamento do Estado de São Paulo.

Entre as análises implementadas destacam-se:

* Evolução temporal da remuneração;
* Comparação entre órgãos;
* Indicadores de remuneração média;
* Distribuição dos gastos com pessoal;
* Rankings e filtros dinâmicos para exploração das informações.

O dashboard foi desenvolvido com foco na clareza das informações e na navegação intuitiva, permitindo diferentes perspectivas de análise sobre os dados públicos.

Status do Projeto

Este projeto encontra-se em desenvolvimento contínuo e está sendo publicado gradualmente.

Nas próximas atualizações serão disponibilizados:

Código-fonte completo, organizado por etapas do pipeline de dados;
Documentação técnica detalhando as decisões de implementação;
Explicações sobre cada script e sua função no processo de tratamento dos dados;
Capturas de tela e atualizações do dashboard desenvolvido em Power BI;
Melhorias na documentação e exemplos de utilização.

Devido às limitações de armazenamento do GitHub, não será possível disponibilizar integralmente todas as bases de dados utilizadas no projeto. Como alternativa, serão disponibilizados arquivos de exemplo, juntamente com a documentação necessária para reprodução do pipeline utilizando os dados públicos obtidos no Portal da Transparência do Estado de São Paulo.

O objetivo é que o repositório evolua gradualmente, documentando não apenas o resultado final, mas também o processo de desenvolvimento e as decisões técnicas adotadas durante a construção do projeto.

