# Production-Ready Systems with LLMs and Agents, labs · 4-week cohort

Companion code for the four-week cut of the course:
**[hub.gazar.dev/llms-and-agents-4-weeks](https://hub.gazar.dev/llms-and-agents-4-weeks/)**
(Oct 5 – Nov 1, 2026 · 8 live sessions · 3 artifacts).

Looking for the six-week cohort? Its repo is
[`maven-llms-and-agents-6-weeks`](https://github.com/ehsangazar/maven-llms-and-agents-6-weeks).
**The lab code in the two repos is the same.** Only the schedule differs: this
repo groups the same six labs into four weeks instead of six.

> **These are reference implementations of *patterns*, not a prescribed stack.**
> The course teaches architecture decisions that hold regardless of language or
> vendor. This repo happens to use TypeScript + OpenRouter so the patterns are
> runnable and concrete. Everything that touches a vendor lives behind one file
> (`common/llm.ts`); swap it and the labs still teach the same thing.

## How this repo is organised

Code is filed by **module**, mirroring the lesson slugs, exactly as in the
six-week repo. `weeks/` is the four-week reading order on top of it: one folder
per week, each README listing that week's sessions, labs and deadlines.

```
common/llm.ts     the only vendor seam
modules/          the code, one folder per lesson
weeks/            the 4-week schedule, pointing into modules/
  week-1-foundations/
  week-2-context-retrieval/
  week-3-architecture-cost-security/   <- the compressed week
  week-4-evals-capstone/
```

## The four weeks

| Week | Dates | Sessions | Labs | Due |
|------|-------|----------|------|-----|
| [1 · Foundations](weeks/week-1-foundations) | Oct 5 – 11 | S1 Tue 6th · S2 Thu 8th | Lab 1 workflow router | |
| [2 · Context & retrieval](weeks/week-2-context-retrieval) | Oct 12 – 18 | S3 Tue 13th · S4 Thu 15th | Lab 2 hybrid RAG | P1 Wed 14th |
| [3 · Architecture, cost & security](weeks/week-3-architecture-cost-security) | Oct 19 – 25 | S5 Tue 20th · S6 Thu 22nd | Lab 3 budget/cache/fallback · Lab 4 guardrailed agent | P2 Wed 21st |
| [4 · Prove it, then defend it](weeks/week-4-evals-capstone) | Oct 26 – Nov 1 | S7 Tue 27th · S8 Thu 29th | Lab 5 eval harness · Lab 6 capstone | P3 Wed 28th |

Week 3 is the compressed one: the six-week cohort splits cost/latency and agent
architecture across two weeks. Nothing is dropped, they are taught together,
because choosing an agent pattern without pricing it is not a real choice.

## Setup

```bash
npm install
cp .env.example .env    # add your OPENROUTER_API_KEY
```

## Running a lesson companion or a lab

Both run the same way:

```bash
npm run lab modules/01-workflows-and-agents/lab-workflow-router/starter/index.ts
```

### The tests are the brief

```bash
npm test
```

**These fail on a fresh clone. That is the point.** A lab's test file is its
spec: it describes exactly what your implementation must do, and you are done
when it is green. Read the test before you write any code.

The tests need no API key and make no network calls. Every lab injects its model
access, so the parts worth testing (which route was taken, what happens when a
tier fails, what it cost) are deterministic. If you cannot test your routing
without calling a model, the seam is in the wrong place. That is a lesson, not a
limitation.

## What is scaffolded today

**Module 1 is complete.** Both lesson companions are fully worked and runnable,
and `lab-workflow-router` ships a starter, a worked solution and its full test
suite. It is the reference for how all of this looks in code.

**Labs 2 to 6 are specified, not scaffolded.** Each has a README describing what
you build, and the corresponding course lesson carries the steps, the acceptance
criteria and the code shape. Build them in your own codebase against that spec,
or wait for the starter to land here.

The lesson companions for modules 2 to 6 hold notes and small runnable snippets
rather than complete worked examples.

The course copy says exactly this, and the two are kept in step. If that stops
being true, the course is the thing to fix.
