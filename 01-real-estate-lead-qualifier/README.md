# AI Real Estate Lead Qualifier

Scores inbound property leads with an AI agent and routes hot, warm and cold leads to the right follow up automatically.

![AI Real Estate Lead Qualifier](canvas.png)

## The problem

Agents lose deals when new leads wait hours for a reply, and they waste time on low intent enquiries.

## How it works

1. Webhook receives leads from the website form or property portals and replies 200 immediately
2. Lead data is normalized (email casing, budget as a number, source tagging)
3. An AI agent scores intent, budget and timeline, and can look up the referenced listing through an HTTP tool
4. A structured output parser guarantees a clean JSON result (score, tier, summary, first message)
5. Hot leads create a HubSpot deal, alert the team in Slack and get an SMS within seconds
6. Warm leads are upserted in HubSpot and receive a personalized nurture email; cold leads are logged to Sheets

## Stack

n8n, OpenAI, HubSpot, Slack, Twilio, Gmail, Google Sheets, Webhooks

## Outcome

Speed to lead drops from hours to under 30 seconds, and agents only spend time on qualified buyers.

## Import

1. In n8n, open **Workflows > Import from File** and select `workflow.json`.
2. Add your credentials to the nodes that show a warning.
3. Replace placeholder IDs (sheets, channels, databases, phone numbers) with your own.
4. Run once with test data, then activate.

Nodes: 14 | Built for n8n 1.x
