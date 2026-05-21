---
title: "Distillation Guard"
collection: portfolio
---

This project won 3rd Place at the Personalized AI Agents Hackathon hosted by Lightning AI and Validia!

A real-time monitoring service that detects distillation attacks against codebase knowledge agents. Built on top of OpenClaw running a fictional NovaPay fintech engineering assistant ("Atlas").

Distillation attacks are prompts designed to extract a model's training data, system context, or capabilities — categorized using Validia's Distillery dataset (53,991 prompts across 7 attack categories).

How It Works
OpenClaw runs Atlas (the NovaPay codebase agent). Distillation Guard runs as a separate monitoring service that tails OpenClaw's session JSONL logs in real time — no proxy, no inline blocking, zero risk of breaking the agent.

Every user prompt is classified against 7 Distillery attack categories and scored using 5 behavioral signals per session. A live dashboard streams events in real time and dynamically filters the feed by selected session.

[Code Repository](https://github.com/savula13/distillation-guard)