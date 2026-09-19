# Python Automation & API Integration

[English](README.md) · [简体中文](README.zh-CN.md)

I build Python tools for lead intake, invoice processing, and support teams. My work includes the input checks, review screens, and failure handling needed to make these workflows usable.

The three projects below are personal demonstrations using synthetic business data, not paid client work. Each runs locally and includes English and Chinese instructions, test results, and known limitations.

## [Lead-to-CRM Automation](https://github.com/myp81607-dot/lead-to-crm-automation)

For a team copying website inquiries into a contact list. A form submission becomes an assigned inquiry, a contact update, and a notification draft. Duplicate deliveries are recognized; missing information and uncertain writes stay visible for review. Completing an old inquiry does not overwrite newer contact details.

[See the current review flow — 20 seconds](https://github.com/myp81607-dot/lead-to-crm-automation/blob/main/docs/review-update.webm) · [Full walkthrough — 58 seconds](https://github.com/myp81607-dot/lead-to-crm-automation/blob/main/docs/demo.webm) · [Screenshot](assets/lead-to-crm.png). Recordings download via GitHub's **View raw** link.

The supplied workflow has run in n8n 2.39.8 against the local Python service and SQLite CRM, including scheduled retries. HubSpot and live AI remain unverified. Notifications are saved drafts.

## [PDF Invoice Reviewer](https://github.com/myp81607-dot/pdf-invoice-reviewer)

For an operations team preparing supplier invoices for a spreadsheet. Upload a text PDF, compare the extracted fields with their source, correct or reject problems, and export confirmed records as CSV. Edits and notes stay in a separate draft when you switch invoices; a stale browser tab cannot silently overwrite a newer saved record.

[60-second step-by-step demo](https://github.com/myp81607-dot/pdf-invoice-reviewer/blob/main/docs/demo.mp4) · [Review screen](assets/invoice-review.jpg) · [Try the sample invoices](https://github.com/myp81607-dot/pdf-invoice-reviewer#readme)

Tested with synthetic English text PDFs. Unfamiliar layouts may need manual completion; scans are unsupported. The repository reports extraction failures as well as the results after fixes.

## [Support Assistant with Citations](https://github.com/myp81607-dot/support-assistant-with-citations)

For a support agent looking up a product policy before replying. Search versioned documents, open the supporting passages, and leave a handoff when the information is missing or conflicting. Optional answer mode adds a short draft that an operator must check and approve before copying. Your own documents can be loaded from a small JSON file.

[35-second search and handoff demo](https://github.com/myp81607-dot/support-assistant-with-citations/blob/main/docs/demo.webm) · [Evidence screen](assets/support-evidence.jpg) · [Examples](https://github.com/myp81607-dot/support-assistant-with-citations#readme)

Search, document updates, handoff, and the approval rules have been tested. Default mode uses no model. The DeepSeek adapter and draft flow were tested with simulated responses; live model answer quality remains unverified.

## Starting a similar project

| Work we could scope | Useful materials to start with |
| --- | --- |
| Connect a form to a CRM, or repair an existing workflow | Sample input, target fields, and an authorized test environment |
| Review a defined set of supplier PDFs before CSV export | Sample documents, required fields, and validation rules |
| Add sources and human handoff to a support knowledge base | Documents you can use, example questions, and escalation conditions |
