e# n8n Workflows: AI contact form for my portfolio site

Two ready-to-import [n8n](https://n8n.io) workflows that power the contact form on my portfolio website. When someone sends a message, the workflow:

1. Receives the form through a **webhook**.
2. **Validates** it and filters out spam.
3. **Logs** the submission to Google Sheets.
4. Drafts a personal **AI reply**.
5. **Emails** the visitor the reply and sends me a notification.

| Workflow | AI model |
|---|---|
| `n8n/contact-form-workflow.json` | Claude Haiku (Anthropic API) |
| `n8n/contact-form-workflow-ollama.json` | A local model through Ollama: free and private |

## Use it

1. In n8n, go to **Workflows → Import from file** and pick one of the JSON files.
2. Connect your own Google Sheets, Gmail and Anthropic (or Ollama) credentials.
3. Replace `PASTE_YOUR_GOOGLE_SHEET_URL` with your sheet, and `YOUR_EMAIL@example.com` with the address that should get notifications.
4. Point your site's contact form at the workflow's webhook URL.

Run `python3 n8n/generate_test_data.py` to create sample submissions for testing the flow (the generated files are not committed).

No credentials are stored in this repo.
