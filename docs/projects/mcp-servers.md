# 🧰 MCP Servers Ecosystem (Model Context Protocol)

!!! info "Overview"
    Percival.OS expands its operational capabilities through an orchestrated network of **15 MCP (Model Context Protocol) servers**. Instead of creating a monolithic agent with dozens of coupled *skills*, I adopted a distributed architecture. Each server acts as a specialized microservice, providing low-level tools isolated by domain.

---

## 🛡️ Security Contracts (Security Posture)

Providing autonomy for LLMs to execute actions in the real world (such as reading emails or executing terminal commands) requires extreme rigor. All servers in this ecosystem were developed or refactored under the **Percival.OS Security Framework**:

* **FastMCP & Pydantic:** Rigorous validation of all input and output data.
* **Prompt Injection Shields:** Sanitization of malicious *inputs* before executing any *tool*.
* **Path Traversal Blocking:** Absolute restriction of read/write to *sandbox* directories (e.g., `/root/.nanobot/workspace`).
* **Untrusted Data Envelopes:** Data from the web or emails are enveloped so they cannot be interpreted as system commands by the LLM.

---

## 🏗️ Original Servers Catalog

Servers architected and developed from scratch to meet the privacy and data sovereignty requirements of the ecosystem.

### ✉️ Communication and Productivity

| Server | Description | Main Tools | Security & Privacy |
|----------|-----------|------------------|-------------------------|
| **`percival-agentmail-mcp`** | Provides the AI agent its own **autonomous email** via AgentMail API. (21 Tools) | `mail_send_email`, `mail_list_threads`, `mail_create_draft` | Context isolation: The agent has its own address, separate from the human user. |
| **`percival-imap-mcp`** | Secure management of the human user's email. | Automatic triage, spam deletion. | Controlled access via IMAP under supervision. |
| **`percival-khan-calendar-mcp`** | Local calendar operating via CLI (`khal`). No cloud dependency. (8 Tools) | `khan_create_event`, `khan_search_events`, `khan_view_agenda` | *Local-first*: Schedule data does not traverse the cloud. XML *tags* prevent calendar injections. |

### 🧠 Knowledge and Memory

| Server | Description | Main Tools | Security & Privacy |
|----------|-----------|------------------|-------------------------|
| **`percival-notes-mcp`** | Collaborative notes management and Wiki in Markdown + YAML Frontmatter. (12 Tools) | `notes_read`, `notes_search`, `notes_get_backlinks` | 100% local processing with strict *Path Traversal* blocking. Notes can be viewed using Obsidian |
| **`percival-internet-archive-mcp`** | Deep connection to the Internet Archive for media and public domain research. (6 Tools) | `archive_search`, `archive_download_file` | Downloads restricted to authorized directories by *Security Profiles* (dev, staging, prod). In this case, several orchestration skills were created to operate this set of tools |

### 👁️ Computer Vision and Generation

| Server | Description | Main Tools |
|----------|-----------|------------------|
| **`percival-vision-mcp`** | Grants visual capabilities to the agent by orchestrating 4 models (including GPT-4o Mini and Qwen3 VL E2EE). | `vision_describe`, `vision_read_text` (OCR), `vision_identify` |
| **`merlin-cv-mcp`** | *Edge* image processing via **OpenCV** and object detection via **YOLO**. | `cv_detect_objects`, `cv_detect_faces`, `cv_apply_filter` |
| **`percival-image-creator-mcp`** | Generation and manipulation suite. Supports 73 models (Default: `flux-2-pro`). | `image_generate`, `image_edit`, `image_get_metadata` |

---

## 🛠️ Refactored Servers (*Hardened Forks*)

Open source projects that were cloned, audited, and extensively refactored to meet the *Security-first* corporate standards of Percival.OS.

### 🐧 System Operations (The Most Critical)
**`percival-ubuntu-mcp` (10 Tools)** Security-focused server to allow the agent to perform operations in the underlying Ubuntu environment.
!!! success "Security Implementation"
    Has profile-based access policies (`secure`, `dev`), native *Shell Injection* blocking, rigid resource limits (CPU/RAM), and transparent audit logs for every executed command (`ubuntu_execute_command`, `ubuntu_read_file`).

### 🌍 Interaction with the External World
* **`percival-deep-research-mcp`:** Empowers the agent to perform complex multi-step web research (30-120s), synthesizing comprehensive reports in Markdown while maintaining source traceability (`research_get_sources`).
* **`percival-osm-mcp`:** Geospatial intelligence integration using OpenStreetMap (Nominatim/Overpass), with over 25 *tools* for Points of Interest (POIs) discovery and routing, without commercial tracking.
* **`percival-weather-mcp`:** Weather forecast telemetry, time zones, and air quality metrics.

