# 260418_GothicApse

A rule-based, parametric apse generator for research workflows, focused on producing simplified recursive Gothic apse geometries in **2D plan** and **abstracted 3D triangular mesh form**.

## Project Goal

This project aims to build an understandable and adjustable geometry system for journal-oriented exploration of historical apse logic:

- Start from recursive 2D plan rules (ambulatory + chapel subdivision).
- Keep parametric controls explicit and editable.
- Generate a 3D mesh that is abstract, polygonal, and triangulated.
- Preserve coherence between plan triangulation and 3D representation.
- Support quick figure production via browser-based PNG export.

## Current Implementation

The core prototype is in `apse_2d3d.html` (single-file HTML/JS, no server required).

It includes:

- Split view:
  - `Plan 2D` canvas
  - `Abstract 3D` canvas
- Parametric controls:
  - `edges`, `sequence`, `apseSize`, `apseRatio`, `divisionThreshold`
  - `columnSize`, `chapelScale`, `wallThickness`
  - 3D controls: `heightScale`, `depthScale`, `rotationY`
  - deterministic `seed`
- Seeded randomization and combined PNG export.
- Interactive 3D camera:
  - drag to rotate
  - Shift/right-drag to pan
  - mouse wheel to zoom
  - double-click to reset

## 3D Modeling Direction (from this build session)

The 3D system was iterated toward a **faceted cascading mesh** inspired by half-model investigations of historical apses:

- No smoothing surfaces.
- Triangle-only polygonal geometry.
- Cascade from central high region downward toward outer edges.
- Connected triangular side walls to close volume boundaries.
- 3D triangulation derived from existing 2D triangulation primitives (ring diagonals, chapel cross-lines, termination fans), rather than adding smooth tessellation overlays.

## Conversation Summary

This implementation session progressed in three stages:

1. **Initial extension plan**
   - Kept original 2D recursive logic.
   - Added 3D projection in the same HTML/JS medium.

2. **First 3D revision**
   - Corrected directionality so the form cascades downward (muqarnas-like) instead of reading as upward growth.
   - Added isometric-style default with interactive rotate/pan/zoom controls.

3. **Second 3D revision (current state)**
   - Removed smoothed/grid-like behavior.
   - Rebuilt 3D as strict polygonal triangles aligned with 2D triangulation logic.
   - Kept the model connected and continuous with triangular faces.

## Files

- `apse_2d3d.html` - main interactive prototype (2D + 3D)
- `apse_simplified.html` - earlier 2D baseline prototype
- `Apse Models Drawings/*.dxf` - reference half-model/apse drawing files
- `PDF12530_001.jpeg`, `PDF2205_000.jpeg` - visual references
- `GUARDRAILS.txt` - project constraints and architecture intent

## Running

Open `apse_2d3d.html` directly in a browser.

No build step and no server are required.
