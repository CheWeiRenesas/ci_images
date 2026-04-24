# ci_images

Auto-built public container images hosted on [GitHub Container Registry](https://ghcr.io).

## Images

### `ghcr.io/<owner>/debian-uv-gdb`

Debian slim base with:

- [`uv`](https://github.com/astral-sh/uv) – fast Python package manager
- `gdb` – GNU debugger

### `ghcr.io/<owner>/debian-uv-gdb-dev`

Debian slim base with everything in `debian-uv-gdb` plus:

- `gcc` / `g++` – GNU C/C++ compilers
- `mingw-w64` – cross-compiler targeting Windows
- `cmake` – build system generator
- `ninja-build` – fast build system
- `zip` – archiving utility

## Build

Images are built automatically on every push to `main` that touches the `images/` directory or the workflow file.  
They are also available to build manually via **Actions → Build and Push CI Images → Run workflow**.

Images are tagged with:

- `latest` (default branch only)
- the short commit SHA

## Usage

```bash
# minimal image
docker pull ghcr.io/<owner>/debian-uv-gdb:latest

# full development toolchain image
docker pull ghcr.io/<owner>/debian-uv-gdb-dev:latest
```