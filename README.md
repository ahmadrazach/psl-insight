# PSL Insight

**PSL Insight** is a lightweight, interactive search tool for **PSL Season 9 (Feb–Mar 2024)** ball-by-ball data. Search with natural language (e.g., _"Shaheen Afridi wickets at Gaddafi Stadium"_) and instantly explore results.

---

## 🚀 Features

- Natural language search with **category filters** (Wickets, Runs, Extras).
- **Precision & Recall** metrics in plain English.
- Quick stats for top results (runs, wickets, boundaries, top players).
- Detailed match/event table with similarity scores.
- Built-in dataset (`psl.csv`) — no extra setup.
- Toggle explanations for every section.

---

## 🛠 Tech

- **Frontend:** HTML, CSS, JS
- **Search:** TF-IDF + cosine similarity
- **Data:** PSL Season 9 CSV (Feb–Mar 2024). *Note: Contains batting/bowling info but not fielder names (catches).*

---

## 📦 Usage

1. Put `psl.csv` in the project folder.
2. Open `index.html` in your browser.
3. Type queries and explore PSL data.

---

## 💡 Example Queries

- `Babar Azam running sixes`
- `Shaheen Afridi yorkers`
- `Fakhar Zaman runs at National Stadium`

---

## ❓ Why You Might See Other Venues or Teams

Search is similarity-based, so results _prefer_ matches but may include others if textually close.  
Use **"Only show these in results"** or add more specific query terms to filter.
