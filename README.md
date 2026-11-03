# PSkills

El repositorio PSkills centralizará los esquemas, prompts, herramientas y datasets de prueba para todos los agentes de inteligencia artificial utilizados en las soluciones del DevTeam. Su objetivo es evitar la duplicación de código y estandarizar las capacidades de los agentes.

## Flujo de trabajo (Trunk-Based Development)

- `main` es la única rama permanente y siempre deployable.
- Las funcionalidades se desarrollan en ramas efímeras: `feature/<nombre>` (máximo 3 días).
- Los hotfixes críticos usan ramas `hotfix/<nombre>` con feature flag.
- No existen ramas `develop`, `release` ni soporte de versiones antiguas.

## CI/CD

Los pipelines de GitHub Actions se encuentran en `.github/workflows/`:
- `ci.yml`: validación en cada PR y push a `main`.
- `release.yml`: generación automática de tags SemVer en cada merge a `main`.
- `rollback.yml`: rollback manual ante incumplimiento del flujo.

## Reglas de contribución

Consulta `CONTRIBUTING.md` para la guía completa de ramas, commits convencionales, pull requests, tags y seguridad.

## Licencia

Apache License 2.0. Consulta `LICENSE` para más detalles.
