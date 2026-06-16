# Technical Writing & Docs Scheduling and Availability API

> Stop manually juggling calendars and email threads to schedule documentation reviews — your tech writing workflow deserves an API that automates availability and syncs slots across teams.

This REST API eliminates the friction of coordinating writing, editing, and approval slots for technical documentation. It handles timezone-aware availability checks, recurring slot generation, and real-time conflict detection, so your docs process runs without back-and-forth.

## What's Included

- Real-time availability sync with Google Calendar, Outlook, and iCal feeds
- Automated timezone conversion for distributed writing teams
- Recurring slot generation for weekly doc reviews or writer office hours
- Conflict detection that prevents double-booking critical review slots
- Simple REST endpoints for availability queries, slot booking, and cancellation

## Who Is This For

- Technical writing teams managing multi-document release cycles
- Freelance tech writers who need to show real-time availability to clients
- Documentation managers coordinating SME reviews across timezones
- Product teams integrating doc scheduling into their project management tools

## How It Works

Get your API key, then call the endpoints to define writer availability windows or book review slots. The API handles timezone mapping, returns free/busy data in JSON, and sends webhooks on booking confirmations — integrate it in minutes.

## Frequently Asked Questions

**Do I need to manage OAuth for calendar integrations?**
No, the API uses a simple API key. We handle calendar authentication on the backend — just provide the calendar feed URL.

**Can this API handle recurring availability slots (e.g., every Tuesday at 10 AM)?**
Yes, you can create recurring slot templates with start/end dates, frequency, and timezone rules.

**How does the API deal with overlapping time zones in a global team?**
Each availability query accepts an optional timezone parameter. The API automatically converts all slots to the requester's timezone for clarity.

**Is this API RESTful and easy to test?**
Absolutely. It follows REST conventions with JSON responses. We provide a Postman collection and interactive Swagger docs for quick testing.

**What happens if two people book the same slot simultaneously?**
The API uses optimistic concurrency with a timestamp lock — only the first confirmed booking succeeds, and the second request receives a conflict error.

## What You Get

- Instant digital download
- Complete REST API with full documentation
- Free updates for life — pay once, own forever
- Setup guide and usage instructions

**Get the Technical Writing & Docs Scheduling and Availability API now and eliminate scheduling friction from your documentation pipeline.**

## Features

- Full REST API

## Quick Start

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Configure environment
cp .env.example .env
# Edit .env with your settings

# 3. Run locally
uvicorn main:app --reload --port 8000

# 4. View interactive docs
open http://localhost:8000/docs
```

## Docker Deployment

```bash
# Build and run
docker compose up -d

# Check health
curl http://localhost:8000/health
```

## Authentication

Get a token first:
```bash
curl -X POST "http://localhost:8000/auth/token?username=admin&password=admin123"
```

Use the token in subsequent requests:
```bash
curl -H "Authorization: Bearer YOUR_TOKEN" http://localhost:8000/items
```

## API Endpoints

| Method | Path | Description |
|--------|------|-------------|
| GET | `/health` | System health |
| POST | `/auth/token` | Get JWT token |
| GET | `/items` | List all items |
| POST | `/items` | Create item |
| GET | `/items/{id}` | Get item |
| PATCH | `/items/{id}` | Update item |
| DELETE | `/items/{id}` | Delete item |
| GET | `/stats` | API statistics |

Full interactive docs: `http://localhost:8000/docs`

## Rate Limits

| Endpoint | Limit |
|----------|-------|
| `/auth/token` | 10/minute |
| `GET /items` | 60/minute |
| `POST /items` | 30/minute |
| `DELETE /items` | 20/minute |

## Running Tests

```bash
pip install pytest httpx
pytest tests/ -v
```

## Production Notes

- Change `SECRET_KEY` in `.env` before deploying
- Replace in-memory `_db` with a real database
- Add proper user management to `auth.py`
- Configure `ALLOWED_ORIGINS` for CORS
- Use Nginx/Traefik as reverse proxy

## License

MIT


---

## Free vs Pro

| Feature | Free | Pro |
|---------|:----:|:---:|
| 100 requests/day | Yes | Yes |
| Standard endpoints | Yes | Yes |
| JSON responses | Yes | Yes |
| Unlimited requests | - | Yes |
| Premium endpoints | - | Yes |
| Batch processing | - | Yes |
| Webhook notifications | - | Yes |
| SLA guarantee | - | Yes |
| Priority support | - | Yes |

### Upgrade to Pro

Get the full version with all premium features, priority support, and lifetime updates.

**[Get Pro Version](https://buy.stripe.com/8x25kD3aLbUE2hibzScZg3E)**

- [Buy Now (Stripe)](https://buy.stripe.com/8x25kD3aLbUE2hibzScZg3E)

