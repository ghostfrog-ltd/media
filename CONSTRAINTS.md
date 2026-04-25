# CONSTRAINTS.md
### YouTube Automation Guardrails

## 🛑 1. The "Anti-Slop" Policy
* **Human-in-the-Loop**: Every script must have a [HUMAN_INPUT] tag where the Architect adds a 5-second personal insight to bypass YT's 2026 AI-originality filters.
* **Zero Repetition**: No two videos can use the same background music track within a 7-day window.

## 🕵️ 2. Stealth & Account Safety
* **Ghost Driver Pacing**: Random delays of 4-9 seconds between clicks in the Gemini Web UI to avoid bot detection.
* **Quota Cap**:
    - Veo (Video): Max 3/day.
    - Nano Banana (Images): Max 50/day.

## 💸 3. Financials
* **Hard Spend Limit**: $0.00 above the existing $20/month subscription.