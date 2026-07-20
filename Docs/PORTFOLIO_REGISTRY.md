# WEBBING — PORTFOLIO REGISTRY

> **FUENTE ÚNICA: este archivo** — para el Principio 10 entre-clientes (anti
> house-style). No es un índice de otra cosa: el estado consolidado del portfolio
> vive acá y en ningún otro lado. CDL-5 (Verificación de Diferenciación de
> Portfolio) lee ESTE archivo primero. Si un proyecto no está listado acá
> todavía, recién ahí hace fallback a grepear `_webbing/<proyecto>/` o el código
> real.
>
> Matiz que lo distingue de un registro primario puro (R1, 2026-07-19): sus
> CELDAS citan decisiones que se cerraron en documentos de proyecto. Por eso rige
> la REGLA DE TRAZABILIDAD de abajo — ninguna celda pasa de `—` sin citar el
> archivo que la cerró. Este archivo es la fuente del *consolidado*; cada celda
> es una cita verificable de su proyecto, nunca una afirmación sin origen.

**Quién escribe acá:** M2 (arquetipo/voz), M3 (tipografía), M5 (paleta + firma +
**dirección fotográfica**, agregado 2026-07-17), M4 (nombre de concepto) y CDL-1
(esqueleto/orden de secciones) agregan o actualizan la fila de su proyecto AL
CERRAR esa decisión — no al final del proyecto. **M9.8 (Signature Pattern
Library) agrega la combinación de patrones M9.1/M9.2 al cerrar, ya avanzado
el proyecto** — es la única columna que se puebla DESPUÉS de GATE 2, no antes
(ver HALLAZGO ABIERTO #3 sobre por qué CDL-5 no puede verificarla en su
propio paso). Un proyecto puede tener fila parcial mientras está en curso
(ej. tipografía cerrada, paleta todavía no). Marcar `—` en lo que falte,
nunca inventar.

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

**Regla de integridad de cita (agregada 2026-07-14, tras INC-1 de Estudio de
Tatuaje — 2da ocurrencia, más grave: la fila fantasma codificaba las DOS
colisiones exactas que ese proyecto había diseñado para evitar):** citar un
archivo no alcanza si el archivo no existe o no dice lo que la celda afirma.
Antes de confiar en una celda con fuente citada: (1) el path tiene que
resolver a un archivo real — un path a una carpeta inexistente es señal de
celda envenenada; (2) el valor de la celda tiene que aparecer, aunque sea
aproximado, en el contenido real de ese archivo — si el M5 real dice "sin
acento cromático" y la celda dice "acento cálido óxido", es conflicto
detectable sin criterio humano, no ambigüedad. Grep del valor contra el
archivo citado; cero coincidencias = celda sospechosa, tratar como NO
VERIFICADO pese a tener "fuente".

**Regla de exclusión propia:** al correr el cross-check de M3/M5/CDL-5 para
UN proyecto, la fila de ESE MISMO proyecto en este registro NUNCA cuenta
como evidencia contra la cual comparar — una fila propia no puede validar
una decisión que el proyecto todavía no tomó. Comparar únicamente contra
las filas de OTROS clientes.

--------------------------------------------------------------------------------

## REGISTRO

