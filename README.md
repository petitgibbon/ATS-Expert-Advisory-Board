# ATS-Council
A board of Advisers for ACR Growth based on a profile of leaders across Finance, Tech, Vision, Marketing and Innovation 

**The Concept: **
This project implements a Companion Agent Orchestrator that behaves like a lightweight “board of directors” for Account Technology Strategists, and offers alternate perspectives grounded in specialist contexts. 

- A single primary orchestrator acts as the entry point and delegates work to five specialist sub‑agents (directors), each optimized for a distinct lens (vision, narrative, engineering delivery, CFO value case, and compute/scale). 
- This orchestrator‑and‑subagent pattern is designed for modularity, reuse, and higher-quality outputs by letting each specialist focus on what they do best, while the orchestrator makes the “who should handle this?” routing decisions. 

Under the hood, it aligns to multi-agent orchestration patterns (e.g., concurrent, sequential, group chat, magentic, handoff) so you can choose parallel critique, step-by-step pipelines, or manager-led collaboration depending on the task. 

To keep Microsoft-specific guidance accurate and current, the system integrates the Microsoft Learn MCP Server, which provides trusted, up-to-date access to official Microsoft documentation through an MCP endpoint. Plans to further integrate WorkIQ MCP to include the conversations already had with customers in the outputs.

