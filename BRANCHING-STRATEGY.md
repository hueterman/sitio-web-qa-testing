# Branching Strategy - Este Proyecto

## Main Branch (main)
- **Propósito**: Código en producción.
- **Estado**: Siempre deployable (estable).
- **Protección**: Los cambios solo entran vía Pull Request + Aprobación de QA.

## Feature Branches
- **Nombre**: `feature/description-short`
- **Basado en**: `main`
- **Vida útil**: Efímera (se borra tras el merge).
- **Destino**: `main` (tras pasar QA testing).

## Bugfix Branches
- **Nombre**: `bugfix/issue-number`
- **Basado en**: `main`
- **Propósito**: Arreglar errores no críticos.

## QA Testing Branch (Local)
- **Nombre**: `review/feature-name`
- **Propósito**: Rama temporal en local para validar el código de un compañero sin ensuciar tu entorno.

## Tag Convention
- **Formato**: `v[Mayor].[Minor].[Patch]` (Semantic Versioning).
- **Ejemplo**: `v1.2.3`
- **Cuándo**: Se crea un tag al cerrar una versión estable.

## Visual Workflow
```
[main] ──────────────────────────────────────────> (Producción)
  │                                          ↑
  │                                        Merge
  │                                          ↑
  └── [feature/nueva-funcionalidad] ─────────┘
      (Desarrollo + Testing)
```
