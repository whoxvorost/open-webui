# Open WebUI Customization Task

## Setup

I cloned the Open WebUI repository and started the project locally using Docker.

Commands used:

```bash
git clone https://github.com/whoxvorost/open-webui.git
cd open-webui
docker compose up -d
```

The app runs on:

```bash
http://localhost:3000
```

---

## UI Changes

I made a few small UI changes to customize the interface.

Changes:

- Added a custom badge at the top center
- Changed the background color to dark gray
- Updated the layout styling
- Created a more internal-company style interface

Badge text:

```text
Freiheit Media • Local Test
```

---

## Files Changed

Main file edited:

```text
src/routes/(app)/+layout.svelte
```

Also used:

```text
docker-compose.yaml
```

---

# Part B — RAG Answer Quality

## System Prompt

```text
You are connected to one customer knowledge base.

Rules:
- Only answer using information from the active knowledge base.
- Do not guess or create missing information.
- If information is not available, say it clearly.
- Keep answers short and clear.
- Mention document names only if needed.
- Never use information from other customers.
```

---

## Example Questions

### Question 1 — Full Information

User Question:

```text
What is the onboarding process for new employees?
```

Model Answer:

```text
Based on the Onboarding Guide – 2024, new employees complete account setup, training, and team introduction during the first week.
```

---

### Question 2 — Partial Information

User Question:

```text
What are the remote work rules?
```

Model Answer:

```text
The knowledge base mentions remote work for some teams, but a full policy is not included.
```

---

### Question 3 — No Information

User Question:

```text
What is the company marketing budget for 2026?
```

Model Answer:

```text
This information is not available in the current knowledge base.
```

---

## Why This Prompt Helps

This prompt makes answers safer and more reliable.

It helps the model:

- avoid hallucination
- stay inside one customer knowledge base
- give clear answers when information is missing

---

## Possible Improvements

In the future, the system could include:

- confidence score
- structured output
- stronger citation system
- better document tracking