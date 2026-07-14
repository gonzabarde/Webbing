# WEBBING — PORTFOLIO REGISTRY

> Fuente de verdad centralizada para el Principio 10 entre-clientes (anti
> house-style). CDL-5 (Verificación de Diferenciación de Portfolio) lee ESTE
> archivo primero. Si un proyecto no está listado acá todavía, recién ahí
> hace fallback a grepear `_webbing/<proyecto>/` o el código real.

**Quién escribe acá:** M2 (arquetipo/voz), M3 (tipografía), M5 (paleta + firma),
M4 (nombre de concepto) y CDL-1 (esqueleto/orden de secciones) agregan o
actualizan la fila de su proyecto AL CERRAR esa decisión — no al final del
proyecto. Un
proyecto puede tener fila parcial mientras está en curso (ej. tipografía
cerrada, paleta todavía no). Marcar `—` en lo que falte, nunca inventar.

**Regla de honestidad:** si un dato no se pudo verificar contra la fuente
real (código, no memoria ni transcripción), se marca `NO VERIFICADO` en vez
de completarlo. Un campo vacío o marcado es más seguro que uno inventado.

**Regla de trazabilidad (agregada 2026-07-13, tras INC-1 de Cursor Café):**
ninguna celda pasa de `—` a un valor sin citar el archivo
`_webbing/<proyecto>/Mx_*.md` que la cerró. Sin fuente citable, la celda
queda en `—` / NO VERIFICADO, aunque el dato "parezca" correcto. Un
registro auto-poblado sin fuente puede auto-validarse a sí mismo — pasó
una vez, casi no se detecta (CDL-5 lee este archivo ANTES de re-verificar
contra código). Trazabilidad, no confianza.

**Regla de exclusión propia:** al correr el cross-check de M3/M5/CDL-5 para
UN proyecto, la fila de ESE MISMO proyecto en este registro NUNCA cuenta
como evidencia contra la cual comparar — una fila propia no puede validar
una decisión que el proyecto todavía no tomó. Comparar únicamente contra
las filas de OTROS clientes.

--------------------------------------------------------------------------------

## REGISTRO

