# 📊 AI Data Analyst Agent (n8n Workflow)

An automated, agentic data pipeline built in n8n that acts as a digital Data Analyst. This workflow ingests raw or semi-structured business sales data, calculates key metrics, logs the structured data into a database, and automatically emails a visual dashboard report to stakeholders.

## 🚀 Features

* **Intelligent Data Parsing:** Utilizes Groq's LLM to read natural language or messy CSV data and extract relevant business entities.
* **Automated Data Processing:** Calculates total revenues, identifies top performers, and aggregates sales data autonomously.
* **Database Integration:** Formats and pushes the cleaned data directly into Google Sheets as structured rows.
* **Dynamic Visualization:** Uses custom JavaScript logic to group data and generate summary charts (Bar and Pie charts).
* **Automated Reporting:** Dispatches a beautifully formatted HTML email dashboard via Gmail, giving business owners instant insights.

## 🛠️ Tech Stack & Tools

* **Orchestration:** n8n (Node-based workflow automation)
* **AI/LLM:** Groq (Llama 3 model for high-speed data processing)
* **Database:** Google Sheets API
* **Delivery:** Gmail API
* **Custom Logic:** JavaScript (Data aggregation and charting)

## ⚙️ How It Works

1. **Input:** The user submits daily sales data via the n8n chat trigger (can easily be swapped for a Webhook to connect to external websites/apps).
2. **AI Processing:** The AI Agent, equipped with a strict system prompt and short-term memory, cleans the data and performs requested math operations.
3. **Database Write:** The structured output is routed to a Google Sheets node to append new rows.
4. **Data Aggregation:** A JavaScript node processes the new data, grouping it by salesperson to prepare for visualization.
5. **Dashboard Delivery:** An HTML email is constructed featuring the generated charts and top-line metrics, and sent directly to the client.

## 📦 Installation & Setup

To run this workflow on your own n8n instance:

1. Clone this repository or download the `.json` blueprint file.
2. Open your n8n workspace and click **Add Workflow**.
3. Go to the top right menu (`...`) and click **Import from File**, then select the downloaded `.json` file.
4. **Configure Credentials:** You will need to connect your own accounts to the following nodes:
   * Groq API Key
   * Google Sheets (OAuth2 or Service Account)
   * Gmail (OAuth2 or App Password)
5. **Set up the Google Sheet:** Ensure you have a target Google Sheet created with the exact column headers expected by the workflow (e.g., `Date`, `Salesperson`, `Items Sold`, `Price Per Item`, `Total Revenue`).
6. Activate the workflow and test via the Chat trigger!

## 💡 Future Enhancements

* Switch the Chat Trigger to a Webhook for SaaS integration.
* Add an error-handling path to alert admins if the data format is completely unrecognizable.
* Connect the Google Sheet directly to Power BI for live, interactive dashboards.

---
**Author:** Arun Jyoti Chakraborty
