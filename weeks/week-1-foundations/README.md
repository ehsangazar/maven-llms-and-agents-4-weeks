# Week 1 · Foundations
**Oct 5 – 11 · S1 Tue Oct 6 · S2 Thu Oct 8**

Why demos die in production, and how to tell when a task actually needs an
agent. Then the one decision that shapes everything after it: what the model
should never touch.

| # | Code | What it is |
|---|------|-----------|
| S1 | [`modules/01-workflows-and-agents/s01-why-demos-die`](../../modules/01-workflows-and-agents/s01-why-demos-die) | The demo that dies under real traffic, then the five workflow patterns, runnable |
| S2 | [`modules/01-workflows-and-agents/s02-code-model-boundary`](../../modules/01-workflows-and-agents/s02-code-model-boundary) | The deterministic/model boundary: one task as a workflow vs as an agent |
| Lab 1 | [`modules/01-workflows-and-agents/lab-workflow-router`](../../modules/01-workflows-and-agents/lab-workflow-router) | Classify, route to the cheapest capable tier, validate, fall back |

Run S1, then S2, then the lab. The lab starts with `npm test` and needs no API
key; the session scripts do call a real model.
