# 📰 TechCrunch Feed Distributor 🤖

## 🚀 Project Overview

This project is a comprehensive **N8N** automation solution to collect the latest news from TechCrunch feed, process it using Artificial Intelligence (AI), efficiently manage data in Google Sheets, and distribute translated summaries to Telegram and Discord. It is a stable and scalable *workflow*.

---

## ✨ Key Features

| Features | Functions |
| :--- | :--- |
| **📰 Automatic RSS Feed Fetching** | Uses `RSS Feed Trigger` to monitor TechCrunch periodically. |
| **🛡️ Data Duplicate Prevention** | Checks unique links in Google Sheets to avoid duplicate entries. |
| **🕸️ Smart Web Scraping** | Handles Google News *redirect* links and downloads article HTML code. |
| **📝 Clean Text Extraction** | Uses `HTML Extract` to get the main article text (`Main Content`), removing ads/menus. |
| **🖼️ Featured Image Extraction** | Detects and extracts the Main Image URL (`og:image`) to include in notifications. |
| **🧠 Bilingual AI Summary** | Uses **Gemini** to summarize articles and translate them into **Bahasa Melayu (BM)** and **English (EN)** in a single API call (structured JSON output). |
| **📊 Advanced Sentiment Analysis** | Analyzes article sentiment (Positive/Negative/Neutral) to add value to the data. |
| **🗂️ Scheduled Data Cleanup** | Automatically deletes data rows older than 24 hours to keep your *spreadsheet* clean. |
| **📣 Multi-Channel Distribution** | Distributes formatted summaries to **Telegram** and **Discord** simultaneously. |

---

## Result Output

🗃️ Spreadsheet Data update:<br>
https://docs.google.com/spreadsheets/d/1pyQn5vY8IOMPzWrTteUDWQyrSxokDXzxfqzYytpUulg/edit?usp=sharing

💬Telegram Channel Update:<br>
EN : https://t.me/techcrunch_en <br>
MY : https://t.me/techcrunch_my

## 🛠️ Setup & Installation

---

### Prerequisites

Before you begin, you must have:

1. **Active N8N Instance:** Running 24/7 (Recommended: **Docker** or **pm2** on a cloud server).
2. **Google Cloud Account:** To get **Gemini** API Key and access Google Sheets.
3. **Telegram Bot & Discord Webhook:** For notification integration.

### N8N Configuration

1. **Import Workflow:** Download the `workflow.json` file (provided in this repository) and import it into your N8N.
2. **Credential Connection:** Prepare and connect the following credentials: 
* `Google Sheets` (OAuth2 with Read/Write access) 
* ``Gemini/OpenAI'' (API Key) 
* `Telegram` (Bot Token) 
* `Discord` (Webhook or Bot Token)
3. **Update Specific Settings:** 
* **`RSS Feed Trigger`**: Change URL and *Poll Time* if necessary. 
* **`Google Sheets`**: Update `Spreadsheet ID` and `Sheet Name` for *all* nodes (Read, Append, Delete, Archive). 
* **`HTML Extract`**: Validate `CSS Selector` for `article-content` if the source website (TechCrunch) changes its structure.

---


## 🔁 Flow Diagram
![Workflow Screenshot](https://raw.githubusercontent.com/fyyqq/n8n-workflows/refs/heads/main/TechCrunch%20Feed%20Distributor/screenshot/Screenshot%202025-11-16%20003508.png)

---

## ⚙️ Conceptual Workflow Diagram

*This workflow shows the sequential and data merging processes required to produce a final row of data.*

---

## ⚠️ Important Warning (System Health)

* **Schedule:** While `RSS Feed Trigger` can be set as low as `1 minute`, we highly recommend no less than **`5 minutes`** to avoid the risk of *Rate Limiting* from TechCrunch.
* **Data Handling:** This *workflow* relies on a careful expression (`$('NodeName').item.json.field`) to merge data. Make sure the node name *isn't* changed after you set it in the expression.

---

## 📝 License

This project is licensed under the terms of the **MIT License**.
