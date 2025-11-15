# 🤖 n8n Workflows Collection

This collection houses various automation projects built using n8n, where each subfolder represents a *workflow* that can be imported directly into your *n8n instance*. These projects are designed to manage data, integrate AI, and distribute information across multiple services.

## 📁 Repository Structure

Each project folder is designed for ease of management and maintenance, containing the critical files below:

| File/Folder | Description |
| :--- | :--- |
| `workflow.json` | The main importable n8n *workflow* export file. |
| `README.md` | Project-specific guides, feature lists, and credential installation instructions. |
| `screenshots/` | Contains workflow diagrams and example *output*. |
| `notes.md` | Development notes, node versions, or any *troubleshooting* needed. |

-----

## 🚀 Available Projects

Here is a list of *workflows* included in this collection. For more details, please refer to the `README.md` file in each subfolder.

### 1\. [TechCrunch Feed Distributor](https://github.com/fyyqq/n8n-workflows/tree/main/TechCrunch%20Feed%20Distributor)

* **Description:** Main project that emulates TechCrunch Feed Distributor. Responsible for ingesting RSS feeds, performing AI analysis (summary & sentiment), and large-scale data management (cleaning, archiving, and distribution).
* **Key Features:** Bilingual AI Integration (EN/BM Summaries & Sentiment), Duplicate Prevention, Advanced Error Handling, and Multi-Channel Distribution (Telegram/Discord).
* **Status:** Active, requires Google Gemini and Google Sheets credentials.

-----

## 🛠️ How to Use

1. **Clone Repository:** Copy (clone) this repository to your computer or N8N server.
2. **Import File:** Open your *N8N instance*. Go to each project folder (e.g. `techCrunch-feed-distributor/`) and import the **`workflow.json`** file into N8N.
3. **Connect Credentials:** Once imported, make sure you connect the correct credentials (Google Sheets, Gemini, Telegram, etc.) to the relevant node.
4. **Activate:** Press the **`Active`** button to start automation.

-----

## 📝 License

The contents of this repository are shared under the **MIT License**.
