
# Google Maps Leads Generation n8n Workflow

This n8n workflow automates the process of generating leads from Google Maps based on business type and location, and saves them directly to a Google Sheet. It also sends an email notification upon completion.

## 🚀 Features

*   **Form-Triggered:** Initiates via a simple form requesting Business Type, City, Country, and Max Results.
*   **Data Validation:** Ensures all required inputs are provided before proceeding.
*   **Apify Integration:** Uses the Apify Google Maps Scraper (`compass~crawler-google-places`) to find businesses matching the criteria.
*   **Google Sheets CRM:** Automatically appends the scraped data (Name, Category, Address, City, Website, Phone, Rating) into a Google Sheet.
*   **Email Notifications:** Sends a confirmation email via Gmail once the leads are successfully added.

## 📋 Prerequisites

To run this workflow, you will need:
1.  [n8n](https://n8n.io/) installed and running.
2.  An **Apify Account** and an [Apify API Key](https://console.apify.com/account/integrations).
3.  A **Google Account** with:
    *   A Google Sheet created with the required headers (Name, Category Name, address, city, website, phone number, total score).
    *   OAuth2 credentials for Google Sheets and Gmail set up in n8n.

## 🛠️ Setup Instructions

1.  **Import the Workflow:**
    *   Open your n8n instance.
    *   Click on **Workflows** -> **Add Workflow**.
    *   Click the **Import from file** button and select the `Leads Generation Google Maps_github.json` file.

2.  **Configure Credentials:**
    *   **Apify:** Double-click the **HTTP Request** node. Replace `YOUR_APIFY_API_KEY` in the URL with your actual Apify API key.
    *   **Google Sheets:** Double-click the **CRM google Sheet** node. 
        *   Select or create your Google Sheets OAuth2 API credentials.
        *   Update the Document ID (`YOUR_GOOGLE_SHEET_ID`) with the ID of your Google Sheet.
    *   **Gmail:** Double-click the **Feedback** node.
        *   Select or create your Gmail OAuth2 credentials.
        *   Update the `sendTo` field from `YOUR_EMAIL@gmail.com` to your email address.

3.  **Activate:** 
    *   Activate the workflow using the toggle in the top right corner.
    *   Open the Webhook URL of the **On form submission** node to access the input form and start generating leads!

## ⚠️ Important Note

Please ensure you comply with Google Maps' Terms of Service and Apify's usage policies when scraping data.
