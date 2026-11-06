# Scanarity
*Local Preflight for Digitized Image Batches*
**Status:** documentation-only public proof of work; application package and source code are not publicly distributed.

## Overview
Scanarity is a local Windows desktop prototype for a mechanical first pass over batches of digitized still images. It is designed to help a human reviewer find files or groups that deserve attention before archiving, hand-off, ingest, or deeper visual quality control.

The core idea is intentionally narrow:

> “Select a folder. Run a local preflight. Review only the files that deserve attention.”

This repository is documentation-only. It does not contain Scanarity source code, the internal release-candidate package, proprietary detection logic, private test fixtures, security documentation, or the internal validation dossier.

## Why this exists
Digitization workflows often combine automated technical checks with human visual review. Scanarity explores a small, low-friction first-pass workflow for teams that handle recurring still-image batches but do not have a mature institutional QC pipeline.

The project does not attempt to replace professional digital-preservation systems or human quality control.

## What v0.1 checks
At a public, high-level description, the v0.1 prototype:
- scans supported image files directly inside one selected local folder;
- supports TIFF, JPEG and PNG filename families;
- identifies supported-image candidates that cannot be read or structurally verified within the supported limits;
- flags mismatches between a supported filename extension and the detected image format;
- identifies exact duplicate file content;
- flags conservative filename-sequence anomalies where the observed naming pattern provides enough evidence;
- reports selected technical metadata distributions and inconsistencies where the comparison is meaningful;
- presents results with ERROR, REVIEW and INFO semantics so anomalies do not automatically become quality verdicts.

## Design boundaries
The v0.1 prototype is:
- local and Windows-focused;
- deterministic, with no AI model in the runtime;
- designed to read the selected batch without intentionally modifying, renaming, moving, deleting, repairing or copying the source files;
- built around an anomaly-first interface rather than one PASS row per file;
- designed without an account, cloud service, API key, analytics or telemetry requirement for the application function;
- deliberately conservative about what it can prove.

Human review remains authoritative. A REVIEW finding means “look at this”, not “this file is wrong”.

## Evidence from the internal v0.1 experiment
The internal v0.1 experiment reached a frozen RC2 baseline after implementation, testing, Windows acceptance and documentation reconciliation.

Public-safe evidence summary:
- the internal core suite completed 67/67 tests successfully on the verified code line;
- manual Windows acceptance covered GUI launch, local-folder selection, a clean synthetic batch, a synthetic batch with known problems, cancellation and rerun;
- controlled acceptance checks confirmed that the source batch remained unchanged;
- the final RC2 audit identified package-internal documentation drift only; the production code, test code and acceptance fixtures of the verified code line were not changed by the RC2 documentation reconciliation.

These statements describe the documented experiment. They do not mean that Scanarity is already a public-distribution or commercial-release package.

## What Scanarity does NOT claim
Scanarity v0.1 does not:
- judge blur, skew, crop, reflections, exposure, contrast or color fidelity;
- perform OCR or semantic/content validation;
- certify archival or preservation compliance;
- guarantee that a digitized batch is safe to accept;
- detect every physically missing page or item;
- scan subfolders recursively;
- process PDF, RAW, HEIC, video or audio;
- provide a public installer or commercial distribution package;
- replace backups, preservation procedures or professional human review.

## Project status
Public product name: Scanarity.
Internal historical/technical baseline: Digitization Batch Guard v0.1 RC2 — frozen.
Technical experiment: complete for the documented v0.1 scope and environment.
Public distribution package: not released.
Commercial validation: ongoing; the current market gate remains “continue with conditions / not yet full pass”.
Commercial release: not authorized by the current project documentation.

## Why the code is not in this repository
Scanarity is being developed as a potential commercial product. The implementation, proprietary rule logic, internal test suite, security documentation and commercial research are therefore kept private.

This repository exists to make the work verifiable at the level appropriate for public proof of work: problem framing, product boundaries, evidence discipline, limitations and project status — without publishing the commercial core.

## Repository boundary
This public repository is intended to contain documentation and, if approved, sanitized visual material only.

Not included:
- source code or executable packages;
- internal test suites or fixtures;
- proprietary rule details;
- threat models or security evidence;
- internal roadmap, pricing or prospect research;
- internal standards or private project documentation.
