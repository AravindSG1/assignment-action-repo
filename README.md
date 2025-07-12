# 📦 action-repo
This is a dummy GitHub repository used to simulate and trigger webhook events such as:

PUSH

PULL_REQUEST

MERGE

These events are captured via a webhook and sent to a Flask-based receiver in the webhook-repo.

## 🔧 Purpose
This repository is used for triggering GitHub webhook events.

Each Git operation performed here (like pushing a commit or opening a pull request) will trigger a webhook configured in the repo settings.

## 📤 Webhook Setup
To simulate the events:

Go to Settings → Webhooks

Add a webhook with:  
**Note:** If you're testing this locally, make sure to expose your local Flask server using [ngrok](https://ngrok.com/) and use the generated URL.

Payload URL: `https://<your-ngrok-id>.ngrok.io/webhook/receiver`

Content type: application/json

Events: Select:

✅ Pushes

✅ Pull requests

✅ Merges (if implementing manually)

Ensure the Flask server in webhook-repo is running when triggering events.

## 🚀 How to Use
You can perform any of the following to trigger webhook calls:

Make a commit and push

Create a pull request

Merge a pull request

Each event will be sent to the webhook receiver and stored in MongoDB, then displayed in a simple frontend UI that polls every 15 seconds.

## 🧪 Example Git Actions

## Create and push a new branch
```
git checkout -b feature-push-check
echo. > demo.txt
git add demo.txt
git commit -m "Test push event"
git push origin feature-push-check
```

## Create a pull request via GitHub UI, then merge it

📎 Linked Repository  
This repo works with the webhook backend available at:  
👉 [webhook-repo](https://github.com/AravindSG1/assignment-webhook-repo)