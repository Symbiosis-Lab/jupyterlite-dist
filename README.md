# jupyterlite-dist

Pre-built [JupyterLite](https://jupyterlite.readthedocs.io/) static assets for [moss](https://github.com/Symbiosis-Lab/moss).

## What this is

JupyterLite requires Python to build (`jupyter lite build`). This repo runs that build via GitHub Actions and publishes the output as a downloadable zip on GitHub Releases.

moss downloads this zip on-demand when `.ipynb` files are detected in a site, caching it at `~/.moss/assets/jupyterlite/`.

## Releases

Triggered manually or on the 1st of each month. Each release contains:

- `jupyterlite.zip` — the complete static site assets
- `VERSION` file inside the zip for cache validation

## Building locally

```bash
pip install jupyterlite-core jupyterlite-pyodide-kernel
jupyter lite build --output-dir dist/ --no-sourcemaps
```
