# DatumInt

DatumInt is an early-stage tool focused on **file-level data inspection** — helping developers
understand *why a data file that looks valid can still cause problems downstream*.

It is designed to surface **structural, schema, and basic logic issues** in common data formats
before those files are used in pipelines, applications, or analyses.

---

## The Problem

In real-world systems, data files often:
- parse successfully
- look fine in editors
- pass basic validation

…but still cause issues later.

Examples include:
- empty values in required fields
- subtle type inconsistencies
- placeholder values like `"N/A"` or `"unknown"`
- duplicated identifiers
- inconsistent date formats
- values that are structurally valid but logically suspicious

These issues usually aren't caught until much later — during ingestion, transformation,
or even after dashboards or models behave incorrectly.

---

## What DatumInt Does (Today)

DatumInt inspects individual data files (e.g. JSON, CSV) and highlights:

- **Structural issues**
  - malformed rows
  - column count mismatches
  - invalid syntax

- **Schema & type issues**
  - missing required fields
  - unexpected nulls
  - type mismatches (string vs number, boolean as string, etc.)
  - invalid or inconsistent date formats

- **Basic consistency & quality checks**
  - duplicate identifiers
  - implausible or out-of-range values
  - high null / empty rates
  - suspicious patterns worth reviewing

The goal is **inspection and visibility**, not automatic correction or deep business logic.

---

## What DatumInt Is Not

To be explicit, DatumInt currently does **not**:

- replace dbt, Great Expectations, or full data observability platforms
- perform cross-file or cross-table validation
- enforce complex business rules
- do ML-based anomaly detection
- integrate directly into production pipelines

DatumInt is intentionally lightweight and focused on **early inspection and understanding**.

---

## How It's Meant to Be Used

DatumInt works best as:
- a quick inspection step before ingesting files
- a debugging aid when a file "looks fine" but breaks later
- a way to surface issues that are easy to miss by eye or basic parsers

Think of it as a **pre-ingestion sanity check**, not a full data quality system.

---

## Repository Purpose

This public repository exists to share:

- high-level project direction and thinking
- documentation and examples
- roadmap and design decisions

Core application code and internal systems live elsewhere and are not part of this repository.

---

## Project Status

DatumInt is in **early development (v0.x)**.

The scope is intentionally narrow while we validate:
- which issues are most painful in practice
- which signals are genuinely useful to developers
- how inspection results should be presented

Roadmap and progress:
- [ROADMAP.md](ROADMAP.md)
- [GitHub Issues](https://github.com/DatumInt/datumint/issues)

---

## Follow or Get Involved

If this problem space resonates with you:

- Star or watch the repository
- Share feedback through issues
- Follow along as the project evolves

This project is exploratory by design, feedback matters more than polish at this stage.
