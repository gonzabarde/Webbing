# CAPTURE BASELINE — PLANTILLA (v1.2)

> Artefacto obligatorio al entregar (GATE 13.4-E). No es módulo de routing.
> Webbing vende sistemas de captación: sin baseline no hay prueba de valor,
> referidos con evidencia, ni calibración de precios (M13.0A señal 2).
> Copiar una instancia por cliente; vincular desde `Client_Record_Template.md`.

---

## CABECERA

| Campo | Valor |
|-------|-------|
| **Cliente** | |
| **Proyecto / URL live** | |
| **Fecha de entrega (baseline)** | |
| **Responsable Webbing** | |
| **Contacto cliente (quien reporta números)** | |

## MÉTRICA PRINCIPAL (elegir UNA)

Marcar la métrica acordada en kickoff o entrega. Debe ser legible sin ambigüedad.

```
[ ] Reservas / turnos atribuibles al sitio (por semana o mes)
[ ] Consultas por WhatsApp desde el sitio (por semana o mes)
[ ] Formularios / leads del formulario principal
[ ] Llamadas / clics en teléfono desde mobile
[ ] Pedidos / checkout completados
[ ] Otra: _______________ (definir exactamente qué cuenta)
```

**Métrica elegida:** _______________

**Definición operativa** (qué cuenta y qué NO):
> Ej: "Reservas confirmadas vía widget de Turnos en el sitio, no walk-ins ni teléfono directo."

### PRUEBA DE COHERENCIA MÉTRICA ↔ FUENTE (v1.2 — OBLIGATORIA, de Calibre N-2)

No alcanza con que la métrica y la fuente estén ambas documentadas. Hay que
declarar que **la fuente PUEDE medir la métrica tal como está definida**.

**REGLA DEL CALIFICADOR:** si el nombre de la métrica lleva un adjetivo que
restringe qué cuenta —"calificadas", "atribuibles", "nuevas", "confirmadas",
"orgánicas"— ese adjetivo necesita **definición operativa Y un mecanismo real que
lo produzca**. Si no existe el mecanismo, hay dos salidas honestas y ninguna
tercera:
  (a) construir el mecanismo (un campo, un criterio, un paso de calificación), o
  (b) **quitar el adjetivo del nombre de la métrica.**
Un calificador sin mecanismo es una promesa que el dato no puede cumplir, y se va
a reportar igual como si la cumpliera.

```
[ ] Verificado: la fuente mide exactamente lo que la métrica declara.
[ ] Si la métrica lleva calificador → mecanismo que lo produce: _______________
    (o marcar: calificador RETIRADO del nombre por no existir mecanismo)
```

> **Caso que originó la regla (Calibre, 2026-07-18):** la métrica declaraba
> *"solicitudes de demo CALIFICADAS / mes"* y la fuente era la tabla de leads
> filtrada por `source='web_demo'` — que registra **todo envío del formulario**.
> Nada calificaba un lead: sin criterio, sin campo, sin paso. GATE 13.4-E se dio
> por pasado verificando que métrica, fuente y baseline EXISTIERAN. El resultado
> habría sido reportar envíos crudos como leads calificados.
>
> Misma familia que el riesgo de sobre-atribución del TIPO DE PUNTO DE PARTIDA:
> un número destinado a ser prueba de valor que mide algo distinto de lo que su
> nombre promete. Y con la misma consecuencia aguas abajo — vía M13.0A señal 2,
> contamina la calibración de precios de toda la agencia.

## FUENTE DEL DATO

| Campo | Valor |
|-------|-------|
| Herramienta | GA4 / panel reservas / WhatsApp Business / MP / hoja del cliente |
| Quién lee el número | cliente / Webbing / ambos |
| Frecuencia de lectura | semanal / mensual |
| Acceso Webbing | sí / no — cómo se accede |

## TIPO DE PUNTO DE PARTIDA (v1.1 — OBLIGATORIO, elegir uno)

"Desde cero" no significa lo mismo en los tres casos. Elegir mal acá invalida
toda la prueba de valor de abajo.

```
[ ] (A) SIN DEMANDA PREVIA — negocio nuevo o sin operación real todavía.
        Crecer desde 0 SÍ es captación nueva.
[ ] (B) CON DEMANDA PREVIA NO ATRIBUIDA — el negocio ya opera y capta por canales
        que nadie mide (Instagram, DM, boca en boca, walk-in, teléfono, reseñas).
        Crecer desde 0 atribuible NO es, por sí solo, captación nueva.
[ ] (C) CON DEMANDA PREVIA MEDIDA — había sitio instrumentado con historial real.
        Hay baseline verdadero y el lift es medible por diferencia.
```

**Tipo elegido:** _______________

> ⚠️ **El caso (B) es el más común en PyME local y el más fácil de reportar mal.**
> Ej. Silvana Dato: 1067 reseñas, Instagram activo, mucha demanda real — y **cero**
> de ella medida o atribuible al sitio. Si a los 90 días se reporta "20 turnos/mes
> desde el sitio, desde baseline 0" como captación **nueva**, se le está
> adjudicando al sitio la demanda que ya traía Instagram.

