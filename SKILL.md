# SKILL.md
### GhostFrog Capability Playbooks

**Skill: Ghost-Driven Asset Generation**
* **Goal**: Generate $0-cost high-fidelity media using the Paid Gemini App.
* **Logic**:
    1. Initialize Playwright using the `persistent_chrome` profile.
    2. Input the script-prompt to generate **Veo** video or **Lyria 3** music.
    3. Monitor DOM for the "Download" button; retry once if UI shifts.
    4. Save to `./assets/staging/` and log to `video_metadata` in Postgres.

**Skill: Automated Hook Verification**
* **Goal**: Ensure the first 3 seconds of the script meet "Retention Scoring" (must be a question or a shocking stat).