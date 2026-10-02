# ☕ SQLPaybook: Interactive SQL Playbook

33 step-by-step SQL scenarios on a coffee shop database, in a **single Google Colab notebook**. Built for **SQL practice and quick revision**.

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/shreyal18ss/SQLPaybook/blob/main/CoffeeShop_SQLipynb.ipynb)

> ⚠️ **Heads up: this project is vibe coded.**
> I built it with AI assistance for my own SQL practice and quick revision. 

---

## 🚀 Quick start

1. Click the **Open in Colab** badge above.
2. Click **Runtime → Run all**.
3. Open the public link printed at the end. That is your interactive playbook.

> 💡 The link only works while the Colab session is running. Re-run the notebook to get a fresh one.
> If the page asks for a password, use the IP address printed by the notebook.

Nothing to install. The notebook sets up its own database and web page.

---

## 🎯 What you can practise (33 scenarios)

Each scenario shows the question, then walks through the SQL one step at a time with the live result of every step.

| Scenarios | Topics |
|-----------|--------|
| 1 to 4 | **Foundations**: SELECT / WHERE / ORDER BY, NULL handling and CASE, string functions, dates |
| 5 to 7 | **Joins and aggregation**: GROUP BY / HAVING, UNION vs UNION ALL, pivoting with CASE |
| 8 to 13 | **Window functions**: ROW_NUMBER / RANK / DENSE_RANK, tie-breaking, NULL ordering, top-N with ties, NTILE / PERCENT_RANK / CUME_DIST, LAG / LEAD / running totals |
| 14 to 17 | **Subqueries and CTEs**: nested subqueries, chained CTEs, recursive CTEs (series, org hierarchy) |
| 18 to 23 | **More patterns**: JSON parsing and filtering, anti-joins, FIRST_VALUE / LAST_VALUE, moving averages, repeat-purchase intervals |
| 24 to 33 | **Advanced, interview-style**: gaps and islands, sessionization, market basket, Pareto, peak concurrency, MoM retention, forward-fill, MoM growth, median without MEDIAN, rolling 3-day revenue |

Every step has a keyword badge and a short explanation, and **View Source Tables** shows the tables that scenario uses.

---

## 🧭 How to use it for revision

1. **Skim first**: read the question and the step labels to refresh the concept.
2. **Try before you peek**: write the query yourself, then compare with the step's SQL.
3. **Check the data**: open **View Source Tables** to see what the query works on.
4. **Break it on purpose**: change a JOIN type, a GROUP BY or a filter and see how the output changes.
5. **Repeat the weak spots**: come back to the scenarios you got wrong.

---

## 🗄️ The sample data

An in-memory SQLite database, rebuilt every time the notebook runs. It holds eight tables:

| Table | What it holds |
|-------|---------------|
| `stores` | 4 coffee shops (Seattle, Portland, Austin, Denver) |
| `customers` | 8 customers with loyalty level and join date |
| `products` | 12 menu items in Espresso, Brewed and Bakery categories |
| `orders` | 12 orders, linked to a customer and a store |
| `order_items` | 16 order lines, linked to an order and a product |
| `employees` | 6 staff with a `manager_id` reporting chain |
| `store_logs` | 3 equipment logs stored as JSON text |
| `store_shifts` | 4 staff shifts with start and end times |

**How they connect:** `orders` → `customers` and `stores`; `order_items` → `orders` and `products`; `employees.manager_id` → `employees`; `store_logs` and `store_shifts` → `stores`; `store_shifts` → `employees`.

---

## 📘 SQL Topics Guide

New to a topic, or short on time? Read the **[SQL Topics Guide](docs/SQL_TOPICS_GUIDE.md)**. For every topic it gives you:

- a plain-English explanation in one line
- a **skeleton** to fill in (for example `SELECT ... FROM ... WHERE ... GROUP BY ... HAVING ... ORDER BY ... LIMIT`)
- **all the alternative ways** to write the same thing
- diagrams, real query results, a dialect cheat sheet and a common-mistakes checklist

Keep the `docs/img/` folder next to the guide, or the diagrams will not show.

---

## 📁 What is in this repo

```
SQLPaybook/
├── CoffeeShop_SQLipynb.ipynb   # the whole playbook: database, scenarios and web page
├── docs/
│   ├── SQL_TOPICS_GUIDE.md         # illustrated topic guide
│   └── img/                        # diagrams used by the guide
└── README.md
```

Inside the notebook, the code cells run in this order:

| Block | Job |
|-------|-----|
| 1 | Installs and imports what the notebook needs |
| 2 | Builds the in-memory SQLite database and seeds the coffee shop data |
| 3 | Holds the catalog of 33 scenarios (question, steps, SQL) |
| 4 | Defines the web page (HTML, CSS and JavaScript) |
| 5 | Runs each step's SQL with pandas and formats it for display |
| 6 | Starts the app and opens a public link with localtunnel |

---

## 🔧 Make it your own

- **Change the data**: edit the seed data in block 2 and re-run.
- **Add a scenario**: add a new entry to the catalog in block 3, copying the shape of an existing one.
- **Change the look**: edit the HTML and CSS in block 4.

---

## 🛠️ Built with

- Python, Flask and pandas
- SQLite (in-memory)
- HTML, CSS and vanilla JavaScript, with Prism.js for SQL syntax highlighting
- localtunnel for the public link
- AI assistance (vibe coded 🎧)

---

## 🤝 Feedback and contributing

Spotted a wrong query or have an idea to make it clearer? Open an [issue](https://github.com/shreyal18ss/SQLPaybook/issues) or send a pull request. Suggestions are welcome.

## 📄 License

MIT

---

*Made for learning, not perfection. Happy querying! ☕*
<img width="2244" height="1436" alt="image" src="https://github.com/user-attachments/assets/009e0c06-5bde-48ef-b115-c19c7deecd81" />

