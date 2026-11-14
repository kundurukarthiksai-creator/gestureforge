# GestureForge

**Say it. Shape it. Move it.**

GestureForge is a planned web experience where a person describes a 3D object in a chatbot, sees it rendered, and later manipulates it with hand gestures.

> Planning status: this repository intentionally contains no product implementation yet. Phase 1 is being defined and divided before coding begins.

## Current focus: Phase 1

Build one reliable vertical slice:

**Chat prompt → model specification → interactive 3D rendering**

Phase 1 includes:

- A simple chatbot interface for model requests.
- A strict shared `ModelSpec` contract between chat and rendering.
- An AI generation path that returns structured model data.
- A deterministic fallback so the demo still works without an AI key or network.
- A browser-based 3D renderer with orbit, zoom, lighting, and reset controls.
- A polished end-to-end judging flow.

Phase 1 does not include:

- Webcam or hand-gesture control.
- User accounts or saved galleries.
- MongoDB, Tiger Data, or Solana integration.
- Public cloud deployment or a branded domain.
- High-detail text-to-mesh generation.

Those items remain in the roadmap and will not block the first working slice.

## Product roadmap

1. **Converse and render** — prompt to structured 3D scene.
2. **Gesture control** — operate the scene from webcam hand landmarks.
3. **Persistence** — save, remix, and share models.
4. **Provenance and telemetry** — sponsor-aligned extensions.
5. **Production hosting** — HTTPS deployment and public demo domain.

## Repository map

- [`docs/PHASE-1.md`](docs/PHASE-1.md) — exact first-slice scope and acceptance criteria.
- [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md) — proposed technical boundaries.
- [`docs/WORKSTREAMS.md`](docs/WORKSTREAMS.md) — recommended division of work.
- [`docs/ROADMAP.md`](docs/ROADMAP.md) — later phases and sponsor opportunities.
- [`docs/DECISIONS.md`](docs/DECISIONS.md) — decisions already made and open questions.
- [`docs/DEMO.md`](docs/DEMO.md) — judging story and demo safety plan.
- [`INDEX.md`](INDEX.md) — key-to-file registry for the whole repository.

## Proposed stack for Phase 1

- Next.js and TypeScript for the web application and server route.
- Gemini structured output for prompt-to-scene generation.
- Zod for runtime validation of generated data.
- Three.js through React Three Fiber for rendering.
- A deterministic procedural generator as the offline fallback.

The stack is proposed, not yet implemented. The final decision is recorded before the first build branch starts.

## Team

- Karthik — repository owner and product lead.
- Shiva — collaborator; GitHub username and workstream assignment pending.

## Working agreement

- `main` stays presentation-ready.
- Each task gets a focused branch and pull request.
- No secret or API key is committed.
- The shared model contract is agreed before parallel implementation.
- Every feature keeps a fallback path for the live demo.

## Next decision

Confirm who owns the chatbot workstream and who owns the renderer workstream. Then start Phase 1 from the GitHub issues, not from an untracked feature list.
