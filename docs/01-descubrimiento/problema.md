# Problema y solución propuesta

**Estado del documento:** borrador. Contiene hipótesis sin validar.
**Última actualización:** 2026-09-17

---

## 1. Contexto

Regalar es una práctica social frecuente y con fechas predecibles: cumpleaños,
Navidad, matrimonios, amigo secreto, nacimientos, graduaciones. Quien regala
quiere acertar; quien recibe quiere algo que realmente use. Hoy la información
necesaria para que eso ocurra (gustos, tallas, lo que ya tiene) no está
disponible de forma ordenada, y se transmite por conversaciones indirectas.

## 2. Problema

Cuando una persona quiere hacer un regalo, normalmente no sabe qué quiere quien
lo recibe ni cuál es su talla. Las salidas habituales son:

- Preguntar indirectamente, arriesgando arruinar la sorpresa.
- Preguntarle a un tercero cercano, que tampoco tiene información precisa.
- Adivinar, con riesgo de error de talla o de gusto.
- Regalar algo genérico o dinero, lo que reduce el valor simbólico del gesto.

A esto se suma un problema de coordinación: cuando varias personas regalan a la
misma persona en la misma fecha, **no hay forma de saber qué ya compró otro**, y
se producen regalos duplicados.

### Consecuencias observables (a verificar)

- Regalos que no se usan.
- Prendas de talla equivocada que hay que cambiar.
- Tiempo perdido buscando opciones sin criterio.
- Duplicaciones en celebraciones con varios invitados.

## 3. Usuarios objetivo

El producto tiene **dos lados**, con motivaciones distintas. Es importante no
diseñar solo para uno.

### Lado A — Quien regala

- Necesita: certeza, rapidez, no quedar mal.
- Fricción principal esperada: no quiere crear una cuenta ni aprender una app
  nueva para resolver algo puntual.
- Momento de uso: días antes de la fecha, a veces horas antes.

### Lado B — Quien recibe

- Necesita: recibir algo que sirva, sin sentir que está pidiendo cosas.
- Fricción principal esperada: incomodidad social al publicar deseos.
- Momento de uso: al crear o actualizar su perfil y sus listas.

**Segmento inicial propuesto para validar:** personas de 18 a 35 años en Chile,
con uso habitual de redes sociales y compra online. Es una acotación de trabajo,
no una conclusión de mercado.

## 4. Hipótesis

Ninguna está validada. Cada una necesita evidencia de usuarios reales antes de
construir sobre ella.

| ID | Hipótesis | Riesgo si es falsa | Estado |
|---|---|---|---|
| H1 | Quien regala siente incertidumbre o estrés al elegir y valoraría una guía. | Medio: sin dolor, no hay razón para usar la app. | Sin validar |
| H2 | Los regalos repetidos o que no se usan son un problema frecuente. | Medio: la función de reserva perdería valor. | Sin validar |
| H3 | Las personas están dispuestas a publicar lo que quieren recibir. | **Alto: sin listas publicadas, el producto no existe.** | Sin validar |
| H4 | Quien regala no quiere registrarse solo para ver o reservar en una lista. | Alto: define toda la arquitectura de autenticación y permisos. | Sin validar |
| H5 | Compartir tallas se percibe como útil y no como invasivo. | Medio: obliga a repensar el perfil y su privacidad. | Sin validar |

### Nota sobre H3

Es la hipótesis más riesgosa del proyecto. En algunos contextos culturales,
publicar deseos abiertamente puede percibirse como interesado o poco elegante.
Si la evidencia apunta en esa dirección, el producto debe reencuadrarse: en vez
de "pide tus regalos", presentarse como "mis gustos y tallas", donde la persona
comparte información sobre sí misma y quien regala la interpreta. Es un cambio de
marco, no de funcionalidad.

## 5. Solución propuesta

Una plataforma (web y móvil) donde cada persona mantiene un perfil con sus
gustos, tallas e intereses, y listas asociadas a ocasiones. Sus cercanos pueden
ver esa información y **reservar** un regalo, de modo que:

- El resto de los invitados ve qué está tomado y evita duplicar.
- La persona homenajeada **no** ve las reservas, preservando la sorpresa.

### Fuera de alcance (decisión inicial)

- Venta o pago dentro de la plataforma.
- Integración con catálogos de tiendas.
- Recomendaciones automáticas de regalos.

Se excluyen para mantener el MVP construible. Pueden reevaluarse después.

## 6. Competencia

Existen productos con propósito similar en el mercado internacional, entre ellos
Giftster y Elfster, además de las listas de deseos de Amazon. En Chile, algunas
tiendas grandes ofrecen listas de novios acotadas a su propio catálogo.

**Pendiente de verificar:** funcionalidades actuales de cada uno, si permiten
tallas, si están disponibles en español y si se usan en Chile. No hay datos
verificados de adopción local; la percepción de que "nadie usa algo así en Chile"
es una impresión, no un dato de mercado.

## 7. Diferenciadores candidatos

- Perfil con tallas estructuradas, no solo una lista de links.
- Enfoque en el mercado chileno: idioma, precios en CLP, tiendas locales.
- Reserva sin registro obligatorio, si H4 se confirma.
- Privacidad y protección de datos como característica visible del producto.

## 8. Consideración legal

El producto almacena datos personales (tallas, intereses, relaciones entre
personas). Chile cuenta con una nueva ley de protección de datos personales
(Ley 21.719).

**Pendiente de verificar en fuente oficial** (Biblioteca del Congreso Nacional o
Diario Oficial): fecha exacta de entrada en vigencia y obligaciones concretas
aplicables a un servicio de este tipo. No construir sobre supuestos en este
punto.

Independiente del detalle legal, se adopta como principio de diseño: recolectar
el mínimo de datos necesario, privacidad por defecto y capacidad del usuario de
exportar y eliminar su información.

## 9. Riesgos principales del proyecto

| Riesgo | Descripción | Mitigación |
|---|---|---|
| Efecto red | La app solo sirve si ambos lados la usan. | Diseñar para que una sola persona pueda compartir su lista por link a gente sin cuenta. |
| Uso esporádico | Se usa pocas veces al año. | Aceptado: el objetivo primario es portafolio, no retención. |
| Incomodidad social (H3) | Publicar deseos puede sentirse mal. | Reencuadre del producto según evidencia de entrevistas. |
| Sobrealcance | Web + móvil + API simultáneos. | Orden estricto: API, luego web, luego móvil. |

## 10. Próximo paso

Validar H1 a H5 mediante entrevistas con usuarios reales de ambos lados.
Ver `guia-entrevistas.md`.
