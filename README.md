# container-image-hash

Hash a Docker build context using `git hash-object` and `.dockerignore` filtering,
and optionally emit a reproducible Docker image tag.

The base version comes from `Cargo.toml` when present, otherwise from the nearest
reachable `vX.Y.Z` git tag.

## Development

This project uses [uv](https://docs.astral.sh/uv/) for development. To set up the
environment, run `uv sync`. Tests and checks can be run with:

```bash
uv run ruff check
uv run ruff format --check
uv run ty check
uv run pytest
```

## Usage

```bash
container-image-hash            # print the build context hash
container-image-hash --details   # print hashes for the root context and included files/directories
container-image-hash --tag        # print a Docker tag in the form <base-version>-<hash>
```
