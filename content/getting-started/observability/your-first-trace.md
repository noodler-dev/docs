+++
title = 'Your First Trace'
date = 2026-01-18T17:35:24-05:00
lastmod = 2026-01-18T17:35:24-05:00
draft = false
description = ''
keywords = []
linktitle = ''
weight = 20
+++

To send traces to Noodler, [install the SDK](/getting-started/install-sdk/) and *instrument* your OpenAI client. Once instrumented, Noodler will automatically capture model calls as traces.

## Prerequisites

You’ll need:

1. A running (self-hosted) Noodler instance
2. The Noodler Python SDK installed in your environment

## Instrumenting Your Application

Instrumentation means adding a small hook so your application emits tracing data that Noodler can receive and store.

In practice, it’s just a few lines of code:

```python
from noodler import setup, instrument_openai
from openai import OpenAI

# Connect to the Noodler server
setup(
    base_url="http://localhost:8000",
    api_key="noodler-api-key",
)

# Create and instrument OpenAI client
client = OpenAI()
wrapped_client = instrument_openai(client)

# Responses will be automatically logged
response = wrapped_client.chat.completions.create(
    model="gpt-4.1",
    messages=[
        {"role": "user", "content": "What is the capital of France?"}
    ],
)
```

## What you should see

After this runs, you should see a new trace in Noodler containing spans for the OpenAI request and response (including metadata like timing, tokens, and cost, if available).
