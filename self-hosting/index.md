---
title: Self-Hosting Noodler
blurb: Self-hosting Noodler can be done in as little as one command.
date: 2026-01-17
updated: 2026-01-17
---

# Self-Hosting Noodler

Self-hosting Noodler is can be done in as little as one command.

## Prerequisites

You will need to have [Docker](https://www.docker.com/) installed. 

## Installing Noodler

Start by cloning the repository:

```bash
git clone https://github.com/noodler-dev/noodler.git
cd noodler
```

Then run Docker compose:

```bash
docker compose up -d
```

And you're done! You should now be able to visit [http://localhost:8000/accounts/login](http://localhost:8000/accounts/login). 

## Behind the scenes

The Docker compose commands launches a few blocks that go together:

1. Django web server on `http://localhost:8000`.
2. RabbitMQ message broker (management UI at `http://localhost:15672`).
3. Celery worker for handling background tasks.

## Additional Commands

To stop all services:

```bash
docker compose down
```

To rebuild after code changes:

```bash
docker compose up -d -build
```

## Next Steps

TODO