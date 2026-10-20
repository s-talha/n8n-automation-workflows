# Booking Confirmations and SMS Reminders

Calendly bookings update HubSpot, send a confirmation and schedule 24 hour and 1 hour SMS reminders; cancellations alert the team.

![Booking Confirmations and SMS Reminders](canvas.png)

## The problem

No shows waste agent time, and manual reminders are easy to forget.

## How it works

1. Calendly trigger fires on every new booking and normalizes the payload
2. The buyer is upserted in HubSpot and receives a confirmation email with the formatted date
3. Wait nodes resume the execution exactly 24 hours and 1 hour before the viewing to send Twilio SMS reminders
4. A second trigger handles cancellations: CRM status update plus a Slack alert with the reason

## Stack

n8n, Calendly, HubSpot, Gmail, Twilio, Slack

## Outcome

Fewer no shows and a CRM that always reflects the latest booking status.

## Import

1. In n8n, open **Workflows > Import from File** and select `workflow.json`.
2. Add your credentials to the nodes that show a warning.
3. Replace placeholder IDs (sheets, channels, databases, phone numbers) with your own.
4. Run once with test data, then activate.

Nodes: 11 | Built for n8n 1.x