| Cliente | Arquetipo (proyecto) | Arquetipo de marca (M2, principal+secundario) | Tipografía (display / body) | Paleta (rol: hex) | Concepto rector | Firma / gesto | Esqueleto (orden) | Dirección fotográfica | Combinación de patrones (M9.1/M9.2) |
|---|---|---|---|---|---|---|---|---|---|
| **Move On Argentina v2** | #2 Lead alta-consideración | NO VERIFICADO | Big Shoulders Display / Onest | naranja(acento) `#F07B24` · azul(estructura) `#2B85D4`/`#1A6BBF` · celeste `#5CB1D5` · sol `#FBB915` · tinta `#0D0D0D` | "Cuerpo y cabeza, hecho a mano" | "La línea de amanecer" (diagonal naranja↔azul) | Hero → Diferenciador anti-app → Coaches → Método → Servicios → Caminantes → Planes → Prueba → FAQ → CTA final → Footer | — | — |
| **VINCA** | #6 Producto (app-shell) | **Protector + Guía** | Fraunces / Geist | off-white `#F6F3EE` · verde salvia(primario) `#2E4B3F` · terracota(acento, solo acción) `#C4633B` | "Papel y sistema" | Fraunces en momentos de marca + base cálida + acento terracota solo en acción | App-shell: auth → onboarding de tenant → core loop (agenda/ficha/cobro/panel) | — | — |
| **Runa** | #2 Lead alta-consideración (marketing) + #6 (dashboard) | NO VERIFICADO | Bricolage Grotesque / Instrument Sans (+ Spline Sans Mono para cifras) | papel `#FAF7F1` · tinta `#1C1B18` · naranja tinta quemada(acento único) `#C24E14` · gris cálido `#6B675F` | NO VERIFICADO (no confirmado contra `docs/M4_Concept.md` en esta pasada) | "El rayado" (línea contable estructural) + "La cifra" (números en mono tabular) | Definido por IA Spec de CDL-1, no fijo en M5 (marketing SaaS estándar: promesa→demostración→prueba→oferta→objeciones→CTA) | — | — |
| **ECOS** | Híbrido (experiencial + transaccional, documentado en M5 como tensión que CDL-1 formaliza) | NO VERIFICADO | Fraunces / General Sans | near-black cálido `#161311`/`#1E1A16` · off-white cálido `#EDE6DA` · ámbar(acento único) `#E8853A` | "Penumbra de cemento resonante" | "La reverberación" (ondas concéntricas que decaen) | Dos registros: experiencial (hero atmosférico→obra→espacio→prueba→CTA bajo compromiso) + transaccional (ecommerce: precio/disponibilidad/checkout) | — | — |
| **Estudio Contable v2** | Mixto (marketing Ligera + portal auth Media) | NO PERSISTIDO (P2) | Fraunces / Inter | paper `#f6f4ee` · ink `#1c1b19` · **pine(primario)** `#12513c` · ochre(acento) `#c08a3e` | **NO PERSISTIDO** — sesión no escribió a disco (CHANGELOG 2026-07-10, P2). Reconstruido solo parcialmente vía auditoría externa. | NO VERIFICADO | NO VERIFICADO | — | — |
| **Vera Arquitectura** | Mixto (#4 Brand Experience + #6 Portal cliente) | **Artesano + Protector** (terciario: Editor) | Newsreader / Schibsted Grotesk (Mona Sans planeado, descartado por buildability — ver `_webbing/INCIDENTES_M14.md` #1 y CHANGELOG P4) | yeso/piedra frío `#E9E8E3` · grafito `#191C1E` · azul de plano(acento) `#2C4A5C` | "Obra Abierta" | "Plano Habitado" (reveal plano técnico → fotografía de materia) | Hero → Work (grid de obras) → Process ("Open work") → Studio (dos arquitectos) → Contact/Footer | — | — |
| **CUORE** | — | NO VERIFICADO | NO VERIFICADO | NO VERIFICADO | NO VERIFICADO | NO VERIFICADO | NO VERIFICADO | — | — |
| **Glow Factor** | — | NO VERIFICADO | NO VERIFICADO | NO VERIFICADO | NO VERIFICADO | NO VERIFICADO | NO VERIFICADO | — | — |
| **Estudio Tatuaje (nombre TBD)** | #4 Brand Experience (3er #4 del portfolio — DIFF de esqueleto obligatorio vs Vera/Cursor en CDL-1) — fuente: `estudio-tatuaje-web/_webbing/M0_discovery.md` | **Artesano + Pionero** (Artesano adyacente a Vera-secundario, evaluado; Pionero fresco) — fuente: `estudio-tatuaje-web/_webbing/M2_brand_translation.md` | **Archivo (Expanded/Black) / Hanken Grotesk** — grotesque sin serif: diferenciación vs registro oscuro-serif de ECOS/Cursor — fuente: `estudio-tatuaje-web/_webbing/M3_typography_semiotics.md` | **SIN acento cromático — el acento es LA LUZ.** near-black neutro `#141516` · hueso `#EDECEA` (15.49:1) · sec `#A6A6A3` · borde-ctrl `#666663` (3.17:1) · B&N monocromo + grano — medidos §2.4.5 — fuente: `estudio-tatuaje-web/_webbing/M5_visual_direction.md` | "El Taller a Oscuras" — fuente: `estudio-tatuaje-web/_webbing/M4_concept.md` | "La luz rasante" (gradiente que revela desde el negro — NO marca/línea/onda/plano/superposición). Motion: "La luz recorre" — fuente: `estudio-tatuaje-web/_webbing/M5_visual_direction.md` | Umbral → La Obra (pocas piezas, NO grilla) → El Oficio → El Autor → La Consulta (por referencia, crítica 5/6) → Footer — fuente: `estudio-tatuaje-web/_webbing/CDL_evaluation_GATE2.md` | — | — |
| **SAVIA** (cosmética natural D2C — **proyecto de práctica / stress test, sin GATE 4**) | **#1 Transacción-first (PRIMER #1 del portfolio)** — fuente: `savia-web/_webbing/CDL_1_project_intelligence.md` | **Editor + Experto** (Editor adyacente a Cursor Café-principal: evaluado y diferenciado por secundario + voz, ver árbol #8) — fuente: `savia-web/_webbing/M2_M4_M5_iteracion2.md` | **Gambetta / Public Sans** — descartadas por sobreuso de portfolio: Fraunces (4º uso), Instrument Serif, Newsreader, Archivo, Inter — fuente: `savia-web/_webbing/M1_M2_M3_estrategia.md` | **SIN verde (regla dura: uniforme de categoría + portfolio).** papel frío `#EEEFEC` · tinta `#15171A` (15.8:1) · gris frío `#5E646B` (5.4:1) · línea `#C9CCC8` · **índigo (acento único, marca LO VERIFICABLE — no "solo acción": ese era el mecanismo de VINCA)** `#1F3BAF` (9.1:1) — fuente: `savia-web/_webbing/M4_M5_creatividad.md` | **"El Reverso Adelante"** (el INCI de 4pt del dorso pasa a ser la cara) — fuente: `savia-web/_webbing/M2_M4_M5_iteracion2.md` | **"El Giro"** (volteo 180° dorso→frente; solo gira lo que tiene dato verificable del otro lado — NO marca/línea/onda/plano/luz). Motion: **"Gira y muestra"** — fuente: `savia-web/_webbing/M2_M4_M5_iteracion2.md` | Entrada+catálogo → Grilla → **Producto + fórmula PEGADA (crítica, 3/6)** → Garantía de 1ª compra → Checkout corto → Footer — fuente: `savia-web/_webbing/CDL_1_project_intelligence.md` | — | — |
| **GMAO (nombre TBD)** — SaaS B2B mantenimiento industrial — **proyecto de práctica / stress test, sin GATE 4** | #2 Lead alta-consideración (2º #2 del portfolio tras Move On — DIFF de esqueleto vs Move On/Runa en CDL-1) — fuente: `gmao-web/_webbing/M0_discovery.md` | **Estratega + Experto** (Estratega fresco; Experto = secundario de SAVIA, distinta categoría/voz — declarado sin colisión) — fuente: `gmao-web/_webbing/M1_M2_M3_estrategia.md` | **Chivo / IBM Plex Sans (+ IBM Plex Mono técnico)** — eco monitoreado: Chivo y Archivo (Estudio Tatuaje) son ambas Omnibus-Type BA, familias distintas/uso opuesto — fuente: `gmao-web/_webbing/M1_M2_M3_estrategia.md` | grafito `#16181B` · off-white frío `#EDEEEA` · acero `#5A6169` · línea `#C9CDCA` · **hi-viz seguridad `#D4FF00`** (acento ÚNICO de ESTADO; NUNCA texto sobre claro, sí sobre grafito) — base neutra comparte familia con Vera (declarado, no colisión: identidad = acento hi-viz vs azul de plano); ratios AA a MEDIR en build — fuente: `gmao-web/_webbing/M4_M4-5_M5_M5-5_creatividad.md` | **"En Tolerancia"** (marca **Calibre**) — fuente: idem | **"El Arco"** (arco/aguja radial de manómetro; marcador de estado en zona de tolerancia — NO línea/plano/onda/luz/marca/reverso/giro. Firma original "El Testigo"=banda lineal RETROCEDIDA por CDL-5: colisionaba con "La Marca" de Cursor Café, gesto "algo que se posa sobre escala"). Motion: **"Directo, mínimo, sostenido"** (re-descriptado por CDL-5: "Preciso/asentado" colisionaba con VINCA/Cursor) — fuente: `gmao-web/_webbing/CDL_1_a_5_juicio.md` | Hero+Arco → Diagnóstico → **Prueba por rubro (crítica, 3/8)** → Producto (UI real) → Por qué no termina en Excel → FAQ → **Demo (form rate-limit+webhook, 7/8; CTA alcanzable desde hero)** → Footer — fuente: idem | documental técnicos reales en planta, grading frío, sin marca competidora visible (H-2); práctica → (e)/(c) — fuente: `gmao-web/_webbing/M4_M4-5_M5_M5-5_creatividad.md` | Hero asimétrico tipo tablero de instrumentos (peso izq.) + firma radial "El Arco" (gauge/aguja) + motion "Directo, mínimo, sostenido" + grilla técnica de fondo. Chequeo v2.10 OMITIDO declarado: todas las demás filas tienen "—" en esta columna → sin comparador de portfolio todavía — fuente: `gmao-web/_webbing/M8-6_gate3.md` |
| **Cursor Café** | #4 Brand Experience (híbrido con conversión real) — fuente: `_webbing/CDL_1_project_intelligence.md` | **Editor + Anfitrión** | Instrument Serif / Familjen Grotesk | vino tostado(fondo dominante, cromático) `#2B161B` · hueso rosado(contrafondo) `#F0E9E6` · ultramar POR ROL (INC-2/INC-4): `--ultramar #3A4FE0` (5.19:1, solo sobre hueso) · `--ultramar-luz #6B84FF` (5.16:1, la marca sobre vino) · `--escala #856C72` (3.56:1, gráfico) · `--escala-texto #997F85` (4.65:1, labels de texto) — fuente: `_webbing/M5_visual_direction.md` + `_webbing/INCIDENTES_M14.md` INC-2/INC-4 | "El Punto Exacto" — fuente: `_webbing/M4_concept.md` | "La Marca" (trazo ultramar que se posa sobre una escala muda — NO la línea: Runa/Move On ya la tienen). Motion: "Aterriza y calla" — fuente: `_webbing/M5_visual_direction.md` | Hero → Origen → Proceso → Catálogo → **El Club (crítica, 5/7)** → El Local → Footer — fuente: `_webbing/CDL_1_project_intelligence.md` | — | — |

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

## HALLAZGO ABIERTO #3 — CDL-5 ítem 10 se verifica en M8.6, no en CDL-5 (2026-07-17)

CDL-5 corre "pre GATE 2" (su propio operational header, CDL-0 §ORDEN DE
EJECUCIÓN). M9 (que produce la combinación de patrones del ítem 10) corre
recién en CAPA 4, después de GATE 2. El fix del 2026-07-16 cableó el ítem 10
al RETROCEDER de CDL-5 sin notar que el dato no existe todavía en ese punto
del pipeline — encontrado en el stress test combinado SAVIA (2026-07-17).
Corregido: CDL-5 documenta el ítem 10 pero no lo evalúa; la verificación
real pasa a M8.6 (que corre después de M9.8, con el dato ya disponible),
contra esta columna del registro.

--------------------------------------------------------------------------------

## Mantenimiento

Actualizar la fila del proyecto correspondiente al cerrar M3 (tipografía),
M5 (paleta + firma), M4 (concepto) o CDL-1 (esqueleto). No esperar al final
del proyecto. Si CDL-5 encuentra una colisión al leer este archivo, cita la
fila exacta que colisiona — no re-describe todo el registro.

Proyectos ausentes de este registro (construidos antes de que existiera):
CUORE, Glow Factor. Si se vuelve a trabajar sobre alguno, poblar su fila
verificando contra el código real antes de usarlo como referencia.
