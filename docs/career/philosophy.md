# 🧠 Engineering and Product Philosophy

!!! abstract "The Bridge Between Science and Software"
    Intelligence, consciousness, and the capacity for creation are the main differentiators of humans in relation to other species that inhabit our small sphere floating in the void. What if, suddenly, we could create an intelligence comparable to ours? Wouldn't this be the greatest invention of all? An invention that can invent.

    As a scientist who has transitioned between biotechnology and computing, when I first interacted with the GPT-3 model in late 2022, I was amazed. I knew, at first contact, that this was one of those fundamental technologies that would change human society. My first reaction as a scientist was to try to deconstruct and understand this new paradigm as much as possible. I have always believed that the best way to learn is by building.

    Today, I continue studying architectures, paradigms, and frameworks daily to master this technology that evolves at a dizzying pace. I believe that, now in mid-2026, the Artificial Intelligence ecosystem has reached an infrastructure maturity that allows us to build truly autonomous and useful tools for the real world.

    Changing focus at 40 years old, with an already consolidated scientific career, may seem unconventional to some. However, for a scientist driven by solving complex problems, there is nothing more exciting than working on the engineering of a creation that creates itself.

    *— Bill Kopp, May 2026*

---

## 🤖 My Vision on Agentic AI

In early 2026, I was introduced to **OpenClaw**, and I was immediately intrigued by the application's architecture and how a solo developer (Peter Steinberger) managed to orchestrate an AI agent with hundreds of thousands of lines of code in such a short time. Since then, I have been dissecting the architecture of OpenClaw and adjacent models (with a strong preference for **Nanobot**) to master the construction of personal, autonomous, and secure agents.

The immersion in Steinberger's highly efficient approach to agentic programming led me to formulate a clear personal vision about the future of human-computer interfaces and how a responsible AI assistant, one that respects user privacy and data sovereignty, should be architected. My research led me to the following architectural thesis:

> **In the very near future, we will stop producing computers focused on humans and start producing computers for AI Agents, which will operate them for the benefit of humans. The AI Agent will simultaneously be the operating system and the interface.**

In this context, I believe that:

!!! info "The New Paradigm"
    :computer: **AI Agents** will be the new **Operating Systems (OS)**

    :package: **MCP Servers** (Model Context Protocol) will be the new **Applications (Apps)**

    :cloud: Specialized agents orchestrated in the cloud (or at the edge) will be the new **SaaS (Software as a Service)**

---

!!! quote "The Product Mantra"
    *"The central mission of Artificial Intelligence should not be to replace people — but to empower them. AI should take on the operational cognitive load so that humans have the freedom to focus on what is strategic, creative, and essential, with the absolute certainty that the operating system is transparent, secure, and governable."*

---

## 🏛️ My Philosophy for Agentic Engineering

The true AI revolution is not in the *chatbot* format, but in **Assisted Autonomy**. Agentic systems (Agentic AI) fail quickly when built as overloaded monoliths with dozens of tools and instructions.

My approach to solving the limits of context windows and performance degradation is **Hierarchical Planning and Routing (LLM Routing)**. When building Multi-Agent ecosystems (such as my *Percival.OS* project and *Open CLI Agents*), I separate orchestrator reasoning from manual execution. This not only solves linear scaling problems but also implements rigorous FinOps control (API cost optimization).

Furthermore, system modularization facilitates *debugging*, fine-tuning, audits, and observability. When this modularization is done through **Docker** containers, we ensure process isolation, drastic reduction of the attack surface, and granular privilege management with controlled persistence on the host operating system.

My work at the intersection of Artificial Intelligence and *Software Engineering* is guided by three non-negotiable principles:

### 1. Governance and Traceability (*Quality Assurance*)
The greatest challenge in modern AI engineering is **controlling a probabilistic nature through deterministic code**. The reasoning engine (the LLM) is probabilistic; therefore, all the software (*wrapper*) that encapsulates it, providing context and action capability, must be strictly deterministic. This balances the system and endows the agent with reliability.

Untracked data is useless data. In AI, an autonomous decision without *audit logs* is an unacceptable compliance risk. My entire technical *stack* is oriented toward this paradigm — not for nothing did I choose the **PydanticAI** framework as the foundation for my architectures. Every MCP server or agent I develop has structured *logging*, strict data validation (strong typing), and total context traceability. The human in command must always have the ability to inspect why the model took a particular action.

### 2. Data Sovereignty (*Data Sovereignty & Privacy-First*)
The most valuable asset of a company or individual in the digital world is their information. AI adoption cannot, under any circumstances, come at the cost of privacy.
* **Edge Computing and Sandboxing:** I prioritize the execution of critical logic and PII (*Personally Identifiable Information*) handling in local infrastructures, isolated via Docker, or in properly fortified private cloud environments.
* **Context Sanitization:** Delegated agents (Workers) receive only the fraction of data strictly necessary to complete a task, ensured through *Untrusted Data Envelopes*.

### 3. *Security-First* and Architectural *Guardrails*
Giving an LLM the ability to execute arbitrary commands in the real world requires a *Defense-in-Depth* architecture. I implement natively:
* **Injection Prevention:** Shields against *Prompt Injection* and rigorous *Shell/Code Injection* blocking.
* **Principle of Least Privilege (PoLP):** Each tool operates with surgically restricted permissions (e.g., *Path Traversal* blocking, forcing the LLM to act exclusively within *sandbox* directories).

---

!!! tip "The Golden Rule of Agentic FinOps"
    *"Never give an AI agent control of your credit card. If you do, it will spend everything on tokens."* 🥲