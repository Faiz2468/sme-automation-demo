# SME Order Notification Automation

A free-tier, self-hosted automation demo simulating a small business's order notification pipeline — built entirely with zero-cost, no-card-required tools.

## Problem

Small e-commerce sellers and local businesses often handle order confirmations manually — checking a dashboard, copying details into a spreadsheet, and messaging the customer or team by hand. This is slow, error-prone, and doesn't scale even at small volume.

## Solution

An automated workflow built in [n8n](https://n8n.io) (open-source, self-hosted) that:
1. Triggers on a new order event
2. Fetches/receives the order data
3. Structures it into a consistent order record (order ID, customer, item, status)
4. Sends an instant notification via Telegram — simulating an owner or staff member being alerted the moment an order comes in

## Architecture
Trigger → HTTP Request → Edit Fields (structure order data) → Telegram

Entire stack runs in a single Docker container via `docker-compose`, requiring no cloud account, no credit card, and no paid service at any point.

## Screenshots

**Workflow running end-to-end:**
![Workflow canvas](screenshots/01-workflow-canvas.png)

**Live Telegram notification:**
![Telegram notification](screenshots/02-telegram-notification.png)

## Tech used

- **n8n** — open-source workflow automation, self-hosted
- **Docker / docker-compose** — containerized, reproducible environment
- **Telegram Bot API** — free notification channel

## Outcome

Reduces order-acknowledgment time from a manual, multi-minute process to instant — demonstrated via the workflow JSON in this repo.

## Running it yourself

```bash
git clone https://github.com/Faiz2468/sme-automation-demo.git
cd sme-automation-demo
docker compose up -d
```

Then open `http://localhost:5678`, import `n8n-sme-automation.json`, and configure your own Telegram bot credentials.

## Why this project

Built to demonstrate translating a real business problem into a working, deployed technical solution — using only free and open-source tools throughout.