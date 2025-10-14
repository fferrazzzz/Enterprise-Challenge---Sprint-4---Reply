# Hermes Reply – Projeto Indústria 4.0

## 📄 Visão Geral

Este projeto tem como objetivo demonstrar um fluxo integrado de dados na Indústria 4.0, desde a coleta de dados por sensores simulados até a visualização de KPIs e alertas em um dashboard. O projeto foi desenvolvido em Python, utilizando Streamlit, SQLite e scikit-learn, contemplando todos os requisitos das entregas anteriores.

O fluxo completo do projeto inclui:

1. **Sensores simulados/ESP32**: geração de leituras de temperatura e umidade.
2. **Ingestão e armazenamento**: persistência das leituras em banco de dados SQLite.
3. **Machine Learning**: treinamento de modelo de regressão linear para previsão de temperatura a partir da umidade.
4. **Visualização e alertas**: dashboard em Streamlit com KPIs, gráficos e alertas configuráveis.

---

## 🛠 Estrutura do Repositório

```
/ ─ Raiz do projeto
├─ /docs/arquitetura       -> Diagrama do fluxo integrado (.drawio/.png)
├─ /ingest/                -> Código de geração e ingestão de dados simulados
├─ /db/                    -> Script SQL para criação e carga de tabelas
├─ /ml/                    -> Notebook ou script de ML com métricas e visualizações
├─ /dashboard/             -> Aplicativo Streamlit com KPIs e alertas
├─ main_app.py             -> Script principal do Streamlit
└─ README.md               -> Este arquivo
```

---

## ⚙️ Setup Local

1. Clone o repositório:

```bash
git clone <URL_DO_REPOSITORIO>
cd <PASTA_DO_REPOSITORIO>
```

2. Instale as dependências:

```bash
pip install streamlit pandas numpy scikit-learn
```

3. Execute o app Streamlit:

```bash
streamlit run main_app.py
```

4. Abra o navegador no link que o Streamlit mostrar (geralmente `http://localhost:8501`).

---

## 🧩 Arquitetura do Fluxo

O diagrama completo está disponível em `/docs/arquitetura/Diagrama HermesReplyDB.drawio`.

**Fluxo de dados:**

```
Sensores Simulados (Temperatura/Umidade) → Ingestão → Banco SQLite → ML (Regressão Linear) → Dashboard Streamlit → KPIs / Alertas
```

---

## 🗄 Banco de Dados

**Tabela:** `sensores`

| Coluna      | Tipo         | PK | Observações        |
| ----------- | ------------ | -- | ------------------ |
| id          | INT          | ✓  | Auto-increment     |
| timestamp   | DATETIME     | ✗  | Momento da leitura |
| temperatura | DECIMAL(5,2) | ✗  | Temperatura (°C)   |
| umidade     | DECIMAL(5,2) | ✗  | Umidade (%)        |

**Script de criação:** `/db/create_tables.sql`

---

## 🤖 Machine Learning

* Modelo: Regressão Linear
* Variável independente: `umidade`
* Variável dependente: `temperatura`
* Métricas exibidas: MAE (Erro Médio Absoluto), R²
* Visualizações: série temporal, relação entre temperatura real e prevista

---

## 📊 Dashboard e Alertas

* Implementado em **Streamlit**
* KPIs exibidos: temperatura média, umidade média, MAE do modelo
* Gráficos de linha para temperatura e umidade
* Alertas configuráveis via sidebar (threshold de temperatura)
* Possibilidade de regenerar dados simulados via botão

---

## 📝 Reprodutibilidade

**Ordem de execução:**

1. Gerar dados simulados e inserir no banco (automático se banco vazio)
2. Treinar modelo de ML e calcular métricas
3. Rodar dashboard Streamlit para visualizar KPIs e alertas

**Observações:**

* Todos os dados são simulados via Python, sem necessidade de CSV ou hardware real.
* Scripts e notebook estão versionados no GitHub.

---

## 📹 Vídeo Explicativo

Link do vídeo demonstrando o fluxo ponta-a-ponta: [INSERIR LINK AQUI]

---

## ✅ Tecnologias Utilizadas

* Python 3
* Streamlit
* SQLite
* pandas, numpy
* scikit-learn
* Diagrams.net (para diagrama ER)

---

## 👥 Equipe

* Integrantes: [NOMES DOS PARTICIPANTES]

---

**Hermes Reply – Indústria 4.0**
