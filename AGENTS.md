# Codex Configuration

This repository contains organization-level GitHub metadata and shared community
health files. Keep changes focused, readable, and compatible with GitHub's
repository-level conventions.

# TDF GIS AI Agent Configuration

This document outlines the standard operating procedures, environmental constraints, and coding standards for AI coding agents (Codex, Cline, Gemini) operating within the Tennessee Division of Forestry (TDF) GIS and Analytics repositories. Adhere to these instructions strictly.

## Working Guidelines

- Make the smallest, most efficient change that satisfies the request.
- Preserve existing code architecture, Markdown structure, and wording unless the task explicitly asks for a broader refactoring or cleanup.
- Prefer plain Markdown and GitHub-supported syntax over custom HTML for documentation.
- Treat documentation and shared templates as team-wide defaults; avoid unnecessary formatting churn.

## Environment & Tooling Constraints

- **Group Policy Block:** This local workspace environment strictly blocks local shell and PowerShell executions. 
- **No Terminal Usage:** Do not use shell or terminal commands to verify, preview, inspect, or read back file edits.
- **Direct File IO:** Rely entirely on direct file-read and file-write tools for repository work.
- **Assume Success:** After a direct file-write tool reports success, assume the write succeeded. Do not attempt to run a readback command to verify it.
- **Unseen Context:** If unseen file context is required, ask the user to provide the relevant file contents instead of attempting to use terminal commands to guess or inspect it.

## Validation

- For Markdown-only edits, review the rendered structure mentally and check that links, tables, and heading levels remain valid.
- When changing GitHub workflow or configuration files, validate syntax using internal tool knowledge.
- Do not introduce generated artifacts, build outputs, or editor metadata (e.g., `.vscode/` files) unless explicitly requested.

## GIS & Data Handling

- **No Binary Reads:** NEVER attempt to read binary spatial files (e.g., .shp, .gdb, .tif, .gpkg) or large data files (e.g., .csv, .geojson over 1MB) directly into context.
- **Schema Discovery:** If you need to understand the structure of a dataset, ask the user to provide the schema, or write a short Python script to print the `head()` or `df.info()` and ask the user to run it and paste the output.
- **Projections:** Assume spatial data operates in standard projections (e.g., EPSG:4326 or standard Tennessee State Plane) unless specified otherwise.

## Script Networking Constraints

- **Corporate Proxy:** All TDF team members operate behind a strict Zscaler corporate proxy.
- **External Requests:** If writing scripts that make external network requests (e.g., Python's `requests` library, Node's `axios`), explicitly remind the user in your chat output that they may need to configure `verify=False` (for internal testing only) or point the script to their local Zscaler certificate path.

## Coding Standards & Preferences

- **Python:** Prefer `geopandas`, `pandas`, and the `arcgis` (ArcGIS API for Python) libraries for spatial data manipulation. 
- **Notebooks:** When editing Jupyter Notebooks (`.ipynb`), only modify the exact code cells requested to avoid corrupting the JSON structure.
- **Node.js:** Use ES6 syntax and prefer native `fetch` over third-party request libraries where possible.
- **Documentation:** Always include clear, brief inline comments explaining complex spatial logic, projections, or data transformations.
