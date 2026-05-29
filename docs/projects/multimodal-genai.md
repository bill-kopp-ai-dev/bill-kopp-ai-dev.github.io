# 🎨 Multimodal & GenAI Applications

!!! abstract "Multimodal Portfolio Overview"
    In this section, I present the development of complete *Full Cycle* applications that orchestrate different Generative Artificial Intelligence foundational models. The focus of these projects is the seamless integration between **Backend Engineering**, **User Interfaces (Frontend)**, and **Multimodal AI** (unified processing of text, audio, image, and video), ensuring functional, scalable products with excellent *Developer/User Experience*.

    In these projects, I worked on the entire product development lifecycle (End-to-End), from architectural conception to production deployment. The backend infrastructure was developed in Python, orchestrating multiple inference providers. The data architecture transitions from TinyDB (for agile local testing) to Firebase Firestore (NoSQL architecture in production). *Deployment* was performed using a *Serverless* and containerized approach via Docker on Google Cloud Run, with microservices exposed and protected centrally by the GCP API Gateway. On the frontend, I used the FlutterFlow (Low-Code) framework boosted with custom functions and actions in Dart, ensuring robust integration via secure API calls.

---

## 🚀 Jarvis.ai: Complete Personal Assistant

[![Access Project](https://img.shields.io/badge/Live_Demo-jarvis--ai.tech-blue?style=flat&logo=googlechrome)](https://jarvis-ai.tech/)

**Jarvis.ai** represents my first major AI project built entirely end-to-end (2023-2024). It is not just a terminal script, but a complete web and mobile application that demonstrates mastery over the software development lifecycle (*SDLC*).

The architectural goal was to integrate GPT series models into conversational flows via WhatsApp. The platform orchestrated audio and image generation capabilities, introducing a **Personas** system, allowing users to interact with customized agents from a dynamic catalog.

### Architecture and *Full Cycle Engineering*
Building Jarvis.ai required the union of critical software engineering disciplines:

* **Backend Development & Infrastructure:** The service was built as a containerized monolith on GCP Cloud Run, exposed via *webhook* to the WhapiCloud API service (gateway for WhatsApp communication).
* **Frontend Development:** Design and implementation of a web interface for account management (*SaaS Dashboard*), created in FlutterFlow (including the Landing Page). In the panel, the user manages plans, monitors image tokens, and API call telemetry.
* **Financial and Data Integration:** Monetization was established through the creation of Python *webhooks* for integration with the **Stripe** API. Data persistence (conversation history and customer data) was orchestrated in Firebase Firestore.

!!! tip "Product Lifecycle and Market Agility"
    The application achieved excellent initial technical validation. However, demonstrating a mature view of *Product Lifecycle*, the service was strategically discontinued after the launch of competing native solutions by Meta and OpenAI. This experience consolidated valuable technical experience in rapid launches (*Go-to-Market*), *webhooks*-based event architecture, and agile competitor monitoring in scenarios dominated by *Big Techs*.

---

## 🌌 Wonderful Companion: The Next Level of Orchestration

[![Access Project](https://img.shields.io/badge/Live_Demo-wonderful--companion.me-purple?style=flat&logo=googlechrome)](https://wonderful-companion.me/)

!!! warning "Content Notice"
    *This project operates in a market niche that includes support for NSFW (Not Safe For Work) content, requiring specific architectural solutions for high-risk compliance infrastructures.*

If Jarvis.ai was the *Full Cycle* foundation, **Wonderful Companion** (2024-2025) is the crucible test in **Multimodal AI** orchestration. This is an AI-based companionship platform of the highest architectural complexity, transitioning from the monolithic model to a robust **Microservices** architecture.

For this project, I developed multiple microservices deployed on Cloud Run and exposed via GCP API Gateway, isolating critical domains:
* Dedicated Inference Engines: **Text Generation**, **Image Synthesis**, and **Video Generation**.
* State Management: Independent services for **Database** and **Memory System**.
* Domain Logic (*Game Logic*): Management of different "Game Worlds" and the "Character Creation" engine.
* Complex Payment Gateways: Dual integration via webhooks and APIs with **Stripe** (fiat) and **Moonpay Commerce** (cryptocurrencies).

The *Frontend* scaled to a massive *WebApp* with over 70 responsive screens in FlutterFlow, communicating exclusively securely with the *backend*.

### The Multimodal Orchestration Challenge
Unlike purely text-based applications, the project handles multiple heavy data streams simultaneously:

=== "Text Generation"
    Use of advanced LLMs to maintain coherence, consistent personality, and deep contextual memory during long interactions, generating immersive narratives and organic dialogues.

=== "Image Synthesis"
    Integration with *Diffusion Models* to generate contextual images on demand, requiring extreme refinement in the programmatic construction of visual *prompts* to ensure aesthetic consistency.

=== "Video Generation"
    The most complex frontier of current Generative AI. Orchestration involves passing state between text, base image, and the video generation engine, controlling latency and temporal coherence.

### Engineering Behind the Experience
* **Asynchronous Processing:** Management of heavy *queues* for video and image generation without blocking the textual conversation *Event Loop*.
* **FinOps (Cost Optimization):** Smart routing to balance cheaper models for routine *chat* and more expensive models for multimedia generation.

!!! success "Engineering Challenges vs. Distribution (GTM)"
    Architecturally, the platform is a success in stability and complex state management. The main bottleneck faced was in user acquisition (*Marketing*), due to severe restrictions from ad platforms for the niche of operation. This provided S-level learning about *high-risk* payment infrastructure management (hence the adoption of cryptocurrencies) and *compliance* barriers in product launches. The project remains active as an extreme technical showcase of scalability and interconnected system design.