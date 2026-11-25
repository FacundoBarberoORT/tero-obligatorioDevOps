# ADR 0001: Monorepo

**Estado:** Aceptada | **Fecha:** 2026-11-25

## Contexto
Tero tiene 6 microservicios, infraestructura, pipelines y documentación. Lo hago yo solo.

## Decisión
Dejo todo en un solo repo: `src/` (servicios), `infra/` (Terraform),
`.github/workflows/` (pipelines) y `docs/`.

## Por qué
- Trabajando solo, mantener varios repos suma trabajo y no aporta nada.
- Branch protection, secretos y escaneos se configuran una sola vez.
- Un cambio que toca varios servicios va en un solo PR.

## Si cambian las condiciones
Si el equipo creciera y la infraestructura tuviera otro ciclo y otros permisos,
separaría `infra/` en su propio repo.
