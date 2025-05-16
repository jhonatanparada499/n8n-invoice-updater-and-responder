# Report Generator & Invoice Auto-Responder (n8n)

The purpose of this self-hosted [n8n](https://n8n.io) automation workflow is to use Gmail to check for incoming emails - Use OpenAI (ChatGPT) to extract and process work log entries - Update a Google Sheet with formatted invoice data - Use Google Drive to create a PDF report - Automatically send the final invoice PDF to the sender

## Services Employed

- [OpenAI API](https://platform.openai.com/)
- [Google Cloud Gmail API](https://console.cloud.google.com/)
- [Google Sheets API](https://developers.google.com/sheets)
- [Google Drive API](https://developers.google.com/drive)

## How It Operates

1. When a new email that meets your criteria arrives, the **Gmail Trigger** is activated.
2. **OpenAI Node**: Transforms email content into structured JSON invoice entries by sending it to GPT-4.1-NANO with a predefined configuration prompt.
3. **Clear + Update in Google Sheets**: Clears out an invoice template in Google Drive before updating it with new parsed data entries.
4. **Google Drive (Download)**: Gets a Google Sheet formatted to PDF sent to the the recipient that meeets your criteria.

## Set up Required Credentials

- OpenAI API Key
- Google Sheets, Drive, and Gmail (OAuth2 or App Passwords)

## Replace the following in the workflow:

- Google Sheet ID (in Sheets node)
- Gmail “To” and “From” fields (in Send and trigger nodes)

## Notes
- This workflow runs fully on a self-hosted n8n instance.
