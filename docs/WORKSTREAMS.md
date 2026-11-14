# Phase 1 Workstreams

## Recommended split

### Workstream A: Chat and generation

Recommended owner: Karthik or teammate selected by the team.

Responsibilities:

- Chat interface and prompt suggestions.
- Generation API request and response behavior.
- Gemini structured-output adapter.
- Deterministic fallback generator.
- Loading, failure, and provider-status messages.
- Unit tests for generation and fallback behavior.

### Workstream B: Model contract and rendering

Recommended owner: Shiva or teammate selected by the team.

Responsibilities:

- ModelSpec schema review and renderer-facing types.
- Primitive and material mapping.
- Camera, orbit, zoom, lighting, grid, and reset controls.
- Renderer error boundary and empty state.
- Performance testing on the demo laptop.
- Unit or component tests for supported part types.

### Shared integration

Both teammates own:

- Freezing the ModelSpec before independent work begins.
- Connecting the API response to the live viewer.
- Testing malformed and oversized data.
- Rehearsing the 60-second judging flow.
- Reviewing one another’s pull requests.

## Branch plan

- `feat/model-contract`
- `feat/chat-generation`
- `feat/model-renderer`
- `feat/phase-1-integration`
- `test/demo-hardening`

## Merge order

1. Model contract.
2. Renderer and chat workstreams in parallel.
3. Generation adapter and deterministic fallback.
4. End-to-end integration.
5. Demo hardening.

## Ownership decision still needed

The recommended split is not final. Record the chosen owners in this file and assign the GitHub issues after Shiva’s username is added.
