
# 🏗️ Modern Data Stack: Arquitetura Medalhão & Reconciliação Financeira

![PySpark](https://img.shields.io/badge/Apache_Spark-PySpark-E35A16?style=for-the-badge&logo=apachespark&logoColor=white)
![Delta Lake](https://img.shields.io/badge/Delta_Lake-Medallion-00AAD2?style=for-the-badge)
![Databricks](https://img.shields.io/badge/Databricks-Unity_Catalog-FF3621?style=for-the-badge&logo=databricks&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-Semantic_Layer-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)

## 📌 Visão Executiva

Este projeto simula um cenário real de **Analytics Engineering** no mercado financeiro: a migração de dados operacionais complexos (operações quantitativas de ETFs, liquidez em criptoativos e liquidações via Pix) para uma arquitetura moderna baseada em **Databricks e Delta Lake**, garantindo a paridade absoluta dos dados antes de virar a chave dos relatórios gerenciais no Power BI.

O foco não é apenas mover dados, mas garantir a **confiança da camada de consumo**.

## 🎯 Desafios de Negócio Resolvidos

1. **Ingestão Protegida:** Implementação de *Data Contracts* para evitar que mudanças sistêmicas na API de origem quebrem o pipeline.
2. **Qualidade de Dados (DQ Gates):** Roteamento dinâmico de registros anômalos para uma *Dead Letter Queue* (Quarentena), preservando o histórico para auditoria sem poluir as tabelas de consumo.
3. **Métricas Certificadas:** Modelagem dimensional (*Kimball*) centralizando as regras de negócio em um *Data Mart* otimizado.
4. **Reconciliação Automatizada:** Um motor de comparação matemática em escala para provar que a nova arquitetura bate com o sistema legado.

---

## 🏗️ A Arquitetura Medalhão

O pipeline foi inteiramente desenvolvido em **PySpark** simulando a engine do Databricks, estruturado nas seguintes camadas:

*   🥉 **Camada Bronze (Raw/Landing):** Ingestão de carga em lote via API, aplicando validação rígida de *Schema* e formatando para Delta.
*   🥈 **Camada Silver (Cleansed/Conformed):** Aplicação de *Expectations* (Regras de DQ). Registros válidos (Preço > 0, Classes catalogadas) avançam. Anomalias são desviadas para a tabela de Quarentena com *flags* de erro, garantindo a rastreabilidade da falha do sistema gerador.
*   🥇 **Camada Gold (Data Mart):** Refatoração da base para um modelo estrela (*Star Schema*). Agregação por dimensões de negócio e cálculo de volume financeiro transacionado.

---

## 🛡️ Governança e Reapontamento de BI

A etapa final do projeto garante a integração com as ferramentas de visualização e o catálogo de dados (Unity Catalog):

*   **Validação de Paridade:** Script de cruzamento multidimensional (`FULL OUTER JOIN`) comparando as volumetrias e recebimentos financeiros entre o Legado e a base Gold. Só avança se o *delta* for exatamente zero.
*   **Reapontamento de BI (Power BI/Tableau):** Documentação do fluxo de *hot-swap* (troca de fonte) via *XMLA Endpoint* e refatoração de *datasets* (M Query), garantindo a transição sem quebra visual de painéis de diretoria.
*   **Unity Catalog:** Descoberta e linhagem das métricas certificadas, atestando a qualidade do ativo de dados para a organização.

---

## 👨‍💻 Autor

**Vinicius Marques do Nascimento**  
*Analytics Engineer & Cientista de Dados*  
Focado em modelagem estatística rigorosa, arquitetura de dados escalável e engenharia financeira quantitativa.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Profile-blue?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/SEU-LINK-AQUI)
