# 📊 Projeto de Pipeline de Vendas – Arquitetura Medallion
<img width="1024" height="768" alt="Texto do seu parágrafo" src="https://github.com/user-attachments/assets/bf9c4438-32b5-4f3c-8b1b-60e12f421d4f" />

## Visão Geral
Este projeto implementa um pipeline de dados para análise de vendas, utilizando recursos da **Azure**, banco de dados **Postgres** e processamento em **Databricks**.  
A arquitetura segue o padrão **Medallion** (Bronze, Silver, Gold), garantindo organização, qualidade e escalabilidade dos dados.

---

## Arquitetura Medallion

| Camada  | Objetivo | Exemplos de Transformações |
|---------|----------|-----------------------------|
| **Bronze** | Ingestão de dados brutos, sem tratamento. | Dados extraídos diretamente do Postgres (transações de vendas, clientes, produtos). |
| **Silver** | Padronização e limpeza dos dados. | Normalização de colunas, remoção de duplicatas, tratamento de nulos, enriquecimento com metadados. |
| **Gold** | Dados prontos para consumo analítico e relatórios. | Agregações de vendas por período, dashboards de performance, métricas de clientes e produtos. |

---

## ⚙️ Tecnologias Utilizadas
- **Azure Databricks** → Processamento distribuído e notebooks para ETL/ELT.  
- **Azure Unit catálogo → Armazenamento das camadas Bronze, Silver e Gold. 
- **Postgres** → Fonte de dados transacionais (sistema de vendas).  
- **Power BI ** → Consumo dos dados da camada Gold para relatórios e dashboards.
- ** Jobs **  → Orquestração de camadas

---

##  Fluxo do Pipeline
1. **Ingestão (Bronze):**
   - Conexão com o banco **Postgres**.
   - Extração de tabelas de vendas, clientes e produtos.
   - Armazenamento em formato **Parquet/Delta** no ADLS.

2. **Transformação (Silver):**
   - Limpeza e padronização dos dados.
   - Criação de tabelas intermediárias com chaves consistentes.
   - Enriquecimento com dados auxiliares (ex.: categorias de produtos).

3. **Curadoria (Gold):**
   - Agregações e métricas de negócio.
   - Estruturação de tabelas otimizadas para BI.
   - Disponibilização para relatórios e análises avançadas.

---

## 🚀 Benefícios da Arquitetura
- Separação clara entre dados brutos, tratados e analíticos.  
- Escalabilidade e governança no pipeline.  
- Facilidade de integração com ferramentas de BI.  
- Redução de retrabalho e inconsistências nos relatórios.  

---

## Imagens do projeto

## Criação do banco de dados no Postgres
![WhatsApp Image 2026-02-13 at 21 14 03](https://github.com/user-attachments/assets/58f93fac-1ed5-4a13-8e39-0e3f59201953)

## Criação dos catálogos e tabelas
![WhatsApp Image 2026-02-13 at 20 31 17](https://github.com/user-attachments/assets/8e49c8a0-5fbb-4a0a-a754-e87ada0381c6)

## Tabela de Clientes em diferentes catálogos
![WhatsApp Image 2026-02-13 at 20 33 04](https://github.com/user-attachments/assets/0bee7cf7-f26a-4f4c-8256-f5d594c2b9a4)
![WhatsApp Image 2026-02-13 at 20 33 29](https://github.com/user-attachments/assets/a9b4cee4-3941-46a1-a9bc-023eeca84584)

## Orquestração com Databricks
![WhatsApp Image 2026-02-13 at 20 24 05](https://github.com/user-attachments/assets/d656dff3-bdb3-4f2e-8ccd-2b51ef14b99f)
![WhatsApp Image 2026-02-13 at 20 24 29](https://github.com/user-attachments/assets/07d32b3c-3881-4933-8e20-4b1dab98734d)

## Modelo de relacionamento entre tabelas no Power BI
![WhatsApp Image 2026-02-13 at 21 13 09](https://github.com/user-attachments/assets/565da24c-4e50-4360-b065-2d73f7322503)

## Dashboard simples para acompanhamento de vendas
![WhatsApp Image 2026-02-13 at 20 24 58](https://github.com/user-attachments/assets/bece9cb0-8c8a-4d5b-a0a4-b4c899bddb1a)

## Recursos Azure utilizados
<img width="1899" height="522" alt="image" src="https://github.com/user-attachments/assets/626081f8-ec1d-4262-9705-94e78c9b6e50" />


