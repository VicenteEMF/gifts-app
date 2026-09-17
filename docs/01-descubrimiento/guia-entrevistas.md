# Guía de entrevistas de validación

**Objetivo:** obtener evidencia real sobre las hipótesis H1 a H5 antes de
escribir código.
**Última actualización:** 2026-09-17

---

## 1. Principio de la entrevista

No se pregunta si la app gustaría. Se pregunta por **comportamiento pasado y
concreto**. La gente miente por cortesía cuando se le pregunta por el futuro:
casi todos dicen "sí, la usaría" y luego no la usan. En cambio, lo que ya hizo la
semana pasada es un dato.

Este enfoque está desarrollado en *The Mom Test*, de Rob Fitzpatrick (2013), que
es una referencia real y recomendable si quieres profundizar.

### Reglas

1. No describas la app antes de escuchar. Si la mencionas primero, el resto de la
   conversación queda contaminado.
2. Pregunta por el último caso real, con fechas y detalles.
3. Busca dolor, esfuerzo y dinero ya gastado, no opiniones.
4. Acepta el silencio. La respuesta útil suele venir después de la pausa.
5. Anota citas literales, no tus interpretaciones.

## 2. A quién entrevistar

Entre 6 y 10 personas, cubriendo ambos lados:

- 3 a 5 personas que hayan regalado algo en los últimos 3 meses.
- 3 a 5 personas que hayan cumplido años o casado recientemente.
- Idealmente al menos 2 personas de más de 40 años, para detectar si el
  comportamiento cambia por edad.

Evita entrevistar solo a amigos cercanos o compañeros de informática: tienden a
validar por afecto y por sesgo técnico.

Duración sugerida: 15 a 25 minutos. Una entrevista breve y honesta vale más que
una larga y complaciente.

## 3. Bloque A — Quien regala (H1, H2, H4)

Apertura neutra: "Estoy investigando cómo la gente elige regalos, no te voy a
vender nada."

1. Cuéntame del último regalo que hiciste. ¿Para quién y por qué ocasión?
2. ¿Cómo decidiste qué regalar? Llévame paso a paso.
3. ¿Cuánto tiempo te tomó decidir? ¿Cuándo empezaste a pensarlo?
4. ¿Qué fue lo más difícil de esa decisión?
5. ¿Averiguaste algo antes de comprar? ¿A quién le preguntaste?
6. ¿Alguna vez te pasó que la persona ya tenía el regalo, o que otro regaló lo
   mismo? ¿Qué hiciste?
7. ¿Alguna vez te equivocaste en la talla? ¿Qué pasó después?
8. ¿Cómo te enteraste de qué quería esa persona, si te enteraste?

Señales a detectar: descripciones de esfuerzo real, workarounds inventados
(grupos de WhatsApp, capturas de pantalla, preguntar a la mamá), o compras que
terminaron mal.

## 4. Bloque B — Quien recibe (H3, H5)

1. Cuéntame de tu último cumpleaños. ¿Qué regalos recibiste?
2. ¿Hubo alguno que no usaste? ¿Qué pasó con él?
3. ¿Alguien te preguntó antes qué querías? ¿Cómo respondiste?
4. Si un familiar te pregunta qué quieres, ¿qué le dices exactamente?
5. ¿Le has mandado a alguien un link o una foto de algo que querías? ¿En qué
   situación?
6. ¿Cómo te sentirías si tus gustos y tallas estuvieran anotados en algún lado
   para que tu familia los consulte?
7. ¿Habría algo de eso que no querrías que se viera? ¿Quién sí y quién no debería
   poder verlo?

La pregunta 6 es la que toca H3 y H5. Presta atención al lenguaje corporal y a
las dudas, no solo a la respuesta.

## 5. Bloque C — Solo al final

Recién aquí puedes describir la idea en una o dos frases y observar la reacción.
No cuentes como validación lo que digan aquí; sirve solo para detectar
malentendidos del concepto.

Preguntas de cierre útiles:

- ¿Conoces a alguien que tenga este problema más fuerte que tú? ¿Me lo
  presentarías?
- ¿Hay algo que no te pregunté y que debería haber preguntado?

## 6. Plantilla de registro

Crear un archivo por entrevista en `01-descubrimiento/entrevistas/`:

```markdown
# Entrevista NN

- Fecha:
- Perfil (edad aproximada, ocupación, relación contigo):
- Lado: regala / recibe / ambos

## Último caso concreto

## Citas literales

## Workarounds que ya usa

## Evidencia por hipótesis
- H1 (incertidumbre al elegir): apoya / contradice / no surgió
- H2 (duplicados y regalos sin uso): apoya / contradice / no surgió
- H3 (disposición a publicar deseos): apoya / contradice / no surgió
- H4 (rechazo al registro): apoya / contradice / no surgió
- H5 (tallas como dato aceptable): apoya / contradice / no surgió

## Sorpresas (algo que no esperabas escuchar)
```

El campo de sorpresas es el más valioso. Si en 8 entrevistas no te sorprendió
nada, probablemente estabas preguntando para confirmar en vez de para aprender.

## 7. Criterio de decisión

Antes de empezar, define qué resultado te haría cambiar de rumbo. Si no lo
defines antes, vas a interpretar cualquier resultado como favorable.

Propuesta:

- **Si la mayoría muestra incomodidad al publicar deseos (H3 falsa):** mantener
  el proyecto, pero reencuadrar el perfil como "mis gustos y tallas" y despriorizar
  las listas explícitas.
- **Si nadie recuerda casos de duplicación (H2 falsa):** la reserva pasa de
  función central a función secundaria, y el foco se mueve a acertar el gusto.
- **Si el registro es una barrera clara (H4 verdadera):** el acceso por link sin
  cuenta se vuelve requisito del MVP, con sus implicancias de seguridad.
- **Si no aparece dolor en ningún lado:** el proyecto sigue como pieza de
  portafolio, con esa conclusión documentada honestamente. Documentar que una
  hipótesis se cayó es una señal de madurez profesional, no un fracaso.

## 8. Resultados

Pendiente. Completar con la síntesis una vez realizadas las entrevistas.
