---
layout: post
---

AgentScape is an open and lightweight, registry for exposing and discovering AI agents. It is designed for use in proof-of-concept (PoC) and MVP-stage projects.

**API Base URL**: `https://api.agentscape.cc`

#### Search for Agents

Query agents by name, organization, or tag.

**GET `/agents`**

```bash
curl "https://api.agentscape.cc/agents?name=contoso"
```

Python:

```python
import requests

res = requests.get("https://api.agentscape.cc/agents", params={"name": "contoso"})
print(res.json())
```

#### Register an Agent Manually

**POST `/agents`**

```bash
curl -X POST https://api.agentscape.cc/agents \
  -H "Content-Type: application/json" \
  -d '{
    "name": "My Research Agent",
    "description": "Summarizes academic content using LLMs.",
    "endpoint": "https://myagent.org/api",
    "openapi_url": "https://myagent.org/openapi.json",
    "org_website": "https://myagent.org",
    "org_email": "team@myagent.org",
    "tags": ["nlp", "summarization", "research"]
  }'
```

#### API Reference

| Method | Endpoint                         | Description                        |
|--------|----------------------------------|------------------------------------|
| GET    | `/agents`                        | List or search agents              |
| GET    | `/agents/{id}`                   | Fetch details of a single agent    |
| POST   | `/agents`                        | Register an agent manually         |


#### Purpose and Scope

AgentScape is a minimal, open registry built to support:

- Experimental deployments of AI agents during PoC/MVP phases
- Projects using LLM-based or autonomous agents with public HTTP interfaces
- Open agent interoperability in research and early-stage development

It is not designed for production or security-critical use.


#### Intended Audience

This project is intended for:

- AI researchers building or evaluating autonomous agents
- Developers integrating with agent orchestration frameworks (e.g. LangChain, AutoGen)
- Teams piloting multi-agent systems and looking for simple discovery tools

#### Open Source Code

AgentScape is open source and available on GitHub: [https://github.com/ScaleUpLabs/agentscape](https://github.com/ScaleUpLabs/agentscape)

#### Contact

For collaboration or support, contact: [marco.cello@scaleuplabs.vc](mailto:marco.cello@scaleuplabs.vc)
