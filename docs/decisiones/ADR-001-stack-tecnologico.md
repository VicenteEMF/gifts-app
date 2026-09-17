# ADR-001: Stack tecnológico

- **Fecha:** 2026-09-17
- **Estado:** Aceptada
- **Decide:** Vicente

---

## Contexto

El producto debe estar disponible en web y en móvil. El proyecto tiene dos
objetivos declarados: ser una pieza de portafolio que amplíe el perfil
profesional, y aprender tecnologías con demanda de mercado.

Experiencia previa del desarrollador: NestJS, Prisma, MySQL, Angular. El stack
elegido debe agregar tecnologías nuevas sin multiplicar el riesgo de que el
proyecto quede inconcluso.

## Decisión

| Capa | Elección | Situación |
|---|---|---|
| API | NestJS + Prisma | Ya conocido |
| Base de datos | PostgreSQL | Nuevo (venía de MySQL) |
| Web | React con Next.js | Nuevo |
| Móvil | React Native con Expo | Nuevo |
| Repositorio | Monorepo con tipos compartidos | Nuevo |

Una sola API atiende a los dos clientes. El modelo de datos y los tipos se
comparten para evitar duplicación de contratos.

## Alternativas consideradas

**Angular para la web.** Descartada: ya está en el portafolio y no agrega
aprendizaje. La decisión aquí es deliberadamente de aprendizaje, no de eficiencia.

**Flutter para móvil.** Es una opción válida y con demanda, pero implica aprender
Dart como ecosistema separado. React Native reutiliza React y TypeScript del lado
web, concentrando el aprendizaje en un solo ecosistema.

**Backend nuevo (otro lenguaje o un BaaS tipo Supabase).** Descartada por ahora:
concentrar el aprendizaje en el frontend permite avanzar más rápido en la parte
visible del producto, que es la que se muestra en un portafolio. Mantener NestJS
también permite ejercer control fino sobre las reglas de visibilidad de las
reservas, que es el punto técnicamente más interesante del proyecto.

**Mantener MySQL.** Descartada: PostgreSQL es un cambio de bajo costo que amplía
el perfil y es muy solicitado.

## Consecuencias

### Positivas

- Suma React, Next.js, React Native y PostgreSQL al perfil.
- Un mismo lenguaje (TypeScript) en las tres capas.
- El backend, al ser terreno conocido, reduce el riesgo de bloqueo total.

### Negativas y riesgos

- Curva de aprendizaje simultánea en varias tecnologías nuevas.
- El monorepo agrega complejidad de configuración desde el inicio.
- React Native introduce una capa de problemas propios (compilación, entorno
  nativo, publicación) que no existe en web.

### Mitigación

Orden de construcción estricto: **API → web → móvil**. No se inicia el cliente
móvil hasta que la web esté funcional y desplegada. Si el tiempo se agota, el
proyecto queda igualmente presentable con la web.

## Nota sobre versiones

Las versiones de Next.js, Expo, React Native y las herramientas de monorepo
cambian con frecuencia y sus guías de configuración quedan obsoletas rápido. La
instalación debe hacerse siguiendo la documentación oficial vigente al momento de
iniciar, no tutoriales de terceros. Las versiones exactas utilizadas se registran
en este documento cuando se inicialice el repositorio.

## Pendiente de registrar

- Versiones exactas de cada dependencia principal.
- Herramienta de monorepo finalmente utilizada.
- Proveedor de infraestructura para la API y la base de datos.
