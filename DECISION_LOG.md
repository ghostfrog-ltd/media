# DECISION_LOG.md
### Architectural Memory

* **[2026-03-28] Decision: Project GhostFrog Named**:
    - **Why**: To separate personal branding from automated orchestration.
* **[2026-03-28] Decision: Ghost-Driver vs. API**:
    - **Decision**: Use Playwright to drive the Web UI instead of the Vertex AI API.
    - **Why**: Saves ~$400/mo in video/image generation tokens by leveraging the existing $20 consumer sub.