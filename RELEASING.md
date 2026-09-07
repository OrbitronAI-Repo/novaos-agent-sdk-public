# Release Process

This document describes how to cut a release of `novaos-agent-sdk`.

## Versioning

Semantic Versioning. While `0.y.z`, breaking changes are allowed in a minor bump.

## Release Checklist

1. Bump `version` in `pyproject.toml` and `src/novaos_agent_sdk/__init__.py` (must match).
2. Commit, PR, merge to `main`.
3. Tag the merge commit: `git tag -a vX.Y.Z -m "Release vX.Y.Z" && git push origin vX.Y.Z`.
4. Create a GitHub Release from that tag — `.github/workflows/release.yml` fires on release
   published and publishes to PyPI via trusted publishing (no stored credentials needed).

## Trusted Publishing

PyPI project `novaos-agent-sdk` has a pending/trusted publisher configured for
`OrbitronAI-Repo/novaos-agent-sdk-public`, workflow `release.yml`. Do not rename
that workflow file or move it — PyPI matches on repo + workflow filename.
