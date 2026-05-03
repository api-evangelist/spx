# SPX Graphics

SPX Graphics is an open-source, browser-based graphics control system for live video productions and live streams. It provides a REST API for external control of graphics templates, rundowns, and playback via integrations with CasparCG, OBS, vMix, and similar broadcast software. SPX enables operators to trigger, control, and update live graphics overlays programmatically or via UI.

**Website:** [spxgraphics.com](https://spxgraphics.com)
**GitHub:** [TuomoKu/SPX-GC](https://github.com/TuomoKu/SPX-GC)
**Documentation:** [spxgc.tawk.help](https://spxgc.tawk.help/)
**License:** MIT

## APIs

| API | Description | OpenAPI |
|---|---|---|
| SPX Graphics Control API | REST API for controlling SPX-GC rundowns, templates, and playback | [openapi](openapi/spx-graphics-control-api-openapi.yml) |

## Artifacts

### OpenAPI Specifications

- [spx-graphics-control-api-openapi.yml](openapi/spx-graphics-control-api-openapi.yml) — Full REST API for SPX-GC: rundown control, item playback, direct playout, file listing, data persistence, and extension invocation

### Spectral Rules

- [spx-rules.yml](rules/spx-rules.yml) — Spectral ruleset enforcing SPX API path conventions, operation naming, and response structure

### Naftiko Capabilities

- [live-graphics-production.yaml](capabilities/live-graphics-production.yaml) — Unified live graphics production capability (REST + MCP)

#### Shared Per-API Definitions

- [spx-graphics-control.yaml](capabilities/shared/spx-graphics-control.yaml) — SPX Graphics Control API shared definition

### JSON Schema

- [spx-rundown-item-schema.json](json-schema/spx-rundown-item-schema.json) — Schema for SPX rundown item objects including template fields and playback state

### JSON Structure

- [spx-rundown-item-structure.json](json-structure/spx-rundown-item-structure.json) — Field-level documentation for SPX rundown items

### JSON-LD

- [spx-context.jsonld](json-ld/spx-context.jsonld) — JSON-LD context for SPX Graphics vocabulary aligned with schema.org

### Examples

- [spx-load-rundown-example.json](examples/spx-load-rundown-example.json) — Load a rundown file into SPX-GC
- [spx-direct-playout-example.json](examples/spx-direct-playout-example.json) — Direct template playout with field data

### Vocabulary

- [spx-vocabulary.yml](vocabulary/spx-vocabulary.yml) — SPX Graphics domain vocabulary (rundowns, templates, play/stop/continue commands, extensions)

## Key Concepts

SPX-GC runs as a local web server (default port 5656) and exposes a REST API for external control by devices like the Elgato Stream Deck, automation scripts, or AI agents. Core capabilities include:

- **Rundown Control** — Load rundown files, navigate items, and manage focus
- **Playback Commands** — Play, stop, and continue graphics items in output
- **Direct Playout** — Trigger templates without a rundown context (v1.0.12+)
- **Item Updates** — Change template field data on the fly
- **File Management** — Browse ASSETS folder media files for template population
- **Extensions** — Invoke custom SPX extension functions (sports scoring, live timing, etc.)

## Authentication

API key authentication is optional. When the `apikey` configuration is set, pass the key as the `apikey` query parameter on all API requests.

## Tags

Broadcast, Graphics, Live Production, Media, Streaming, Video Production
