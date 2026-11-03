# Guía de contribución — PSkills

## Flujo de trabajo (Trunk-Based Development)

- `main` es la única rama permanente y siempre debe estar en estado deployable.
- Las funcionalidades se desarrollan en ramas efímeras: `feature/<nombre>`.
- Vida máxima de una rama de feature: **3 días**.
- Los hotfixes críticos usan ramas `hotfix/<nombre>` con **feature flag**.
- No existen ramas `develop`, `release` ni soporte de versiones antiguas.

## Crear una rama de feature
```bash
git checkout main
git pull origin main
git checkout -b feature/mi-cambio
```

## Commits convencionales
Todos los commits deben seguir el formato:
```
<tipo>: <descripción>
```
Tipos permitidos: `feat`, `fix`, `docs`, `chore`, `refactor`, `test`, `build`, `ci`.

Ejemplo: `feat: agregar esquema de validación para prompts`

## Pull Request
1. Abre un PR hacia `main` desde tu rama de feature.
2. Completa la plantilla de PR (`.github/pull_request_template.md`).
3. Mínimo 1 aprobación del staff (4 miembros).
4. Los checks de CI deben estar verdes.
5. Vida máxima de la rama: 3 días. Mergear o abandonar.

## Tags y releases
- Los tags SemVer (`v1.0.0`) son generados automáticamente por el CI en cada merge a `main`.
- No se crean release notes por ahora; solo el tag.
- Ningún release puede saltar el flujo. Ante incumplimiento, rollback inmediato.

## Seguridad
- No commitear secretos ni credenciales.
- Toda PR pasa por la skill `pr-review` para verificar ausencia de fugas de seguridad.
