<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>HSRIS - Hybrid Semantic Retrieval & Intelligence System</title>

<style>
body {
    font-family: Arial, sans-serif;
    max-width: 900px;
    margin: auto;
    padding: 20px;
    line-height: 1.6;
    color: #24292e;
}

h1, h2, h3 {
    color: #0366d6;
}

.header {
    text-align: center;
    border-bottom: 1px solid #ddd;
    margin-bottom: 20px;
}

.badge {
    display: inline-block;
    padding: 5px 10px;
    margin: 5px;
    border-radius: 5px;
    color: white;
    font-size: 12px;
}

.python { background: #3776AB; }
.pytorch { background: #EE4C2C; }
.gradio { background: #FF6B6B; }
.license { background: #28a745; }

.section {
    margin-top: 30px;
}

.card {
    border: 1px solid #ddd;
    padding: 15px;
    border-radius: 8px;
    margin-bottom: 15px;
    background: #f6f8fa;
}

pre {
    background: #f6f8fa;
    padding: 15px;
    border-radius: 8px;
    overflow-x: auto;
}

table {
    width: 100%;
    border-collapse: collapse;
}

th, td {
    border: 1px solid #ddd;
    padding: 10px;
}

th {
    background: #f6f8fa;
}
</style>
</head>

<body>

<div class="header">
    <h1>🔍 HSRIS</h1>
    <p><strong>Hybrid Semantic Retrieval & Intelligence System</strong></p>
    <p>TF-IDF + GloVe | Dual GPU Optimized</p>

    <span class="badge python">Python</span>
    <span class="badge pytorch">PyTorch</span>
    <span class="badge gradio">Gradio</span>
    <span class="badge license">MIT</span>
</div>

<div class="section">
<h2>📌 Overview</h2>
<p>
HSRIS is a hybrid search system combining:
</p>
<ul>
    <li><b>TF-IDF</b> for keyword matching</li>
    <li><b>GloVe embeddings</b> for semantic understanding</li>
    <li><b>Hybrid scoring</b> using adjustable α</li>
</ul>
</div>

<div class="section">
<h2>🚀 Live Demo</h2>
<p>
<a href="https://huggingface.co/spaces/YOUR_USERNAME/hsris-ticket-search" target="_blank">
Launch on Hugging Face
</a>
</p>
</div>

<div class="section">
<h2>📊 Dataset</h2>
<table>
<tr><th>Property</th><th>Value</th></tr>
<tr><td>Records</td><td>8,469</td></tr>
<tr><td>Source</td><td>Kaggle</td></tr>
<tr><td>Fields</td><td>Description, Type, Priority, Channel, Resolution</td></tr>
</table>
</div>

<div class="section">
<h2>🏗️ Architecture</h2>
<pre>
Input Query
     │
 ┌───────┬────────┬────────┐
 ▼       ▼        ▼
TF-IDF  GloVe     α
 │       │        │
 ▼       ▼        ▼
Scores  Scores  Weight
 └───────┴────────┘
         │
         ▼
Final Score = α × TF-IDF + (1-α) × GloVe
         │
         ▼
 Top-K Results
</pre>
</div>

<div class="section">
<h2>✨ Features</h2>

<div class="card">
<h3>TF-IDF Search</h3>
<p>Keyword-based retrieval with custom tokenizer</p>
</div>

<div class="card">
<h3>GloVe Semantic Search</h3>
<p>Uses embeddings for semantic similarity</p>
</div>

<div class="card">
<h3>Hybrid Scoring</h3>
<p>Score = α × TF-IDF + (1-α) × GloVe</p>
</div>

<div class="card">
<h3>GPU Optimization</h3>
<p>7.7× speedup using dual GPUs</p>
</div>

</div>

<div class="section">
<h2>📈 Performance</h2>
<table>
<tr><th>Metric</th><th>Value</th></tr>
<tr><td>Dataset Size</td><td>8,469</td></tr>
<tr><td>Speedup</td><td>7.7×</td></tr>
<tr><td>Precision@5 (Hybrid)</td><td>22%</td></tr>
</table>
</div>

<div class="section">
<h2>🛠️ Tech Stack</h2>
<ul>
    <li>Python</li>
    <li>PyTorch</li>
    <li>NumPy, Pandas</li>
    <li>Gradio</li>
</ul>
</div>

<div class="section">
<h2>📁 Project Structure</h2>
<pre>
hsris/
│── data/
│── models/
│── app.py
│── README.html
</pre>
</div>

<div class="section">
<h2>📄 License</h2>
<p>MIT License</p>
</div>

</body>
</html>
