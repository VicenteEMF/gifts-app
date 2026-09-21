# gifts-app

Plataforma de listas de regalos: perfiles con gustos y tallas, listas por ocasión
y reserva de regalos sin arruinar la sorpresa ni duplicar compras.

**Estado del proyecto:** fase de descubrimiento. Todavía no existe código de
aplicación. Ver `docs/README.md` para las fases y `docs/01-descubrimiento/problema.md`
para el planteamiento del problema.

## Idioma

- Código, identificadores, nombres de archivos y mensajes de commit: **inglés**.
- Documentación en `docs/` y conversación: **español**.

## Convenciones de Git

- Commits siguiendo Conventional Commits: `feat:`, `fix:`, `docs:`, `refactor:`,
  `test:`, `chore:`.
- Un commit por cambio lógico. No agrupar cambios no relacionados.
- No hacer push directo a `main`. Trabajar con ramas y pull request.
- Nombres de rama: `feat/short-description`, `fix/short-description`.
- No commitear `.env`, credenciales ni `node_modules`.
- No agregar `Co-Authored-By` ni menciones de herramientas en los mensajes de commit.

## Stack previsto

| Capa | Tecnología |
|---|---|
| API | NestJS + Prisma |
| Base de datos | PostgreSQL |
| Web | Next.js (React) |
| Móvil | React Native (Expo) |

La justificación está en `docs/decisiones/ADR-001-stack-tecnologico.md`.

**Orden de construcción obligatorio: API → web → móvil.** No iniciar el cliente
móvil hasta que la web esté funcional y desplegada.

## Reglas de trabajo

- **Verificar antes de afirmar.** Las versiones de Next.js, Expo y las
  herramientas de monorepo cambian rápido. No inventar nombres de funciones,
  métodos ni opciones de configuración: si hay duda, decirlo y consultar la
  documentación oficial vigente.
- **No inventar contexto de producto.** Si una decisión de producto no está en
  `docs/`, preguntar en vez de asumir. Las hipótesis del documento de problema
  están sin validar y no deben tratarse como hechos.
- **Registrar decisiones técnicas relevantes** como un nuevo ADR en
  `docs/decisiones/`, numerado secuencialmente, no como comentarios en el código.
- **Cambios acotados.** Preferir propuestas pequeñas y revisables. Para cambios
  que toquen varios archivos o el modelo de datos, presentar el plan antes de
  escribir código.
- No crear archivos de documentación nuevos sin que se hayan pedido.

## Contexto del desarrollador

Trabaja una sola persona en el proyecto. Tiene experiencia previa en NestJS,
Prisma, MySQL y Angular. React, Next.js, React Native, PostgreSQL y los monorepos
son nuevos para él, así que al introducir patrones propios de esas tecnologías
conviene explicar el porqué, no solo entregar el código.

## Estructura objetivo

```
apps/
  api/      → NestJS
  web/      → Next.js
  mobile/   → Expo
packages/
  shared/   → tipos y validaciones compartidas
docs/       → documentación de producto e ingeniería
```

Esta estructura es el objetivo, no el estado actual. La generan las herramientas
del monorepo al inicializarlo.

## Datos personales

La aplicación almacena datos personales (tallas, intereses, relaciones entre
personas). Principios de diseño obligatorios:

- Recolectar el mínimo de datos necesario.
- Privacidad por defecto: nada público salvo que el usuario lo decida.
- Las reservas de regalos **nunca** deben ser visibles para el dueño de la lista.
  Cualquier endpoint o consulta que exponga reservas debe filtrarlas según quién
  consulta.
