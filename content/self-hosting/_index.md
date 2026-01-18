+++
title = 'Self-Hosting Noodler'
date = 2026-01-18T14:13:53-05:00
lastmod = 2026-01-18T14:13:53-05:00
draft = false
description = 'Self-host Noodler with Docker in minutes. Follow this step-by-step guide to install Noodler locally, run required services, and start collecting OpenTelemetry-based AI traces.'
keywords = ['self-hosting', 'docker']
linkTitle = 'Self-Hosting'
+++

## Prerequisites

You’ll need:

- [Docker](https://www.docker.com/) installed on your system

## Installing Noodler

Start by cloning the repository:

```bash
git clone https://github.com/noodler-dev/noodler.git
cd noodler
```

Then start the services with Docker Compose:

```bash
docker compose up -d
```

That’s it. Once the services are running, you can visit:

[http://localhost:8000/accounts/login](http://localhost:8000/accounts/login)

## Behind the Scenes

The Docker Compose setup starts a small set of services that work together:

- Django web server running at `http://localhost:8000`
- RabbitMQ message broker
    - Management UI available at `http://localhost:15672`
- Celery worker for background and asynchronous tasks

## Common Commands

Stop all running services:

```bash
docker compose down
```

Rebuild images and restart after code changes:

```bash
docker compose up -d --build
```

## Next Steps

- Create your first organization and project.
- Generate an API key.
- Start sending traces from your application.

