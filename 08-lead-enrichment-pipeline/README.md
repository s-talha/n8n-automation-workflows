# B2B Lead Enrichment and Scoring Pipeline

Daily pipeline that finds decision makers for target accounts, scores them against an ICP, de duplicates and syncs qualified contacts to HubSpot.

![B2B Lead Enrichment and Scoring Pipeline](canvas.png)

## The problem

Sales reps waste hours researching contacts and the CRM fills up with duplicates and poor fit leads.

## How it works

1. Weekday cron reads new target accounts from Google Sheets
2. Apollo people search finds senior decision makers per domain with rate limited batching
3. A transparent JavaScript scoring model rates seniority, company size, region and email status
4. Only contacts scoring 60 or more pass; duplicates by email are removed
5. Contacts are upserted to HubSpot and a summary is posted to Slack

## Stack

n8n, Apollo API, Google Sheets, HubSpot, Slack, JavaScript

## Outcome

Reps start each day with a short list of verified, high fit contacts already in the CRM.

## Import

1. In n8n, open **Workflows > Import from File** and select `workflow.json`.
2. Add your credentials to the nodes that show a warning.
3. Replace placeholder IDs (sheets, channels, databases, phone numbers) with your own.
4. Run once with test data, then activate.

Nodes: 10 | Built for n8n 1.x
