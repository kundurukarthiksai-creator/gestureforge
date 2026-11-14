# Proposed Phase 1 Architecture

## Principle

The shared contract is the center of the system. The chatbot and renderer can be developed in parallel only after both teammates agree on the same `ModelSpec`.

## Boundaries

### Chat interface

Owns prompt entry, conversation display, loading state, error state, suggested prompts, and generation status. It does not know how Three.js geometry is constructed.

### Generation route

Owns server-side provider calls, prompt instructions, structured output, validation, and fallback selection. API keys remain on the server.

### Model contract

Owns the supported primitive vocabulary and all numeric bounds. It is imported by both the generation route and renderer. This is the first artifact to freeze.

### Renderer

Owns translation from valid model parts to scene objects, lighting, camera behavior, interaction, and rendering performance. It never renders unvalidated provider output.

### Deterministic fallback

Owns several prompt-aware templates such as rover, robot, satellite, vehicle, and abstract composition. It uses the exact same model contract as the AI path.

## Data path

`Prompt → generation route → AI or fallback → schema validation → ModelSpec → renderer → interactive scene`

## Reliability rules

- Validate at the server boundary and again defensively at the client boundary.
- Bound part count, dimensions, material values, and prompt length.
- Keep the fallback local and deterministic.
- Avoid provider-specific objects in the renderer.
- Do not place state updates inside the animation loop; mutate render references instead.
- Keep the first version to procedural primitives so results appear quickly and predictably.

## Proposed repository structure after planning approval

- `src/app` — page and generation API route.
- `src/components/chat` — chat interface.
- `src/components/viewer` — 3D scene and controls.
- `src/lib/model-spec` — shared schema and types.
- `src/lib/generation` — AI provider and fallback adapters.
- `tests` — contract, fallback, route, and smoke tests.

No implementation directories are created in this planning stage.
