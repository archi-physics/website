---
layout: post
title: "Archi presented at CERN EP-IT Data Science Seminar"
date: 2026-03-17
author: Jason Mohoney
excerpt: "Jason Mohoney presented 'Agents for Scientific Computing' at the CERN EP-IT Data Science Seminar, covering Archi's deployment in CMS Computing Operations, privacy architecture, and the roadmap toward active automation."
image: /assets/images/archi-architecture.png
---

Jason Mohoney (MIT CSAIL) presented *Agents for Scientific Computing* at the [CERN EP-IT Data Science Seminar](https://indico.cern.ch/event/1659399/) on March 17, 2026.

The talk covered the mechanics of AI agents — retrieval, tool use, and orchestration — and argued that their immediate value in scientific computing lies in low-risk tasks like documentation search, code generation, and debugging, rather than full automation.

## Archi in CMS Computing Operations

Archi is deployed as a prototype assistant for CMS Computing Operations, where operational knowledge is scattered across wikis, JIRA tickets, Redmine, and runbooks. The system ingests these sources into a Postgres-backed vector store and uses a [ReAct](https://arxiv.org/abs/2210.03629)-style agent loop to retrieve context and answer operator questions with cited sources.

![Archi architecture](/assets/images/archi-architecture.png)

The deployment follows CERN's data privacy guidelines: personal identifiers are stripped via an anonymization pipeline, models run through CERN LiteLLM or OpenAI with data collection opt-out, and the system supports access control and local model hosting.

## Usage and feedback

Early usage data from the Grafana dashboard shows response times and conversation volumes. User feedback identified areas for improvement — retrieval bugs when users paste JIRA links, missing capabilities like web search, and edge cases in data anonymization — all of which are being addressed in subsequent releases.

![Archi Grafana dashboard](/assets/images/news/archi-grafana.png)

## What's next

The talk outlined two directions under active development: automating routine operations tasks (ticket triage, root-cause analysis) and building a cooperative agent for HEP physics analysis that augments coding agents with domain-specific knowledge from Archi.

- [Slides](https://indico.cern.ch/event/1659399/attachments/3241100/5781202/Agents%20for%20Scientific%20Computing-7.pdf)
- [Recording](https://videos.cern.ch/record/3023647)
- [Event page](https://indico.cern.ch/event/1659399/)
- [All talks →](/talks/)
