# AUDITORÍA — B2 y B5, 2026-07-20

FUENTE ÚNICA de este documento: sí mismo (auditoría directa, no corrida de M14
sobre proyecto de cliente). No confundir con `Docs/M14_PROPOSAL_LOG.txt`, que
indexa retrospectivas de proyectos ficticios — B2 y B5 son módulos del sistema,
no un cliente. Mismo patrón que las auditorías de seguridad del sábado 18/7
(commits `sec:`), sin correr M14 sobre ellos.

## Contexto

B0, B1, B3, B4, B6 tenían auditoría formal (backend layer original de junio +
hardening de seguridad del 18/7, 12 commits `sec:`). B2 (pagos) nunca había
sido auditado. B5 (performance) tampoco tenía auditoría formal, pero **sí**
tenía una inserción de seguridad puntual del 18/7 (rate limiting, PERF-6).

**Verificación de integridad de PERF-6, previa a auditar:** `git diff 9af8730
-- BACKEND/B5_Performance_Scaling_Engine.txt` → vacío. El bloque PERF-6 sigue
byte a byte idéntico al commit del sábado. No se tocó en esta auditoría.

## Patrón buscado

El mismo que cerró 9 de 14 ítems de seguridad y el bug de GATE 4 con capturas
de pantalla: una regla existe en el módulo (como pregunta de gate, "¿...?")
pero no hay ningún método prescrito para verificarla EJECUTANDO. Un ítem así
puede leerse OK en revisión de código y fallar recién con datos/carga reales
— la misma clase que Calibre H-1 (build con TODOS los chequeos estáticos en
verde, cliente completamente muerto) y el bug de GRANT de Estudio Contable P1
(RLS habilitada, revisión de schema en verde, insert real fallando).

**Confirmado por grep antes de escribir cualquier hallazgo:** cero ocurrencias
de "EJECUTABLE" / "ejecutando" / "CÓMO SE VERIFICA" en B2 y en B5 (verificado,
no asumido — ver protocolo de auto-chequeo al final de este documento).

## Hallazgos

| ID | Severidad | Ítem | Estado |
|---|---|---|---|
| H-B2-1 | **Crítica** | PAY-3 (webhook vs. redirect), PAY-4 (idempotencia), ECOM-3 (stock atómico concurrente) sin verificación ejecutable | **APLICADO** — bloque "CÓMO SE VERIFICA (PAGOS)" en B2 v1.1 |
| H-B2-2 | Alta | PAY-7 (firma de webhook por PSP) sin verificación ejecutable por PSP | **APLICADO** — mismo bloque |
| H-B2-3 | Media | SAAS-2 (estado de suscripción → acceso) sin prueba de revocación ejecutada | **PENDIENTE** — no aplicado hoy |
| H-B2-4 | Baja | AFIP/facturación electrónica sin criterio de verificación ejecutable | **PENDIENTE** — no aplicado hoy |
| H-B5-1 | Alta | PERF-4 (N+1) sin método de detección ejecutable | **APLICADO** — bloque "CÓMO SE VERIFICA (CARGA)" en B5 v1.1 |
| H-B5-2 | Alta | PERF-8 (connection pooling serverless) sin verificación bajo concurrencia real | **APLICADO** — mismo bloque |
| H-B5-3 | Media | PERF-5 (paginación) sin método ejecutable | **PENDIENTE** — no aplicado hoy |
| H-B5-4 | Media | PERF-6 (rate limit): el módulo no prescribe el método que Calibre inventó ad hoc (N+1 requests, confirmar 429) | **PENDIENTE** — no aplicado hoy. Nota: gap de *completitud*, no de integridad — el texto del sábado está intacto |
| H-B5-5 | Baja | Budgets (PERF-9/10/11/12) sin forma ejecutable | **PENDIENTE** — declarativos, no comportamiento de código, prioridad baja |
| H-B5-6 | Baja | PERF-1 (invalidación de cache) sin verificación ejecutable | **PENDIENTE** — condicional; el propio módulo dice "empezar SIN cache" |

## Por qué H-B2-1 es Crítica y no Alta

B2 declara textualmente: "Falla cualquiera → no construir el cobro. Cada uno
de estos es plata real o fraude." Un gate que se aprueba sin ejecutar en los
tres ítems de mayor probabilidad de ocurrencia real (webhook-vs-redirect,
replay de evento, compra concurrente sobre última unidad) puede dar acceso
gratis, cobrar doble, o vender la misma unidad dos veces — con datos y plata
reales de un cliente, no de un proyecto de práctica. Calibra al mismo nivel
que Estudio Contable P1 (RLS sin GRANT, Crítica): ambos son "el gate dio OK
por diseño, no por ejecución, y el fallo real solo aparece con tráfico vivo".

## Diferidos — por qué NO se tocan hoy

Instrucción explícita: hoy es el último día antes del corte del 21/7, sin
margen para otra ronda. Los 6 diferidos (H-B2-3, H-B2-4, H-B5-3, H-B5-4,
H-B5-5, H-B5-6) son Media/Baja por diseño — ninguno es "plata real perdida
hoy mismo" ni "outage total sin aviso": son fugas lentas (revenue, paginación
sin tope) o ítems declarativos (budgets, completitud legal) que no compiten
en urgencia con los 4 aplicados. Quedan anotados acá, no en el código, para
que una corrida de M14 futura los levante sin tener que re-descubrirlos.

## PROTOCOLO DE AUTO-CHEQUEO (pedido explícito, mismo error que casi pasó con G4)

En la auditoría anterior (fixes de seguridad del sábado), un primer grep sobre
"G4" dio falso negativo porque esa etiqueta vive solo en el mensaje del commit,
no en el texto insertado. Antes de reportar los 4 fixes de hoy como aplicados,
se corrió el mismo chequeo: grep del patrón REAL insertado (no una etiqueta
asumida), contra el archivo después de la edición.

Resultado (ver también el bloque de verificación corrido en la sesión):
- B2: grep de `"Webhook como única fuente de verdad (PAY-3) \[EJECUTABLE\]"`,
  `"Idempotencia (PAY-4) \[EJECUTABLE\]"`, `"Stock atómico bajo concurrencia
  (ECOM-3, si aplica) \[EJECUTABLE\]"`, `"Firma de webhook por PSP (PAY-7"` —
  las 4 frases literales aparecen, 1 ocurrencia cada una.
- B5: grep de `"N+1 en listados con relaciones (PERF-4) \[EJECUTABLE\]"` y
  `"Connection pooling bajo concurrencia (PERF-8"` — ambas aparecen, 1
  ocurrencia cada una.
- Confirmado además que el header de versión cambió en ambos archivos (v1 →
  v1.1) y que el conteo total de `[EJECUTABLE]` subió de 0 a 5 en B2 y de 0 a
  2 en B5 — no solo que la frase exista, sino que sea la única inserción
  nueva (sin duplicados por un Edit corrido dos veces).
