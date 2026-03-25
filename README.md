# 📊 TalkToData

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)
![Streamlit](https://img.shields.io/badge/Streamlit-1.35%2B-FF4B4B?logo=streamlit)
![Powered by Claude](https://img.shields.io/badge/Powered%20by-Claude%20AI-blueviolet)
![License](https://img.shields.io/badge/License-MIT-green)

An AI-powered business intelligence dashboard that lets you explore the [Olist Brazilian E-Commerce dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) using natural language. Ask questions in plain English, get SQL, results, and charts — no SQL knowledge required.

---

## ✨ Features

- **📈 BI Dashboard** — KPIs, revenue trends, top product categories, order status breakdown, revenue by state, and review score distribution
- **🤖 AI Insights** — Claude automatically generates a plain-English business summary of the data on load
- **💬 Natural Language Chat** — type any question about the data and get back the SQL query, a results table, and an auto-generated chart
- **⚡ Fast queries** — powered by DuckDB reading directly from SQLite

---

## 🖥️ Demo

> **Live demo:** *(add your Streamlit Cloud URL here after deploying)*

Example questions you can ask:
- *"Which 5 product categories have the highest average review score?"*
- *"Show monthly revenue for 2018"*
- *"What percentage of orders were delivered late?"*
- *"Which states have the most customers?"*
- *"Show the top 10 sellers by total revenue"*

---

## 🛠️ Tech Stack

| Layer | Tool |
|---|---|
| UI & app framework | [Streamlit](https://streamlit.io) |
| Query engine | [DuckDB](https://duckdb.org) |
| Charts | [Plotly](https://plotly.com/python/) |
| LLM (text-to-SQL + insights) | [Claude via Anthropic API](https://www.anthropic.com) |
| Data | [Olist Brazilian E-Commerce](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) |

---

## 🚀 Getting Started

### 1. Clone the repo
```bash
git clone https://github.com/YOUR_USERNAME/talktodata.git
cd talktodata
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Get the dataset
Download the SQLite version of the Olist dataset from Kaggle:

👉 [kaggle.com/datasets/terencicp/e-commerce-dataset-by-olist-as-an-sqlite-database](https://www.kaggle.com/datasets/terencicp/e-commerce-dataset-by-olist-as-an-sqlite-database)

Rename the file to `olist.db` and place it in the root of the project (same folder as `app.py`).

> The database file is gitignored and will not be pushed to GitHub.

### 4. Add your Anthropic API key

Copy the example secrets file:
```bash
cp .streamlit/secrets.toml.example .streamlit/secrets.toml
```

Then edit `.streamlit/secrets.toml` and add your key:
```toml
ANTHROPIC_API_KEY = "your_key_here"
```

Get an API key at [console.anthropic.com](https://console.anthropic.com).

### 5. Run the app
```bash
streamlit run app.py
```

---

## ☁️ Deploy to Streamlit Cloud

1. Push this repo to GitHub
2. Go to [share.streamlit.io](https://share.streamlit.io) and connect your repo
3. In the Streamlit Cloud dashboard, go to **Settings → Secrets** and add:
```toml
ANTHROPIC_API_KEY = "your_key_here"
```
4. For the database: either use a hosted SQLite alternative or instruct users to run locally

---

## 📁 Project Structure

```
talktodata/
├── app.py                          # main Streamlit app
├── requirements.txt                # Python dependencies
├── .gitignore
├── .streamlit/
│   └── secrets.toml.example        # template for API key (safe to commit)
└── README.md
```

---

## 📊 Dataset

This project uses the [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce), which contains ~100,000 orders from 2016–2018 across multiple Brazilian marketplaces.

The dataset is licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).

---

## 📄 License

MIT
