# Phase 1: Chatbot to Model Rendering

## Objective

A user types a model request into a chatbot and receives a useful interactive 3D scene in the browser within a few seconds.

## User story

As a non-expert creator, I want to describe an object in everyday language so that I can immediately inspect a 3D interpretation without learning modeling software.

## End-to-end flow

1. The user enters a prompt such as “Create a neon lunar rover with six wheels and a sensor mast.”
2. The chat layer sends the prompt to a server route.
3. The generation layer produces a bounded, structured `ModelSpec` document.
4. The server validates that document before returning it.
5. The renderer converts each valid part into a 3D primitive and displays the scene.
6. The user can orbit, zoom, reset the camera, and try another prompt.
7. If AI generation fails, the deterministic fallback returns a valid scene instead.

## In scope

- One-page chatbot and viewer experience.
- Text prompts of a safe, bounded length.
- Procedural scenes made from common primitives.
- Scene title, background, floor, lights, and reusable materials.
- Part position, rotation, scale, color, and primitive type.
- Loading, success, empty, and error interface states.
- Mouse and touch orbit controls.
- Deterministic fallback behavior.
- Basic automated validation and a rehearsed demo script.

## Out of scope

- Photorealistic mesh generation.
- Import or export of GLB, OBJ, or STL.
- Hand tracking and camera access.
- Authentication, accounts, or persistence.
- Multi-user collaboration.
- Blockchain or telemetry.
- Final cloud infrastructure.

## Proposed ModelSpec contract

The exact JSON Schema will be frozen in the first GitHub issue. At minimum it will define:

- Scene name and short explanation.
- Background and floor colors.
- A bounded list of parts.
- A stable identifier for every part.
- A supported primitive type for every part.
- Position, rotation, and scale as numeric three-value vectors.
- Material color plus bounded roughness and metalness.
- Optional simple animation metadata.

## Acceptance criteria

- A user can go from a fresh page to a visible 3D result without instructions.
- The same valid `ModelSpec` always renders the same scene.
- Invalid or malicious model data is rejected before rendering.
- AI failure does not end the demo; a fallback result appears with a clear status.
- Renderer interaction stays smooth on the team’s demo laptop.
- No secret is exposed to the browser or source repository.
- The complete flow can be demonstrated in under 60 seconds.

## Definition of done

- All Phase 1 issues are closed through reviewed pull requests.
- The contract and architecture documents match the implementation.
- Lint, type checks, tests, and production build pass.
- Both teammates have run the demo from a clean checkout.
- The fallback path has been tested with the AI key removed.
