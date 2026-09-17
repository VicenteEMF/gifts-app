# gifts-app

Plataforma de listas de regalos: perfiles con gustos y tallas, listas por ocasión
y reserva de regalos sin arruinar la sorpresa ni duplicar compras.

> **Estado:** fase de descubrimiento. Todavía no hay código de aplicación. La
> documentación de producto e ingeniería está en [`/docs`](./docs).

## El problema

Al momento de regalar, quien regala no suele saber qué quiere la otra persona ni
su talla, y cuando hay varios invitados nadie sabe qué ya compró otro. El
resultado son regalos duplicados, de talla equivocada o que no se usan.

Ver el planteamiento completo en
[`docs/01-descubrimiento/problema.md`](./docs/01-descubrimiento/problema.md).

## Stack previsto

| Capa | Tecnología |
|---|---|
| API | NestJS + Prisma |
| Base de datos | PostgreSQL |
| Web | Next.js (React) |
| Móvil | React Native (Expo) |

La justificación de cada elección y las alternativas descartadas están en
[`docs/decisiones/ADR-001-stack-tecnologico.md`](./docs/decisiones/ADR-001-stack-tecnologico.md).

## Hoja de ruta

- [ ] Validación del problema con entrevistas a usuarios reales
- [ ] Definición del alcance del MVP
- [ ] Diseño de flujos y wireframes
- [ ] Modelo de datos y contrato de API
- [ ] API
- [ ] Cliente web
- [ ] Cliente móvil

## Convenciones

- Código, nombres e identificadores en inglés. Documentación en español.
- Commits siguiendo [Conventional Commits](https://www.conventionalcommits.org/).
- Trabajo mediante ramas y pull requests hacia `main`.
