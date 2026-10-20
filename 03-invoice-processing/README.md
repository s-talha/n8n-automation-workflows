# AI Invoice Processing and Approvals

Extracts structured data from PDF invoices with an LLM, routes large invoices for Slack approval and books bills in QuickBooks.

![AI Invoice Processing and Approvals](canvas.png)

## The problem

Finance teams retype invoice data by hand, chase approvals over email and lose track of what was booked.

## How it works

1. Gmail trigger picks up PDF invoices from a labeled inbox
2. Text is extracted from the PDF and parsed by Claude into a strict JSON schema (vendor, dates, VAT, totals, line items)
3. Invoices above 5,000 EUR are sent to Slack with approve and reject buttons using send and wait
4. Approved or small invoices become bills in QuickBooks; rejections notify accounts payable
5. Every invoice is appended to a Google Sheets ledger for audit

## Stack

n8n, Anthropic Claude, Gmail, Slack, QuickBooks, Google Sheets

## Outcome

Cuts manual entry to near zero and gives finance a single approval flow with a full audit trail.

## Import

1. In n8n, open **Workflows > Import from File** and select `workflow.json`.
2. Add your credentials to the nodes that show a warning.
3. Replace placeholder IDs (sheets, channels, databases, phone numbers) with your own.
4. Run once with test data, then activate.

Nodes: 12 | Built for n8n 1.x
