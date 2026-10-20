# AI Support Inbox Agent (RAG + Tools)

An AI agent that answers support emails from a Pinecone knowledge base and live order data, with a confidence gate and human escalation.

![AI Support Inbox Agent (RAG + Tools)](canvas.png)

## The problem

Support teams spend most of their day answering the same delivery, refund and how to questions.

## How it works

1. Gmail trigger polls the support inbox; a filter drops auto replies and no reply senders
2. The agent keeps per thread memory so follow ups stay in context
3. It retrieves help center content from Pinecone (OpenAI embeddings) and looks up orders in Google Sheets as tools
4. A structured parser returns reply, confidence and a needs_human flag
5. Confident answers are sent as a reply in the same thread and labeled; everything else goes to Slack with a draft

## Stack

n8n, OpenAI, Pinecone, Gmail, Google Sheets, Slack, LangChain

## Outcome

Typically resolves 50 to 70 percent of tier 1 tickets automatically while keeping a human in the loop for edge cases.

## Import

1. In n8n, open **Workflows > Import from File** and select `workflow.json`.
2. Add your credentials to the nodes that show a warning.
3. Replace placeholder IDs (sheets, channels, databases, phone numbers) with your own.
4. Run once with test data, then activate.

Nodes: 14 | Built for n8n 1.x
