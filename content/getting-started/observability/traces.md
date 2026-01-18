+++
title = 'What are Traces?'
date = 2026-01-18T17:29:50-05:00
lastmod = 2026-01-18T17:29:50-05:00
draft = false
description = ''
keywords = []
linktitle = ''
weight = 10
+++

Noodler’s observability is built on two ideas: **traces** and **spans**.

A **trace** represents a single interaction with your AI system, from start to finish.

A **span** represents one step that happens during that interaction.

## A Simple Example

Imagine a user asks an AI a question:

> **User**: What is the capital of Guyana?

> **AI**: The capital is Georgetown.

Even though this looks like a single exchange, multiple things happen behind the scenes.

In Noodler, we break this interaction into **spans**, such as:

1. Receiving the user’s input
2. Generating a response with the model

Each span captures useful details about that step — like how long it took, how many tokens were used, or how much it cost.

All of these spans are grouped together into a single **trace**, which represents the full interaction.

## Why Traces Matter

Traces let you see how an AI interaction actually unfolds.

Instead of guessing why a response was slow, expensive, or incorrect, you can see each step that led to it — in order, with context.

If you want to improve an AI system, traces show you where to look.

## OpenTelemetry

Noodler uses [OpenTelemetry](https://opentelemetry.io/) and adheres to its tracing model.

This means traces and spans in Noodler follow an industry standard, making your observability data portable and interoperable with the broader ecosystem.

