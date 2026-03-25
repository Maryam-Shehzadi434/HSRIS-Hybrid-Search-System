<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HSRIS - Hybrid Semantic Retrieval & Intelligence System</title>
    <style>
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', sans-serif;
            line-height: 1.6;
            max-width: 1000px;
            margin: 0 auto;
            padding: 20px;
            color: #24292e;
            background: #fff;
        }
        .header {
            text-align: center;
            border-bottom: 1px solid #e1e4e8;
            padding-bottom: 20px;
            margin-bottom: 30px;
        }
        h1 { font-size: 2.5em; margin-bottom: 10px; color: #0366d6; }
        .badges {
            margin: 15px 0;
        }
        .badge {
            display: inline-block;
            padding: 5px 10px;
            margin: 0 5px;
            border-radius: 5px;
            font-size: 12px;
            font-weight: bold;
            color: white;
        }
        .python { background: #3776AB; }
        .pytorch { background: #EE4C2C; }
        .gradio { background: #FF6B6B; }
        .license { background: #28a745; }
        .feature-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }
        .feature-card {
            border: 1px solid #e1e4e8;
            border-radius: 8px;
            padding: 20px;
            background: #f6f8fa;
        }
        .feature-card h3 { margin-top: 0; color: #0366d6; }
        .architecture {
            background: #f6f8fa;
            padding: 20px;
            border-radius: 8px;
            text-align: center;
            font-family: monospace;
            margin: 20px 0;
            overflow-x: auto;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }
        th, td {
            border: 1px solid #e1e4e8;
            padding: 10px;
            text-align: left;
        }
        th { background: #f6f8fa; }
        .code-block {
            background: #f6f8fa;
            padding: 15px;
            border-radius: 8px;
            overflow-x: auto;
            font-family: monospace;
            font-size: 14px;
        }
        .footer {
            text-align: center;
            margin-top: 50px;
            padding-top: 20px;
            border-top: 1px solid #e1e4e8;
            color: #586069;
        }
        a { color: #0366d6; text-decoration: none; }
        a:hover { text-decoration: underline; }
    </style>
</head>
<body>

<div class="header">
    <h1>🔍 HSRIS</h1>
    <p><strong>Hybrid Semantic Retrieval & Intelligence System</strong></p>
    <p>Customer Support Ticket Search Engine | TF-IDF + GloVe | Dual GPU Optimized</p>
    
    <div class="badges">
        <span class="badge python">Python 3.8+</span>
        <span class="badge pytorch">PyTorch 2.0</span>
        <span class="badge gradio">Gradio 4.19</span>
        <span class="badge license">MIT License</span>
    </div>
</div>

## 📌 Overview

HSRIS is a hybrid search system for customer support tickets that combines:

- **Keyword-based retrieval** using TF-IDF (Term Frequency-Inverse Document Frequency)
- **Semantic retrieval** using GloVe word embeddings
- **Weighted combination** with adjustable α parameter

---

## 🚀 Live Demo

**[👉 Launch HSRIS on Hugging Face Spaces](https://huggingface.co/spaces/YOUR_USERNAME/hsris-ticket-search)**

---

## 📊 Dataset

| Property | Value |
|----------|-------|
| **Source** | [Customer Support Ticket Dataset (Kaggle)](https://www.kaggle.com/datasets/waseemalastal/customer-support-ticket-dataset) |
| **Records** | 8,469 tickets |
| **Key Fields** | Ticket Description, Ticket Type, Ticket Priority, Ticket Channel, Resolution |

---

## 🏗️ System Architecture

<div class="architecture">
<pre>
Input Query
     │
     ├──────────────────┬──────────────────┐
     ▼                  ▼                  ▼
TF-IDF Vectorizer   GloVe Embeddings   α Slider
     │                  │                  │
     ▼                  ▼                  ▼
Keyword Scores     Semantic Scores    Weight Control
     │                  │                  │
     └──────────────────┴──────────────────┘
                    │
                    ▼
     Final Score = α × TF-IDF + (1-α) × GloVe
                    │
                    ▼
        Top-3 Similar Tickets + Resolutions
</pre>
</div>

---

## ✨ Features

<div class="feature-grid">
    <div class="feature-card">
        <h3>🔍 TF-IDF Keyword Search</h3>
        <p>Exact word matching with custom tokenizer, n-grams, and IDF weighting built from scratch.</p>
    </div>
    <div class="feature-card">
        <h3>🧠 GloVe Semantic Search</h3>
        <p>300-dimensional word embeddings with TF-IDF weighted averaging to prevent semantic dilution.</p>
    </div>
    <div class="feature-card">
        <h3>⚖️ Hybrid Scoring</h3>
        <p><code>Score = α × TF-IDF + (1-α) × GloVe</code><br>Adjustable α slider (0.0 to 1.0)</p>
    </div>
    <div class="feature-card">
        <h3>⚡ Dual GPU Optimization</h3>
        <p>7.7x speedup using DataParallel across dual T4 GPUs on Kaggle.</p>
    </div>
    <div class="feature-card">
        <h3>📊 OOV Handling</h3>
        <p>Explicit <code>&lt;UNK&gt;</code> token for out-of-vocabulary words.</p>
    </div>
    <div class="feature-card">
        <h3>🎨 Gradio Interface</h3>
        <p>Interactive web app with side-by-side TF-IDF vs GloVe comparison.</p>
    </div>
</div>

---

## 📈 Performance Metrics

| Metric | Value |
|--------|-------|
| Dataset Size | 8,469 tickets |
| Vocabulary | 5,000 terms |
| Embeddings | GloVe 200-dim |
| GPU | Dual T4 (Kaggle) |
| Speedup (100 queries) | 7.7x |
| Precision@5 (Hybrid) | 22% |
| Precision@5 (TF-IDF) | 18% |
| Precision@5 (GloVe) | 17% |

---

## 🛠️ Tech Stack

| Category | Technologies |
|----------|--------------|
| **Language** | Python 3.8+ |
| **Deep Learning** | PyTorch (Dual GPU support) |
| **Data Processing** | NumPy, Pandas, Regex |
| **Visualization** | Matplotlib |
| **Deployment** | Gradio, Hugging Face Spaces |

---

## 📁 Project Structure
