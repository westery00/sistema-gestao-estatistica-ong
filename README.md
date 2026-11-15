<div align="center">

# 🐾 Instituto Eu Sou o Bicho
### Sistema Integrado de Cadastro, Controle Operacional e Estatística para ONG

[![Excel/Google Sheets](https://img.shields.io/badge/Stack-Excel%20%2F%20Google%20Sheets-green?style=for-the-badge&logo=microsoft-excel&logoColor=white)](https://microsoft.com)
[![Data Modeling](https://img.shields.io/badge/Modelagem-Relacional%20Simulada-blue?style=for-the-badge&logo=databricks&logoColor=white)](https://github.com)
[![Applied Statistics](https://img.shields.io/badge/Estatística-Descritiva%20%26%20Probabilidade-orange?style=for-the-badge&logo=google-analytics&logoColor=white)](https://github.com)
[![Status](https://img.shields.io/badge/Status-Concluído%20%2F%20Em%20Produção-success?style=for-the-badge)]()

*Solução analítica de alta performance desenvolvida para otimizar a gestão de doadores, controle de estoque e rastreabilidade de doações em abrigos de proteção animal.*

</div>

---

## 🚀 Sobre o Problema e a Solução

### O Desafio
Organizações não-governamentais (ONGs) de proteção animal frequentemente enfrentam grandes gargalos operacionais devido à descentralização de dados. O controle manual ou fragmentado de doadores (pessoas físicas e jurídicas), entradas de insumos (ração, medicamentos, produtos de limpeza) e a distribuição para animais resgatados geram perdas de insumos, falta de previsibilidade de estoque e dificuldade na prestação de contas para parceiros e doadores.

### A Solução
O **Instituto Eu Sou o Bicho** é um sistema integrado de gestão e inteligência de dados desenvolvido em planilha eletrônica avançada (Excel / Google Planilhas). A solução simula um modelo de banco de dados relacional por meio de chaves padronizadas, automatiza o fluxo operacional de ponta a ponta e aplica rigorosos conceitos de **Estatística Descritiva e Probabilidade** para transformar dados transacionais em insights estratégicos para a diretoria da ONG.

---

## 🏗️ Arquitetura do Sistema e Modelo de Dados

Para garantir a integridade referencial sem a necessidade de um SGBD tradicional, o sistema adota uma **arquitetura relacional em abas**, interligadas por IDs estruturados e **Tabelas do Excel (ListObjects)** com expansão automática de fórmulas e formatação.

### Convenção de Chaves (IDs Padronizados)
* **`DOR-`** ➔ Doadores (Pessoas Físicas e Jurídicas)
* **`BEN-`** ➔ Beneficiários / Animais e Setores de Abrigo
* **`PRO-`** ➔ Produtos e Insumos do Catálogo
* **`DOA-`** ➔ Doações (Entradas e Registro de Suprimentos)
* **`DIS-`** ➔ Distribuições (Saídas e Consumo Interno)

```mermaid
graph TD
    A[Doadores (DOR-)] -->|Registra| C[Doações (DOA-)]
    B[Produtos (PRO-)] -->|Categoriza| C
    B -->|Controla Estoque| D[Distribuições (DIS-)]
    C -->|Atualiza Saldo| E[Painel de Controle & Estatísticas]
    D -->|Baixa de Estoque| E
```

---

## 🧮 Stack Tecnológica & Fórmulas Aplicadas

O ecossistema foi construído utilizando recursos avançados de manipulação de dados e modelagem matemática do Excel:

| Categoria | Função / Recurso | Aplicação Prática no Projeto |
| :--- | :--- | :--- |
| **Contagem Condicional** | `CONT.SE` / `CONT.SES` | Mapeamento de frequência relativa de doadores por categoria e tipo de doação. |
| **Agregação Inteligente** | `SOMA` / `SOMASE` | Cálculo de volume total de insumos arrecadados por período e categoria de produto. |
| **Medidas de Tendência Central** | `MÉDIA` | Análise do ticket médio e quantidade média de itens por doação recebida. |
| **Contagem de Registros** | `CONT.VALORES` | Dinamismo nas listagens de cadastros ativos e auditoria de preenchimento. |
| **Automação de Layout** | Tabelas do Excel | Expansão automática de intervalos, fórmulas estruturadas e consistência visual. |

---

## 📂 Destaques dos Módulos Principais

O sistema é modularizado em abas funcionais que cobrem toda a cadeia de suprimentos e relacionamento da ONG:

1. **`Leia-me`**: Documentação técnica interna, orientações de uso e metadados do período de apuração.
2. **`Doadores`**: Gestão cadastral unificada (PF/PJ), com contagem automatizada e análise de frequência relativa de contribuição.
3. **`Produtos`**: Catálogo categorizado de itens com controle dinâmico de estoque mínimo e alertas visuais de criticidade (*Baixo* / *Esgotado*).
4. **`Doações`**: Registro granular de entradas de insumos, contabilização de volumes e cruzamento com a tipologia dos doadores.
5. **`Painel Executivo`**: Dashboard central com indicadores-chave de desempenho (KPIs) e análises probabilísticas atualizadas em tempo real.

---

## 📊 Painel & Dinâmica de Atualização

O **Painel Executivo** consome os dados transacionais de forma dinâmica por meio de intervalos parametrizados e datas configuráveis. 
* **Atualização em Tempo Real:** Sempre que uma nova linha é inserida nas tabelas de Doações ou Distribuições, as fórmulas estruturadas recalculam instantaneamente os saldos de estoque e as probabilidades de origem.
* **Análise Estatística Embutida:** O painel traduz os dados em métricas de probabilidade (ex: probabilidade de uma doação de ração vir de pessoa jurídica vs. física) auxiliando campanhas futuras de captação de recursos.

---

## 🧭 Guia do Operador (Boas Práticas)

Para manter a integridade relacional e evitar quebra de fórmulas, siga as diretrizes abaixo:

1. **Nunca utilize linhas em branco:** Sempre insira novos registros diretamente ao final das **Tabelas do Excel** para garantir que as propriedades de auto-expansão funcionem.
2. **Respeite os Prefixo de IDs:** Ao registrar novas doações ou produtos, utilize rigorosamente o padrão estabelecido (`DOR-001`, `PRO-012`, etc.).
3. **Auditoria de Estoque:** Monitore regularmente a aba de Produtos para verificar itens com status de estoque abaixo do limite mínimo configurado.

---

## 💡 Aprendizados e Competências Demonstradas

O desenvolvimento deste projeto consolidou competências essenciais de engenharia de dados, modelagem e análise quantitativa:
* **Modelagem de Dados Conceitual:** Simulação prática de integridade referencial e chaves primárias/estrangeiras em ambientes de planilha.
* **Estatística Aplicada:** Aplicação de probabilidade e estatística descritiva para tomada de decisão em cenários com restrição de recursos.
* **Mentalidade de Produto (Data-Driven):** Foco na experiência do usuário final (operadores da ONG), entregando uma interface limpa, automatizada e à prova de erros.

---

<div align="center">
  <i>Desenvolvido com dedicação por um entusiasta de Dados e Tecnologia. Sinta-se à vontade para clonar, sugerir melhorias ou entrar em contato!</i>
</div>
