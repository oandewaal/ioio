# BESS Design Tool

A web application for preliminary Battery Energy Storage System (BESS) design.

## Purpose

The application is intended to support the early-stage engineering workflow for BESS projects, including:

- Project and site inputs
- BESS sizing
- Battery and PCS selection
- Electrical configuration
- Site layout
- Civil constraints
- MV network design
- Engineering validation
- Design optimization
- 2D CAD output
- 3D visualization
- Technical reports

## Planned Architecture

```
Site / GIS
    ↓
BESS Equipment Library
    ↓
Layout Engine
    ↓
Civil Constraints
    ↓
MV Network
    ↓
Validation Engine
    ↓
Optimization
    ↓
2D CAD / 3D Visualization
    ↓
Reports
```

## Development Principles

The application separates:

1. **Engineering data** - equipment specifications and project inputs
2. **Engineering logic** - sizing, calculations and validation
3. **Application logic** - workflows and state management
4. **Presentation** - UI and visualization
5. **Outputs** - drawings, reports and exported data

Engineering calculations should be deterministic and covered by tests.

## Technology

The target stack is:

- Next.js
- TypeScript
- React
- Tailwind CSS
- Vercel
- GitHub

## Development

Install dependencies:

```bash
npm install
```

Run the development server:

```bash
npm run dev
```

Run checks before committing:

```bash
npm run lint
npm test
npm run build
```

Use `.env.example` to document required environment variables. Never commit secrets.

## AI-Assisted Development

Project-wide AI development rules are defined in [AGENTS.md](./AGENTS.md).

Feature-specific prompts can be stored under:

```
prompts/
```

Recommended pattern:

```
prompts/
├── 00-project.md
├── 01-foundation.md
├── 02-bess-sizing.md
├── 03-equipment-library.md
├── 04-layout-engine.md
├── 05-validation.md
└── 06-reporting.md
```

Each feature prompt should define:

- Context
- Goal
- Existing implementation
- Requirements
- Constraints
- Files or modules affected
- Acceptance criteria
- Validation steps

## Repository Structure

The structure will evolve as the application grows. Prefer domain-oriented modules and keep engineering calculations independent from UI code.

## Deployment

The intended deployment platform is Vercel.

GitHub should be the source of truth for the codebase. Changes should be developed in feature branches where practical, validated, and then merged into the production branch.

## Project Status

Early development.

The architecture and engineering model should be established before adding large feature sets.
