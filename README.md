<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Online Retail Dataset — ML Lab</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;600&family=Sora:wght@400;600;700;800&display=swap');

  :root {
    --bg: #0d1117;
    --card: #161b22;
    --border: #30363d;
    --accent: #58a6ff;
    --green: #3fb950;
    --orange: #f78166;
    --yellow: #d29922;
    --text: #e6edf3;
    --muted: #8b949e;
    --code-bg: #1f2937;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Sora', sans-serif;
    max-width: 860px;
    margin: 0 auto;
    padding: 40px 24px;
    line-height: 1.7;
  }

  h1 {
    font-size: 2rem;
    font-weight: 800;
    color: var(--text);
    margin-bottom: 12px;
  }

  h2 {
    font-size: 1.15rem;
    font-weight: 700;
    color: var(--accent);
    margin: 32px 0 12px;
    padding-bottom: 6px;
    border-bottom: 1px solid var(--border);
  }

  .badges {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 24px;
  }

  .badge {
    padding: 4px 12px;
    border-radius: 20px;
    font-size: 0.75rem;
    font-weight: 600;
    font-family: 'Fira Code', monospace;
  }

  .badge-blue  { background: #1f3a5f; color: #58a6ff; border: 1px solid #2d5a8f; }
  .badge-green { background: #1a3a2a; color: #3fb950; border: 1px solid #2d6a3f; }
  .badge-orange{ background: #3a2a1a; color: #f78166; border: 1px solid #6a4a2d; }
  .badge-done  { background: #1a3a1a; color: #56d364; border: 1px solid #2d6a2d; }

  .about {
    background: var(--card);
    border: 1px solid var(--border);
    border-left: 4px solid var(--accent);
    border-radius: 8px;
    padding: 16px 20px;
    color: var(--muted);
    font-size: 0.95rem;
  }

  table {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.9rem;
    margin-top: 8px;
  }

  th {
    background: var(--card);
    color: var(--accent);
    padding: 10px 14px;
    text-align: left;
    border: 1px solid var(--border);
    font-weight: 600;
  }

  td {
    padding: 9px 14px;
    border: 1px solid var(--border);
    color: var(--text);
  }

  tr:nth-child(even) td { background: #161b2288; }
  tr:hover td { background: #1f2937; }

  .findings-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
    gap: 12px;
    margin-top: 8px;
  }

  .finding-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 14px 18px;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .finding-card .icon { font-size: 1.5rem; }

  .finding-card .info .label {
    font-size: 0.72rem;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }

  .finding-card .info .value {
    font-size: 0.95rem;
    font-weight: 700;
    color: var(--text);
  }

  pre {
    background: var(--code-bg);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 16px;
    overflow-x: auto;
    margin-top: 8px;
  }

  code {
    font-family: 'Fira Code', monospace;
    font-size: 0.85rem;
    color: #79c0ff;
  }

  .cmd { color: #d2a8ff; }
  .comment { color: #6e7681; }

  hr {
    border: none;
    border-top: 1px solid var(--border);
    margin: 32px 0;
  }

  .author-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 18px 20px;
    display: flex;
    align-items: center;
    gap: 16px;
  }

  .author-avatar {
    width: 52px; height: 52px;
    border-radius: 50%;
    background: linear-gradient(135deg, #58a6ff, #3fb950);
    display: flex; align-items: center; justify-content: center;
    font-size: 1.4rem; font-weight: 800; color: #0d1117;
  }

  .author-info .name { font-weight: 700; font-size: 1rem; }
  .author-info .role { color: var(--muted); font-size: 0.85rem; }

  .star-box {
    margin-top: 28px;
    text-align: center;
    padding: 16px;
    background: var(--card);
    border: 1px dashed var(--border);
    border-radius: 10px;
    color: var(--muted);
    font-size: 0.95rem;
  }

  .star-box span { color: #f1c40f; font-size: 1.2rem; }
</style>
</head>
<body>

<h1>🛒 Online Retail Dataset — ML Lab</h1>

<div class="badges">
  <span class="badge badge-blue">Python 3.x</span>
  <span class="badge badge-green">Pandas</span>
  <span class="badge badge-orange">Jupyter Notebook</span>
  <span class="badge badge-done">✔ Completed</span>
</div>

<hr>

<h2>📌 About This Project</h2>
<div class="about">
  This is a <strong>Machine Learning Lab Evaluation</strong> project where I performed
  data analysis on the <strong>Online Retail Dataset</strong> using Python and Pandas.
  The goal was to extract useful business insights such as top products,
  revenue, peak shopping hours, and customer behaviour.
</div>

<h2>📂 Dataset</h2>
<table>
  <tr><th>Detail</th><th>Info</th></tr>
  <tr><td>Name</td><td>Online Retail Dataset</td></tr>
  <tr><td>File</td><td>Online Retail.xlsx</td></tr>
  <tr><td>Rows</td><td>5,36,641</td></tr>
  <tr><td>Columns</td><td>10</td></tr>
</table>

<h2>🔧 Libraries Used</h2>
<table>
  <tr><th>Library</th><th>Purpose</th></tr>
  <tr><td>pandas</td><td>Data manipulation and analysis</td></tr>
  <tr><td>matplotlib</td><td>Data visualization</td></tr>
  <tr><td>seaborn</td><td>Statistical plots</td></tr>
</table>

<h2>📊 Tasks Performed</h2>
<table>
  <tr><th>#</th><th>Task</th></tr>
  <tr><td>1</td><td>Load data and display 10 rows</td></tr>
  <tr><td>2</td><td>Check rows and missing values</td></tr>
  <tr><td>3</td><td>Remove duplicate values</td></tr>
  <tr><td>4</td><td>Add Revenue column</td></tr>
  <tr><td>5</td><td>Top 10 selling products by quantity</td></tr>
  <tr><td>6</td><td>Calculate total revenue of the store</td></tr>
  <tr><td>7</td><td>Total number of unique customers</td></tr>
  <tr><td>8</td><td>Calculate average order value</td></tr>
  <tr><td>9</td><td>Country with highest number of orders</td></tr>
  <tr><td>10</td><td>Products bought together</td></tr>
  <tr><td>11</td><td>Customers who purchased more than 10 items</td></tr>
  <tr><td>12</td><td>Peak shopping hours</td></tr>
</table>

<h2>📈 Key Findings</h2>
<div class="findings-grid">
  <div class="finding-card"><div class="icon">💰</div><div class="info"><div class="label">Total Revenue</div><div class="value">£9,726,006.95</div></div></div>
  <div class="finding-card"><div class="icon">👥</div><div class="info"><div class="label">Unique Customers</div><div class="value">4,372</div></div></div>
  <div class="finding-card"><div class="icon">🏆</div><div class="info"><div class="label">Top Country</div><div class="value">United Kingdom</div></div></div>
  <div class="finding-card"><div class="icon">⏰</div><div class="info"><div class="label">Peak Shopping Hour</div><div class="value">12:00 PM</div></div></div>
  <div class="finding-card"><div class="icon">🥇</div><div class="info"><div class="label">Best Selling Product</div><div class="value">WW2 Gliders (53,751)</div></div></div>
  <div class="finding-card"><div class="icon">🧾</div><div class="info"><div class="label">Avg Order Value</div><div class="value">£375.52</div></div></div>
</div>

<h2>🚀 How to Run</h2>
<pre><code><span class="comment"># 1. Clone this repository</span>
<span class="cmd">git clone</span> https://github.com/aryanvirdi/Online-Retail-Dataset.git

<span class="comment"># 2. Install required libraries</span>
<span class="cmd">pip install</span> pandas matplotlib seaborn openpyxl

<span class="comment"># 3. Open Jupyter Notebook</span>
<span class="cmd">jupyter notebook</span>

<span class="comment"># 4. Run Online_Retail_Dataset.ipynb</span></code></pre>

<hr>

<h2>👨‍💻 Author</h2>
<div class="author-card">
  <div class="author-avatar">A</div>
  <div class="author-info">
    <div class="name">Aryan Virdi</div>
    <div class="role">Student — Machine Learning Lab</div>
  </div>
</div>

<div class="star-box">
  <span>⭐</span> If you found this helpful, give it a star on GitHub!
</div>

</body>
</html>
