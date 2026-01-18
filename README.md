# Coaches Cold Outreach Workflow

This n8n workflow automates the entire process of finding and reaching out to potential leads in the coaching industry. It integrates Instagram scraping, email verification, data logging, and automated email campaign enrollment.

## 🚀 Features

- **Automated Scraping:** Uses the **Apify Instagram Email Scraper** to find leads based on custom keywords (e.g., coaching, business coach).
- **Lead Cleaning:** Automatically removes duplicate entries to ensure a clean database.
- **Email Verification:** Integrates with a third-party API (`verify-email.app`) to validate lead emails before outreach.
- **Data Persistence:** Automatically appends lead details (Account, Name, Email, Biography) to a designated **Google Sheet**.
- **Automated Outreach:** Syncs verified leads directly into an **Instantly.ai** campaign for cold email sequences.
- **Smart Formatting:** Uses JavaScript to extract and format first and last names from raw Instagram profile titles.

## 🛠️ Prerequisites

To use this workflow, you will need:
- An **n8n** instance.
- **Apify API Key** (for Instagram scraping).
- **Google Sheets OAuth2** credentials.
- **Instantly.ai API Key** (for outreach campaigns).
- **Verify-Email.app API Key** (for email validation).

## ⚙️ How It Works

1.  **Trigger:** The workflow starts via a **Webhook** receiving `instagramKeywords`.
2.  **Scrape:** The **Apify node** searches Instagram for profiles matching those keywords.
3.  **Validate:** The system filters for unique leads and uses an **HTTP Request** node to verify each email address.
4.  **Process:** A **Code node** cleans up the profile data, separating names and handles.
5.  **Store & Sync:**
    - Verified leads are added to the "Automated cold outreach" Google Sheet.
    - Leads are simultaneously added to the specified Instantly campaign.

## 📦 Installation

1. Download the `coaches cold outreach workflow.json` file.
2. Open your n8n dashboard and click on **Import from File**.
3. Configure the credentials for:
   - Apify
   - Google Sheets
   - Instantly
   - HTTP Request (Verify-Email.app)
4. Update the **Google Sheet ID** and **Instantly Campaign ID** in their respective nodes.
