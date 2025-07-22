# 📊 Dashboard executiva de produto SaaS com Power BI

Este projeto simula um cenário real de atuação como analista de dados em uma empresa SaaS. 

O objetivo foi construir um **dashboard executivo** para apoiar a liderança na tomada de decisões baseadas em dados, com foco especial em **retenção de clientes, engajamento com o produto e geração de receita**.

> 🔗 Acesse a [base de dados pública no Kaggle](https://www.kaggle.com/datasets/gsagar12/dspp1)
> 
> ⚠️ O arquivo do dashboard (`.pbix`) foi construído em **português**.

---

## 📌 O desafio

### 🧭 Contexto

A empresa fictícia oferece dois tipos de planos (mensal e anual) e já possui uma base relevante de clientes. Diante disso, surgem perguntas como:

- Como está a retenção ao longo do tempo?
- Qual é o tempo médio de vida dos clientes por tipo de plano?
- Quem são os clientes que mais cancelam — e por quê?
- O suporte tem relação com o churn?

Este projeto foi uma oportunidade de aplicar técnicas de modelagem de dados, DAX e visualização estratégica no Power BI, com foco em resolver problemas reais de negócio.

### 📂 Base de dados utilizada

A base é composta por quatro arquivos `.csv`, que simulam o ciclo de vida dos clientes e interações com o suporte:

- `customer_info.csv`: dados demográficos dos clientes (idade e gênero)
- `customer_product.csv`: datas de entrada/saída e tipo de plano contratado
- `product_info.csv`: detalhes dos produtos (tipo de cobrança e valor)
- `customer_cases.csv`: tickets de suporte, com canal e motivo

---

## 👣 Etapas da solução

### 1. Exploração e planejamento

Antes de tudo, explorei as tabelas e identifiquei perguntas relevantes para o negócio, como:

- Qual é a evolução da receita?
- Como está a base ativa?
- Gênero e idade influenciam no churn ou na receita?
- O suporte impacta na retenção?

A partir disso, rascunhei a estrutura do dashboard para guiar a modelagem e manter o foco nas perguntas-chave.

### 2. Tratamento e modelagem

- Remoção de colunas irrelevantes e revisão de tipos de dados
- Criação de **tabela calendário** para análises temporais
- Modelagem em formato **snowflake**
- Colunas auxiliares criadas:
  - Faixa Etária (a partir da idade)
  - Preço Mensal Equivalente (valor total / ciclo de cobrança)

### 3. Criação das medidas (DAX)

Organizei as medidas em dois grupos:

- **`SS_` (Snapshot)**: independentes de data, refletem o estado atual
  - MRR Atual, ARPU, LTV Médio, Churn Rate (média 6 meses)
- **`TMP_` (Temporais)**: para análise ao longo do tempo
  - Clientes ativos, Novos clientes, Cancelamentos, Receita, Churn

💡 Testei cada medida isoladamente durante a criação, garantindo validação passo a passo. Também adotei um padrão de nomenclatura para facilitar a organização e uso nos visuais.

### 4. Visualizações

Organizei o dashboard em **5 abas temáticas**:

1. **Snapshot**  
   Visão executiva atual: clientes ativos, MRR, ARPU, perfil da base e receita por plano.

2. **Evolução no Tempo**  
   Tendências mensais: crescimento da base, churn, receita e movimentações.

3. **Churn e Perfil**  
   Análise de cancelamentos por faixa etária, gênero, tipo de plano e uso de suporte.

4. **Receita por Segmento**  
   Receita por produto, faixa etária, gênero e cruzamentos entre essas dimensões.

5. **Suporte e Retenção**  
   Relação entre uso de suporte e churn: motivos, canais e frequência de atendimento.

---

## 📊 Resultado final

Cada aba do dashboard responde a uma pergunta estratégica e foi pensada para ser intuitiva mesmo para quem não é técnico. A navegação é clara, e os insights estão organizados para facilitar decisões rápidas e informadas.

### 🔍 Destaques de cada aba

**1. Visão Atual (Snapshot)**  
Panorama do estado atual: KPIs principais e distribuição dos clientes.

**2. Evolução no Tempo**  
Compreensão da dinâmica de crescimento, retenção e churn mês a mês.

**3. Churn e Perfil**  
Identificação de padrões de cancelamento e perfis de risco.

**4. Receita por Segmento**  
Avaliação do potencial de receita por plano e perfil de cliente.

**5. Suporte e Retenção**  
Exploração da influência do suporte na retenção.

---

## 💬 Considerações finais

Escolhi esse case por representar bem os desafios reais de um negócio SaaS: entender o comportamento dos clientes, reduzir churn e tomar decisões com base em dados.

Foi uma ótima forma de aplicar na prática conceitos de DAX, modelagem e visualização, com foco no que importa: **gerar insights acionáveis**.

### 💡 Aprendizados

- Organização e padronização tornam o projeto mais robusto
- Nem toda métrica precisa existir de início — mas toda métrica criada precisa ser validada
- Clareza visual depende tanto do design quanto da estruturação dos dados

---

## 🔄 Próximos passos

- Criar versões com diferentes identidades visuais
- Recriar a análise no Looker Studio para fins comparativos
- Publicar uma versão online e navegável do dashboard

---

## 📝 Licença

Este projeto está licenciado sob a [Licença MIT](./LICENSE).
