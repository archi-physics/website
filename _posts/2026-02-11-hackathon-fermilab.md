---
layout: post
title: "Archi Hackathon at Fermilab"
date: 2026-02-11
author: Luca Lavezzo
image: /assets/images/news/hackathon-group.jpg
---

The recent [Large Language Model Hackathon](https://indico.cern.ch/event/1623577) at the LHC Physics Center (LPC) at Fermilab brought together physicists and computer scientists from across the CMS experiment to hack away at building agents for use in the Collaboration.

![Team at Fermilab](/assets/images/news/hackathon-group.jpg)

Ideas are abundant as AI-enabled agents promise to affect all branches of high-energy physics: from accelerating experimental design, to automating experiments, to running agentic workflows for analyses. The challenge ahead is to master these emerging tools, and integrating them in our workflows, while maintaining the high level of rigor we already demand of our work.

The [Archi](https://github.com/archi-physics) framework has sought to provide a basis for the development of agents at CMS, by implementing an end-to-end modular pipeline for data collection and running of agents, tuned for high-energy physics use-cases.

The hackathon was maybe the last straw for the A2rchi team to rebrand and get rid of the much disputed '2' in the name, to the leaner "Archi". Together with the rebranding came a suite of new features: a fully agentic pipeline (LLMs can freely interact with tools through a [ReAct loop](https://arxiv.org/abs/2210.03629)), a cleaner, more interactive UI, and a complete re-write of the backend storage to [Postgres](https://en.wikipedia.org/wiki/PostgreSQL).

The hackathon saw several new and old deployments of Archi come together to collaborate:

- **CompOps**: an assistant for engineers working in computing operations
- **WisDQM**: an assistant for DQM shifters
- **Heavy-ions agent**: for expert analysis support
- **CRAB-expert**: for analysis support

The Computing Operations deployment is already in a prototype-mode for operators at CMS, and a more general release is planned for later in the month.

Many ideas came together as hackers discussed current issues and wish-lists. Many new features were developed over the week, including: a new document-uploader, a database UI, live-data tools for Rucio, roles for users, sandboxed code execution, and a more robust CI with benchmarking against previous releases.

![Hackers at Fermilab facilities](/assets/images/news/hackathon-collage.png)

The hacking was set to the backdrop of the beautiful Wilson Hall at Fermilab, where we were kindly hosted by the LPC. The hackathon can be concluded a success, as the team met each other in person for the first time, much work was done during the week, and we laid the work ahead for the next couple of months.

*Originally published on the [MIT PPC blog](https://ppc.mit.edu/blog/2026/02/11/archi-hackathon-at-the-lpcfnal/).*
