# Support-Ticket-Router
The Support Ticket Router is an automation workflow built using n8n. It automatically routes incoming support tickets based on their urgency.
High Priority → Sends an instant notification to a Slack channel.
Normal Priority → Logs the ticket into Google Sheets for later review.
This project reduces manual work and ensures urgent issues receive immediate attention.
🚀 Features
Accepts support tickets through a Webhook.
Checks ticket urgency using an IF node.
Sends high-priority alerts to Slack.
Stores normal-priority tickets in Google Sheets.
Easy to customize and extend.
🛠️ Technologies Used
n8n
Slack Incoming Webhook
Google Sheets
Webhook Trigger
HTTP Request Node
IF Node
📂 Workflow
Webhook
    │
    ▼
IF (Urgency Check)
   │
   ├── High
   │      ▼
   │  Slack Notification
   │
   └── Normal
          ▼
     Google Sheets
📋 Input JSON
{
  "subject": "Server Down",
  "message": "Website is not responding",
  "urgency": "high"
}
or
{
  "subject": "Password Reset",
  "message": "User forgot password",
  "urgency": "normal"
}
📊 Output
High Priority
Slack receives an instant alert.
Normal Priority
A new row is added to Google Sheets containing:
Subject
Message
Urgency
Date
▶️ How to Run
Clone this repository.
Import the workflow JSON into n8n.
Connect your Google Sheets account.
Configure the Slack Incoming Webhook URL.
Execute the workflow.
Send a POST request to the Webhook URL with the required JSON.
Verify Slack notifications or Google Sheets entries.
📁 Project Structure
Support-Ticket-Router/
│
├── workflow.json
├── README.md
├── screenshots/
│   ├── workflow.png
🎯 Future Enhancements
Email notifications
Ticket priority levels (Low, Medium, High, Critical)
Database integration (MySQL/MongoDB)
Automatic ticket assignment
Dashboard for ticket monitoring