| Cliente | Arquetipo (proyecto) | Arquetipo de marca (M2, principal+secundario) | Tipografía (display / body) | Paleta (rol: hex) | Concepto rector | Firma / gesto | Esqueleto (orden) |
|---|---|---|---|---|---|---|---|
| **Move On Argentina v2** | #2 Lead alta-consideración | NO VERIFICADO | Big Shoulders Display / Onest | naranja(acento) `#F07B24` · azul(estructura) `#2B85D4`/`#1A6BBF` · celeste `#5CB1D5` · sol `#FBB915` · tinta `#0D0D0D` | "Cuerpo y cabeza, hecho a mano" | "La línea de amanecer" (diagonal naranja↔azul) | Hero → Diferenciador anti-app → Coaches → Método → Servicios → Caminantes → Planes → Prueba → FAQ → CTA final → Footer |
| **VINCA** | #6 Producto (app-shell) | **Protector + Guía** | Fraunces / Geist | off-white `#F6F3EE` · verde salvia(primario) `#2E4B3F` · terracota(acento, solo acción) `#C4633B` | "Papel y sistema" | Fraunces en momentos de marca + base cálida + acento terracota solo en acción | App-shell: auth → onboarding de tenant → core loop (agenda/ficha/cobro/panel) |
| **Runa** | #2 Lead alta-consideración (marketing) + #6 (dashboard) | NO VERIFICADO | Bricolage Grotesque / Instrument Sans (+ Spline Sans Mono para cifras) | papel `#FAF7F1` · tinta `#1C1B18` · naranja tinta quemada(acento único) `#C24E14` · gris cálido `#6B675F` | NO VERIFICADO (no confirmado contra `docs/M4_Concept.md` en esta pasada) | "El rayado" (línea contable estructural) + "La cifra" (números en mono tabular) | Definido por IA Spec de CDL-1, no fijo en M5 (marketing SaaS estándar: promesa→demostración→prueba→oferta→objeciones→CTA) |
| **ECOS** | Híbrido (experiencial + transaccional, documentado en M5 como tensión que CDL-1 formaliza) | NO VERIFICADO | Fraunces / General Sans | near-black cálido `#161311`/`#1E1A16` · off-white cálido `#EDE6DA` · ámbar(acento único) `#E8853A` | "Penumbra de cemento resonante" | "La reverberación" (ondas concéntricas que decaen) | Dos registros: experiencial (hero atmosférico→obra→espacio→prueba→CTA bajo compromiso) + transaccional (ecommerce: precio/disponibilidad/checkout) |
| **Estudio Contable v2** | Mixto (marketing Ligera + portal auth Media) | NO PERSISTIDO (P2) | Fraunces / Inter | paper `#f6f4ee` · ink `#1c1b19` · **pine(primario)** `#12513c` · ochre(acento) `#c08a3e` | **NO PERSISTIDO** — sesión no escribió a disco (CHANGELOG 2026-07-10, P2). Reconstruido solo parcialmente vía auditoría externa. | NO VERIFICADO | NO VERIFICADO |
| **Vera Arquitectura** | Mixto (#4 Brand Experience + #6 Portal cliente) | **Artesano + Protector** (terciario: Editor) | Newsreader / Schibsted Grotesk (Mona Sans planeado, descartado por buildability — ver `_webbing/INCIDENTES_M14.md` #1 y CHANGELOG P4) | yeso/piedra frío `#E9E8E3` · grafito `#191C1E` · azul de plano(acento) `#2C4A5C` | "Obra Abierta" | "Plano Habitado" (reveal plano técnico → fotografía de materia) | Hero → Work (grid de obras) → Process ("Open work") → Studio (dos arquitectos) → Contact/Footer |
| **CUORE** | — | NO VERIFICADO | NO VERIFICADO | NO VERIFICADO | NO VERIFICADO | NO VERIFICADO | NO VERIFICADO |
| **Glow Factor** | — | NO VERIFICADO | NO VERIFICADO | NO VERIFICADO | NO VERIFICADO | NO VERIFICADO | NO VERIFICADO |
| **Cursor Café** | #4 Brand Experience (híbrido con conversión real) — fuente: `_webbing/CDL_1_project_intelligence.md` | **Editor + Anfitrión** | Instrument Serif / Familjen Grotesk | vino tostado(fondo dominante, cromático) `#2B161B` · hueso rosado(contrafondo) `#F0E9E6` · ultramar POR ROL (INC-2/INC-4): `--ultramar #3A4FE0` (5.19:1, solo sobre hueso) · `--ultramar-luz #6B84FF` (5.16:1, la marca sobre vino) · `--escala #856C72` (3.56:1, gráfico) · `--escala-texto #997F85` (4.65:1, labels de texto) — fuente: `_webbing/M5_visual_direction.md` + `_webbing/INCIDENTES_M14.md` INC-2/INC-4 | "El Punto Exacto" — fuente: `_webbing/M4_concept.md` | "La Marca" (trazo ultramar que se posa sobre una escala muda — NO la línea: Runa/Move On ya la tienen). Motion: "Aterriza y calla" — fuente: `_webbing/M5_visual_direction.md` | Hero → Origen → Proceso → Catálogo → **El Club (crítica, 5/7)** → El Local → Footer — fuente: `_webbing/CDL_1_project_intelligence.md` |

--------------------------------------------------------------------------------

## HALLAZGO ABIERTO #2 — arquetipo de marca compartido (M2, sin chequeo hasta hoy)

**"Protector" aparece en VINCA (principal) y en Vera Arquitectura (secundario).**
No es un clón exacto (VINCA = Protector+Guía; Vera = Artesano+Protector+Editor),
pero es exactamente el tipo de colisión que M2 nunca chequeó hasta que se
agregó el árbol #8 (2026-07-11). Con solo 8 arquetipos en la guía de M2 y un
portfolio que crece, la repetición es matemáticamente esperable. No se
corrige retroactivamente en estos dos proyectos (ambos de práctica, VINCA ya
cerrado) — queda documentado para que la próxima corrida de M2 lo evite.

--------------------------------------------------------------------------------

## HALLAZGO ABIERTO — no resuelto por este registro, solo documentado

**"Crema/papel cálido + verde tipo pino + acento cálido único" apareció TRES
veces**, dos de ellas a través de Webbing:
1. VINCA (oficial, verde salvia `#2E4B3F` + terracota) — el original.
2. estudio-contable v1 (NO-Webbing, `frontend-design`) — clón confirmado el
   2026-07-09 (ver CHANGELOG), motivó el hallazgo original de la sesión.
3. **estudio-contable-v2 (SÍ Webbing, verde pino `#12513c` + ochre)** —
   confirmado recién al poblar este registro, el 2026-07-11. Predata el
   chequeo cross-portfolio de M5 (agregado procesando la corrida de Vera) —
   no es un fallo del mecanismo, es evidencia de antes de que existiera.

No se corrige acá — el proyecto es de práctica, sin GATE 4. Queda anotado
para que la próxima vez que alguien abra estudio-contable-v2 (o lo use de
referencia) sepa que su paleta colisiona con VINCA.

--------------------------------------------------------------------------------

## Mantenimiento

Actualizar la fila del proyecto correspondiente al cerrar M3 (tipografía),
M5 (paleta + firma), M4 (concepto) o CDL-1 (esqueleto). No esperar al final
del proyecto. Si CDL-5 encuentra una colisión al leer este archivo, cita la
fila exacta que colisiona — no re-describe todo el registro.

Proyectos ausentes de este registro (construidos antes de que existiera):
CUORE, Glow Factor. Si se vuelve a trabajar sobre alguno, poblar su fila
verificando contra el código real antes de usarlo como referencia.