## BASELINE (al entregar)

| Campo | Valor |
|-------|-------|
| **Número baseline (atribuible al sitio)** | |
| **Período** | ej. "promedio últimas 4 semanas pre-launch" o "desde cero atribuible" |
| **DEMANDA TOTAL ACTUAL (T0)** — obligatorio si el tipo es (B) | consultas/turnos por semana **por TODOS los canales**, aunque sea estimado por el cliente |
| **Cómo se obtuvo el T0** | preguntado al cliente / recepción / agenda / no disponible |
| **Notas** | estacionalidad, campaña activa, datos incompletos |

> **Cómo se pregunta el T0** (una sola pregunta, en kickoff o entrega):
> *"¿Cuántas consultas o turnos por semana manejás hoy, contando todos los canales
> — Instagram, WhatsApp, teléfono, gente que cae?"* No hace falta precisión: hace
> falta un orden de magnitud registrado ANTES de entregar.
>
> **Si el cliente no lo puede dar:** marcar "no disponible" y asumir el límite —
> sin T0 nunca se puede afirmar que el sitio generó demanda nueva, solo que hay
> N atribuibles al sitio. Es una limitación declarada, no un permiso para inferir.

## META ACORDADA

| Horizonte | Meta | Notas |
|-----------|------|-------|
| 30 días | | |
| 60 días | | |
| 90 días | | |

**Éxito a 90 días** (una frase, acordada con el cliente):
> Ej: "Al menos 20 reservas/mes atribuibles al sitio, vs baseline de 8."

## CHECK-INS (parte del retainer M13.4-C)

Medir **DOS** números, no uno. El atribuible solo no distingue captación nueva de
re-atribución; el total sí. Es la única forma barata de saber cuál de las dos pasó.

| Fecha | (1) Atribuible al sitio | (2) Total todos los canales | vs baseline | vs meta | Acción si bajo |
|-------|------------------------|------------------------------|-------------|---------|----------------|
| +30 días | | | | | |
| +60 días | | | | | |
| +90 días | | | | | |

**CÓMO SE LEE LA COMBINACIÓN (v1.1):**

| Total (2) | Atribuible (1) | Qué pasó realmente |
|-----------|----------------|--------------------|
| **Sube** | Sube | **CAPTACIÓN NUEVA** — el sistema amplió la demanda. Es el resultado que justifica subir el ancla de precio |
| **Plano** | Sube | **RE-ATRIBUCIÓN** — el sistema formalizó demanda que ya existía. Valor real, pero de otra clase (ver abajo) |
| **Baja** | Sube o plano | Problema externo (estacionalidad, mercado, algo del negocio). Mirar aparte antes de sacar conclusiones del sitio |

## QUÉ SE PUEDE Y QUÉ NO SE PUEDE AFIRMAR (v1.1)

**La re-atribución NO es valor falso.** Formalizar demanda que estaba dispersa en
DMs y llamadas tiene valor propio y reportable: menos fricción para el cliente
final, menos leads que se pierden, menos tiempo administrativo del negocio, y por
primera vez datos para decidir. Se reporta **como lo que es**.

Lo prohibido es una cosa sola: **presentar re-atribución como demanda nueva.**

- ✅ "Entran 20 turnos/mes por el sitio, que antes se manejaban a mano por DM."
- ✅ "El total del negocio pasó de ~30 a ~38 consultas/semana; 20 llegan por el sitio."
- ❌ "El sitio generó 20 clientes nuevos por mes." (si el total no se movió)

**Impacto en el precio (crítico):** M13.0A señal 2 habilita subir el ancla del Core
y del Recurrente sobre *resultado medido*. Solo la **captación nueva** —o una mejora
de conversión demostrable— habilita esa suba. **La re-atribución sola no.** Calibrar
precios sobre re-atribución leída como demanda nueva es construir el pricing de toda
la agencia sobre una señal falsa.

## USO DEL NÚMERO (obligatorio si es bueno)

- [ ] Referido pedido a cliente (M18 loop) — fecha:
- [ ] Caso de portfolio actualizado con resultado (M18 orgánico)
- [ ] Evidencia para calibrar precio Core/Recurrente (M13.0A)
- [ ] Input M14 eje 6 (resultado de negocio)

## SI NO CAPTA A 60-90 DÍAS

No es dato a esconder. Registrar causa hipótesis (una línea):
- Tráfico / mensaje / oferta / fricción en el path / métrica mal elegida / otro

**Próximo paso acordado con el cliente:**

---

**GATE 13.4-E:** sin este documento completo (métrica + fuente + **prueba de
coherencia métrica↔fuente** + baseline + TIPO DE PUNTO DE PARTIDA, y el T0 de
demanda total si el tipo es (B)), el proyecto no se da por cerrado.

Que los campos EXISTAN no basta: el gate verifica que la fuente pueda medir la
métrica declarada y que el punto de partida esté bien tipificado. Un baseline
completo en la forma pero incoherente en el fondo pasa el gate y falla el trabajo.
