# BESS Design Tool - AI Development Instructions

## Project Purpose

Build and maintain a production-quality web application for preliminary BESS project design, sizing, configuration, layout and technical documentation.

The application should support an engineering workflow from project inputs through equipment selection, calculations, validation and reporting.

## Technology

- Next.js
- TypeScript
- React
- Tailwind CSS
- Vercel deployment

Prefer the existing project stack and patterns. Do not introduce a new framework or major dependency without a clear reason.

## Engineering Rules

- Keep engineering calculations separate from UI components.
- Calculations must be deterministic, testable and use explicit units.
- Use SI units consistently unless the UI explicitly requires another unit.
- Equipment specifications must come from structured project data.
- Never invent manufacturer specifications, certifications or performance values.
- Clearly distinguish user inputs, calculated values and assumptions.
- Make important assumptions visible to the user.
- Add tests for calculation logic and validation rules.

## Software Rules

- Use TypeScript strict typing.
- Prefer small, reusable components.
- Reuse existing components and utilities before creating duplicates.
- Keep business logic out of presentation components where practical.
- Keep dependencies to a minimum.
- Never put secrets, API keys or credentials in client-side code.
- Keep environment variables documented in `.env.example`.

## Change Workflow

Before changing code:

1. Inspect the existing implementation.
2. Identify the relevant files and dependencies.
3. Explain the intended change when the task is complex.
4. Make the smallest sensible change.

After changing code:

1. Run linting.
2. Run relevant tests.
3. Run the production build.
4. Fix errors before considering the task complete.
5. Summarize changed files and validation performed.

## Scope Control

Do not:

- Rewrite unrelated functionality.
- Redesign existing screens unless requested.
- Remove working functionality without explicit instruction.
- Add authentication, databases or external services unless requested.
- Add dependencies just to solve a small problem.
- Hard-code engineering assumptions inside UI components.

## UI

The application should be:

- Desktop-first but responsive.
- Clear and suitable for engineering users.
- Consistent in spacing, typography and component usage.
- Accessible and keyboard-friendly where practical.

Prioritize functional clarity over decorative UI.

## BESS Domain

Use clear terminology for:

- BESS power: MW
- BESS energy: MWh
- Duration: h
- Efficiency: %
- State of Charge: SoC
- State of Health: SoH
- Depth of Discharge: DoD
- Power Conversion System: PCS
- Energy Management System: EMS
- Supervisory Control and Data Acquisition: SCADA
- Medium Voltage: MV
- Grid connection / Point of Connection: PoC

When a calculation depends on degradation, efficiency, usable SoC window, temperature or other assumptions, expose those assumptions rather than hiding them.

## AI Behaviour

When requirements are ambiguous, identify the ambiguity rather than silently inventing a requirement.

When asked to implement a feature:

- First inspect the repository.
- Reuse existing architecture.
- Implement only the requested scope.
- Add or update tests where appropriate.
- Do not claim something works unless it has been validated.

