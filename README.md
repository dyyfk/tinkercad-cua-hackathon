# Tinkercad CUA Hackathon

Browser automation experiments that pair Kernel cloud browsers with Tzafon Northstar computer-use actions to operate Tinkercad and generate 3D model assets.

## What is included

- `tinkercad-builder-app.mjs` - Kernel app that logs into Tinkercad, opens the 3D editor, and hands the browser to Northstar to create a simple design.
- `tinkercad-advanced-cat-primitives.mjs` - primitive-based Tinkercad construction run for an advanced cat model.
- `tinkercad-import-bear-doll.mjs`, `tinkercad-advanced-cat-import.mjs`, and `tinkercad-fortnite-llama.mjs` - import generated STL assets into Tinkercad.
- `build-*-assets.mjs` - local asset generators for printable/exportable STL, OBJ, SVG preview, and HTML reports.
- `cat_assets/`, `advanced_cat_assets/`, `bear_doll_assets/`, and `llama_assets/` - generated 3D assets and build notes.

## Setup

```bash
npm install
cp .env.example .env
```

Fill in `.env` with `KERNEL_API_KEY` and `TZAFON_API_KEY`. Add `TINKERCAD_EMAIL` and `TINKERCAD_PASSWORD` only for scripts that need to sign in to Tinkercad.

## Run

Deploy the Kernel app:

```bash
npx kernel deploy tinkercad-builder-app.mjs --env-file .env
npx kernel invoke tinkercad-builder build
```

Generate assets locally:

```bash
node build-small-3d-cat-assets.mjs
node build-advanced-3d-cat-assets.mjs
node build-bear-doll-assets.mjs
node build-fortnite-llama-assets.mjs
```

## Notes

Local `.env`, downloaded videos, dependency folders, and one-off browser run outputs are ignored so the repository can stay public and reproducible without publishing secrets or bulky scratch files.
