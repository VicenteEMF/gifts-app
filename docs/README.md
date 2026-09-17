# Documentación del proyecto

Documentación de producto e ingeniería de la plataforma de listas de regalos.
Vive en el repositorio y se versiona con el código.

## Estado actual

**Fase:** Descubrimiento (definición del problema y validación de hipótesis)
**Última actualización:** 2026-09-17

## Estructura

| Carpeta | Contenido |
|---|---|
| `01-descubrimiento/` | Problema, usuarios, hipótesis, competencia y validación con usuarios reales |
| `02-producto/` | Visión, alcance del MVP, historias de usuario, requisitos no funcionales |
| `03-diseno/` | Flujos de usuario, wireframes, sistema de diseño |
| `04-arquitectura/` | Diagramas C4, modelo de datos, contrato de API |
| `decisiones/` | ADR (Architecture Decision Records) |
| `05-calidad/` | Plan de pruebas, criterios de aceptación, CI/CD |

Las carpetas se crean cuando se llega a la fase correspondiente. No se documenta
por adelantado algo que todavía no se ha decidido.

## Convenciones

- Todo documento distingue explícitamente entre **hecho verificado**, **hipótesis
  sin validar** y **decisión tomada**. Una hipótesis nunca se escribe como si
  fuera un hecho.
- Toda afirmación sobre el mercado, la competencia o la normativa legal lleva
  fuente o queda marcada como pendiente de verificar.
- Las decisiones técnicas relevantes se registran como ADR, no se dejan
  implícitas en el código.
- Los documentos se actualizan cuando cambia la realidad del proyecto, no al
  final. Un documento desactualizado es peor que no tenerlo.

## Fases y criterio de avance

1. **Descubrimiento** → se cierra cuando las hipótesis críticas están validadas o
   descartadas con evidencia de usuarios reales.
2. **Producto** → se cierra cuando el alcance del MVP está congelado por escrito.
3. **Diseño** → se cierra cuando los flujos principales están resueltos en
   wireframes.
4. **Arquitectura** → se cierra cuando el modelo de datos y el contrato de API
   están definidos.
5. **Construcción** → API primero, luego web, luego móvil.
