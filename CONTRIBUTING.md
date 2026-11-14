# Contributing

## Before implementation starts

1. Confirm Phase 1 scope in `docs/PHASE-1.md`.
2. Assign the chat/generation and model/rendering workstreams.
3. Freeze the first ModelSpec contract through a pull request.
4. Move the relevant GitHub issues into progress.

## Development workflow

- Branch from `main` using the names in `docs/WORKSTREAMS.md`.
- Keep each pull request focused on one GitHub issue.
- Link the issue in the pull request description.
- Add tests or verification notes for behavior changes.
- Request review from the other teammate before merging.
- Never commit API keys, cloud credentials, tokens, or personal data.

## Pull request standard

A pull request explains what changed, how it was verified, which contract fields it affects, and how the live demo behaves if the feature fails.