---

## 🗄️ Long-Term Memory Integration

### **`mempalace-mcp`** (Custom Fork - 29 Tools)
The main long-term persistence engine (L2) of the ecosystem. Provides integrated vector storage and a *Knowledge Graph* for verbatim retention of contextual information.

!!! warning "Deprecation Notice (Google Workspace)"
    The old `google-workspace-mcp` was **deprecated** in the ecosystem due to recurring OAuth token expiration failures and *Data Sovereignty* limitations. It was fully replaced by *Local-first* solutions (`percival-imap-mcp` and `percival-khan-calendar-mcp`), demonstrating the mature evolution of the architecture towards stability and security.

---

## 📚 All MCP Servers Source Code

Below is the complete list of MCP servers that compose the Percival.OS ecosystem:

### 🏗️ Original Servers (Built from Scratch)

| Badge | Repository |
|-------|------------|
| [![percival-imap-mcp](https://img.shields.io/badge/percival--imap--mcp-009688?style=flat&logo=github)](https://github.com/bill-kopp-ai-dev/percival-imap-mcp) | percival-imap-mcp |
| [![merlin-cv-mcp](https://img.shields.io/badge/merlin--cv--mcp-009688?style=flat&logo=github)](https://github.com/bill-kopp-ai-dev/merlin_cv_mcp) | merlin-cv-mcp |
| [![percival-vision-mcp](https://img.shields.io/badge/percival--vision--mcp-009688?style=flat&logo=github)](https://github.com/bill-kopp-ai-dev/percival_vision_mcp) | percival-vision-mcp |
| [![percival-khan-calendar-mcp](https://img.shields.io/badge/percival--khan--calendar--mcp-009688?style=flat&logo=github)](https://github.com/bill-kopp-ai-dev/percival-khan-calendar) | percival-khan-calendar-mcp |
| [![percival-agentmail-mcp](https://img.shields.io/badge/percival--agentmail--mcp-009688?style=flat&logo=github)](https://github.com/bill-kopp-ai-dev/percival-agentmail-mcp) | percival-agentmail-mcp |
| [![percival-image-creator-mcp](https://img.shields.io/badge/percival--image--creator--mcp-009688?style=flat&logo=github)](https://github.com/bill-kopp-ai-dev/percival_image_creator_mcp) | percival-image-creator-mcp |
| [![percival-deep-research-mcp](https://img.shields.io/badge/percival--deep--research--mcp-009688?style=flat&logo=github)](https://github.com/bill-kopp-ai-dev/percival-deep-research) | percival-deep-research-mcp |
| [![percival-weather-mcp](https://img.shields.io/badge/percival--weather--mcp-009688?style=flat&logo=github)](https://github.com/bill-kopp-ai-dev/percival-weather-mcp) | percival-weather-mcp |
| [![percival-osm-mcp](https://img.shields.io/badge/percival--osm--mcp-009688?style=flat&logo=github)](https://github.com/bill-kopp-ai-dev/percival-osm) | percival-osm-mcp |
| [![percival-ubuntu-mcp](https://img.shields.io/badge/percival--ubuntu--mcp-009688?style=flat&logo=github)](https://github.com/bill-kopp-ai-dev/percival-ubuntu-mcp) | percival-ubuntu-mcp |
| [![percival-notes-mcp](https://img.shields.io/badge/percival--notes--mcp-009688?style=flat&logo=github)](https://github.com/bill-kopp-ai-dev/percival-notes-mcp) | percival-notes-mcp |
| [![percival-internetarchive-mcp](https://img.shields.io/badge/percival--internetarchive--mcp-009688?style=flat&logo=github)](https://github.com/bill-kopp-ai-dev/percival-internetarchive-mcp) | percival-internetarchive-mcp |

### 🔄 Third-Party Servers (Refactored/Integrated)

| Badge | Repository |
|-------|------------|
| [![mempalace](https://img.shields.io/badge/mempalace-6c5ce7?style=flat&logo=github)](https://github.com/bill-kopp-ai-dev/mempalace) | mempalace |
| [![google-workspace-mcp](https://img.shields.io/badge/google--workspace--mcp-636e72?style=flat&logo=github)](https://github.com/bill-kopp-ai-dev/google_workspace_mcp) | google-workspace-mcp |