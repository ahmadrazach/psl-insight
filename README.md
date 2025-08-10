Browser‑based search and retrieval‑metrics explorer for PSL Season 9 (ball‑by‑ball). No backend. Deploy anywhere.

## What it does

• Free‑text search over ball‑by‑ball events.
• Team/venue/season filters.
• Top‑K ranking via TF‑IDF + cosine similarity.
• Retrieval metrics: Precision & Recall per label (batting, wicket, extras, other).
• Quick stats for the current result set (runs, wickets, 4s/6s, top batters/bowlers).

## Dataset

• Source: PSL Season 9 (Feb–Mar 2024), ball‑by‑ball (Cricsheet derived).
• Fields used: match*id, season, start_date, venue, innings, ball, batting_team, bowling_team, striker, non_striker, bowler, runs_off_bat, wides, noballs, byes, legbyes, penalty, wicket_type, player_dismissed, other*\*.

## How it works

• Build TF‑IDF vectors in the browser from a rich text view of each row.
• Embed query with the same vocabulary.
• Rank with cosine similarity (Top‑K).
• Auto‑label rows:
• wicket: any wicket_type present
• batting: runs_off_bat ≥ 1
• extras: sum of wides/noballs/byes/legbyes/penalty ≥ 1
• other: otherwise
• Compute Precision = TP/(TP+FP) and Recall = TP/(TP+FN) on the filtered set.

## Quick start 1. Place these files together:

index.html
psl.csv # your Season 9 ball-by-ball CSV

    2.	Open index.html in a browser

– or push to GitHub and deploy on Vercel/Netlify as a static site.

(No API keys. No servers. Everything runs client‑side.)

Usage
• Type a query (e.g., Shaheen Afridi wicket Gaddafi).
• Set filters (season/team/venue) as needed.
• Choose a “Retrieval label” for metrics (batting/wicket/extras/other).
• Click Search (or press Enter).
• Review:
• Ranked rows with emoji match quality (🟢✨ ≥0.80, 🟢 ≥0.50, 🟡 ≥0.20, 🔴 <0.20)
• Precision/Recall for the chosen label
• Quick stats for the current Top‑K

Example queries
• Babar Azam boundaries
• Islamabad United wides
• Multan Sultans wickets National Stadium
• Fakhar Zaman sixes Lahore
• Usama Mir bowling economy

Tech
• HTML + Vanilla JS
• PapaParse for CSV
• In‑browser TF‑IDF + cosine

Roadmap
• CSV upload for any PSL season.
• Per‑match and per‑player dashboards.
• N‑gram tokens and stop‑word cleanup.
• Optional sentence embeddings (precomputed) for semantic search.

License

MIT for code. Data © respective owners (Cricsheet‑derived).
