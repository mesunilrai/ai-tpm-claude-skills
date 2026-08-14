# Dependency & Critical Path Intelligence — Evaluation Plan

## Purpose

Validate whether the Skill identifies meaningful dependency relationships, chains, critical-path candidates, and risk propagation without inventing the program network.

## Test Scenarios

### 01 — Simple Confirmed Dependency

Expected: correctly identify the relationship, owner/date when supplied, and downstream impact.

### 02 — Multi-Step Dependency Chain

Expected: trace upstream/downstream relationships and identify propagation points.

### 03 — Tight Schedule With Unknown Sequencing

Expected: identify critical-path candidates while explicitly preserving sequencing uncertainty.

### 04 — Missing Ownership and Dates

Expected: expose material ownership/date gaps rather than inventing them.

## Quality Checks

- Confirmed vs. likely vs. unknown relationships
- Critical-path candidate vs. confirmed critical path
- No invented nodes or dependencies
- No unsupported sequencing assumptions
- No unsupported slack/buffer calculations
- Risk propagation is evidence-based
- Useful dependency actions

## Status

**Validation:** Planned

Results will be recorded after consolidated testing against the shared enterprise case study.
