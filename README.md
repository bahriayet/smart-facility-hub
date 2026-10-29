<h1 align="center">Smart Palm-Oil Yield &amp; Sustainability Monitor</h1>

<p align="center">
  <strong>A specification-first prototype for palm-oil mill operations: real-time weighing, local AI yield prediction, truck queues, and Telegram notifications.</strong>
</p>

<p align="center">
  <img alt="Status: specification" src="https://img.shields.io/badge/status-specification-C98A12?style=flat-square">
  <img alt="Next.js" src="https://img.shields.io/badge/Next.js-16-111111?style=flat-square&logo=next.js&logoColor=white">
  <img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-5-3178C6?style=flat-square&logo=typescript&logoColor=white">
  <img alt="Tailwind CSS" src="https://img.shields.io/badge/Tailwind-4-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white">
</p>

> **Status:** this repository currently contains the product requirements and a
> Next.js scaffold. The dashboard, weighing integration, AI service, and
> Telegram bot are **not implemented yet**. The README describes the intended
> product, not shipped functionality.

## Problem

Palm-oil mills (PKS) coordinate weighbridges, truck queues, lab sampling, and
loading ramps with paper forms, spreadsheets, and phone calls. The result is
avoidable waiting time, delayed quality feedback, and weak traceability from
the weighbridge to the mill's yield.

This project explores a single operations dashboard that connects those steps.

## Planned capabilities

- **Real-time weighing** — gross, tare, and net weight synced from the
  weighbridge to the dashboard, with offline buffering.
- **Local yield prediction** — a Python service estimates oil extraction rate
  (rendemen) from fruit quality and historical data before the truck unloads.
- **Truck queue management** — gate, weighbridge, and loading-ram status with
  priority rules based on arrival time and fruit quality.
- **Telegram notifications** — queue calls, weighing results, and unloading
  instructions sent to drivers without a custom app.
- **Traceability** — a record from supplier and truck to weighbridge, quality
  prediction, and mill intake.

## Current repository

```text
PRD.md                  Product requirements and architecture
src/app/                Next.js App Router scaffold
src/components/         Empty folders reserved for dashboard, queue,
                        weighing, AI prediction, and UI components
src/lib/                Shared utilities (empty)
src/services/           Firebase, Telegram, and AI clients (empty)
src/types/              Shared TypeScript types (empty)
```

## Run the scaffold

```bash
npm install
npm run dev
# http://localhost:3000
```

Build:

```bash
npm run build
```

## Roadmap

1. Model the weighbridge ticket, truck, supplier, and queue entities.
2. Build the operator dashboard with a mock in-memory store.
3. Add Firebase persistence and offline sync.
4. Add the Python yield-prediction service and a typed API boundary.
5. Add Telegram notifications for drivers.
6. Add authentication, roles, and an audit trail.

## Documentation

The full specification is in [PRD.md](PRD.md). It covers the product vision,
core features, high-level architecture, and success metrics.

## Why this is public

The specification is published as a reference for teams building mill
operations software. It is intentionally separate from the author's production
projects until the implementation is usable.
