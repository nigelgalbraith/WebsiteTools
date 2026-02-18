# WebsiteTools

WebsiteTools is a modular utility suite for generating site structure diagrams, flowcharts, and optimized assets for structured static websites.

It is designed to automate documentation, enforce consistency, and reduce manual diagram maintenance.

The goal is simple:

- Keep site structure explicit
- Keep diagrams configuration-driven
- Keep logic modular
- Keep outputs reproducible
- Avoid manually maintained visual documentation

---

## Overview

WebsiteTools provides:

- Site structure diagram generation (Mermaid-based)
- Flowchart generation from JSON configuration
- Image optimization utilities
- Structured JSON-driven rendering
- Rebuildable documentation artifacts

Instead of manually drawing diagrams, this system:

1. Reads structured configuration files
2. Generates `.mmd`, `.svg`, or related outputs
3. Produces consistent, repeatable diagrams
4. Keeps documentation synchronized with project structure

---

## Core Components

### 1. Generate-SiteDiagrams.py

Generates site maps and structural diagrams from JSON configuration files.

Used for:

- HTML page relationship diagrams
- JavaScript dependency diagrams
- Project page structure visualization
- Multi-page site hierarchy diagrams

Configuration files are located in:

```
diagrams/siteMaps/
```

Each JSON file defines:

- Node labels
- Relationships
- Styles
- Links
- Metadata
- Rendering rules

---

### 2. Generate-Flowchart.py

Generates structured flowcharts from JSON configuration files.

Used for:

- Application logic flows
- Program pipelines
- Script execution paths
- Data transformation flows

Configuration files are located in:

```
diagrams/flowCharts/
```

Each flow configuration defines:

- Node types
- Labels
- Connections
- Styles
- Direction
- Diagram layout

This allows program logic to be visually documented without manual diagram tools.

---

### 3. Image-Optimizer.py

Optimizes image assets used in the website.

Designed to:

- Reduce image size
- Standardize formats
- Maintain visual quality
- Update references where required

Helps maintain performance while preserving consistency.

---

## Folder Structure

```
WebsiteTools/
│
├── PythonFiles/
│   ├── Generate-SiteDiagrams.py
│   ├── Generate-Flowchart.py
│   ├── Image-Optimizer.py
│
├── diagrams/
│   ├── siteMermaidConfig.json
│   ├── FlowConfig.json
│   │
│   ├── siteMaps/
│   │   ├── *.json
│   │   ├── *.mmd
│   │   ├── *.svg
│   │
│   ├── flowCharts/
│       ├── *.json
│       ├── *.mmd
│       ├── *.svg
```

- `.json` → configuration source
- `.mmd` → Mermaid intermediate files
- `.svg` → rendered diagram output

---

## Execution Model

All tools follow the same pattern:

1. Load configuration
2. Validate structure
3. Generate diagram or asset
4. Write output
5. Report status

No logic is hardcoded into diagrams.

All relationships are configuration-driven.

---

## Site Diagram Generation

To generate site structure diagrams:

```bash
python3 PythonFiles/Generate-SiteDiagrams.py
```

This reads:

- `siteMermaidConfig.json`
- JSON files inside `diagrams/siteMaps/`

Outputs:

- Mermaid files
- SVG diagrams

---

## Flowchart Generation

To generate flowcharts:

```bash
python3 PythonFiles/Generate-Flowchart.py
```

This reads:

- `FlowConfig.json`
- JSON files inside `diagrams/flowCharts/`

Outputs:

- Mermaid files
- SVG diagrams

---

## Image Optimization

To optimize images:

```bash
python3 PythonFiles/Image-Optimizer.py
```

This processes defined image assets according to configuration rules.

---

## Architecture Principles

WebsiteTools is built around:

- Configuration-driven generation
- Single-responsibility scripts
- Deterministic output
- Reusable generation logic
- Separation of structure and rendering
- No manually edited diagram artifacts

Diagrams are treated as build artifacts — not hand-drawn documentation.

---

## Conceptual Pipeline

```
JSON Configuration
        ↓
Python Generator
        ↓
Mermaid (.mmd)
        ↓
Rendered Output (.svg)
        ↓
Website Documentation
```

Documentation remains synchronized with system structure.

---

## Intended Use

WebsiteTools is designed to support:

- Portfolio documentation
- System architecture visualization
- Static site documentation workflows
- Program flow documentation
- Rebuildable diagram systems

It eliminates manual diagram drift.

---

## Run

Ensure Python 3 is installed.

Then execute the relevant script:

```bash
python3 PythonFiles/<script_name>.py
```

All configuration is located in the `diagrams/` directory.
