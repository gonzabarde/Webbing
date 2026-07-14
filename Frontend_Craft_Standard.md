# FRONTEND CRAFT STANDARD (v1.4)

> Material de referencia transversal de craft visual. NO es un módulo de routing:
> lo cargan M3, M5, M5.5 y M8.6 vía sus hooks (cuando el humano apruebe los diffs)
> y cualquier sesión de ejecución frontend (M8–M9.8).
> Origen: propuesta tipo M14 (2026-07-04) — "el output de Webbing sale genérico
> con olor a IA". Autoridad: Claude propone, el humano aplica (SKILL.md §7 y §13).
> Estado: ACTIVO como material de referencia. Los hooks en módulos existentes
> requieren OK del humano (ver Docs/PROPUESTA_Frontend_Craft_diffs.md).

---

## 0. PROBLEMA QUE RESUELVE

El sistema tiene disciplina de proceso (gates, fidelidad, anti-clichés por
categoría) pero el craft visual por default converge a lo promedio del modelo:
Inter centrado sobre fondo plano con tres cards. Evidencia real:

- CUORE pasó GATE 3 con el sistema de imágenes de M5 ausente; lo detectó el
  humano mirando el deploy ("es muy pobre en términos de calidad").
- Tres sitios reales compartían el mismo esqueleto (origen del Principio 10).
- M8.6 solo detecta drift contra el Mapa de Clichés de la CATEGORÍA (M5.5).
  Los tells de IA genérica (Inter como body, fondo plano, hero simétrico,
  copy hedgey) no figuran en ningún mapa → un build tibio da "AUSENTE" y pasa.

Este estándar no reemplaza a M5/M5.5/M8.6: les da el piso de craft que asumían.

**Regla madre:** lo que no sirve es lo TIBIO. Maximalismo brutal y minimalismo
refinado sirven por igual. Lo que se prohíbe es el punto medio sin decisión.

---

## 1. MANDATO — DIRECCIÓN ESTÉTICA EXTREMA Y NOMBRADA

Antes de producir cualquier frontend (mockup, hero, build), declarar por escrito:

1. **NOMBRE de la dirección** (2–5 palabras, específico, no genérico).
   - Válidos: "brutalismo atlético nocturno", "editorial de archivo suizo",
     "lujo silencioso mediterráneo", "retro-futurismo de terminal".
   - Inválidos: "moderno y limpio", "premium", "minimalista" (a secas),
     "profesional". Si el nombre le sirve a cualquier proyecto, no es un nombre.
2. **MUNDO de referencia** (1 línea): de qué universo material/cultural sale.
   Ej: "señalética de estadio + camisetas + luz de reflector sobre cemento".
3. **QUÉ EXCLUYE** (3+ ítems): decisiones que esta dirección prohíbe.
   Una dirección que no excluye nada no es una dirección.
4. **EL EXTREMO**: en qué variable esta dirección se compromete a fondo
   (escala, oscuridad, vacío, densidad, color, movimiento). "Un poco de todo"
   está prohibido.

Sin estas 4 líneas declaradas, no se produce. Es condición de entrada a
cualquier trabajo visual, y GATE 2 la hereda vía M5 (hook propuesto).

---

## 2. TIPOGRAFÍA — REGLAS DURAS

### 2.1 PROHIBIDAS COMO BODY POR DEFAULT
Inter, Roboto, Arial, Helvetica/Helvetica Neue, system-ui / -apple-system /
"system font stack", Open Sans, Lato, Poppins, Montserrat, Space Grotesk.

Excepción única: producto UI-denso (dashboard, app) donde la neutralidad es
decisión estratégica ESCRITA, con la diferenciación cargada explícitamente en
otra variable (layout, color, motion) y declarada en el Signature Brief.
"Es legible y segura" no es justificación: es la definición del default.

### 2.2 PAIRING OBLIGATORIO CON CARÁCTER
- Display y body se eligen como PAR, no por separado. El par debe producir la
  tensión útil de M3 (historia+sistema, drama+control, futuro+pasado, etc.).
- Al menos UNA de las dos familias debe tener carácter identificable: si un
  diseñador no puede nombrar qué la distingue en una línea, no tiene carácter.
- JUSTIFICACIÓN ESCRITA obligatoria: qué comunica el par (señal semiótica de
  M3), por qué ESTE proyecto y no cualquiera, y contra qué 2 alternativas
  perdió cada elección.
- Fuente única (una familia, múltiples pesos) sigue siendo válida (M3 Pairing 5)
  solo si la familia tiene carácter propio y la escala hace el trabajo de
  contraste. Fuente única con neo-grotesk neutro = default disfrazado.

### 2.3 ESCALA
- Heredar los ratios de M3, pero el hero de un proyecto con dirección extrema
  usa el extremo del sistema: clamp() con techo real (100px+ desktop cuando la
  dirección lo pide), no el hero "seguro" de 49-61px por inercia.
- Contraste de pesos visible: si todos los textos pesan 400-600, no hay sistema.

---

## 2.4 CONSTRUCCIÓN DE PALETA — REGLAS DURAS DE COLOR

R1 (atmósfera) y el tell #6 (paleta tibia) del checklist §4 asumen un piso de
color que hasta ahora no estaba escrito. Acá está, en positivo.

### 2.4.1 NUNCA blanco puro ni negro puro
Prohibido `#FFFFFF` como fondo/texto claro y `#000000` como fondo/texto oscuro,
salvo excepción escrita. El blanco y el negro puros son la señal más barata de
"default sin decisión". Se usan SIEMPRE tintados hacia la temperatura de la
dirección:
- Claro cálido: `#F2F1ED`, `#F7F3E9`, `#E9E0CF` (crema/perla/alabastro).
- Oscuro tintado: `#101211`, `#161616`, `#0D1B2A` (carbón verdoso, obsidiana,
  azul casi-negro). El oscuro lleva un matiz (verde, azul, vino) según la
  dirección — nunca gris neutro plano.
Regla de Oryzo, verificada en referencia de gama alta: el tinte cálido/frío ES el
sistema; la pureza lee como error.

### 2.4.2 ESTRUCTURA DE PALETA (roles, no lista de colores)
Una paleta premium es un SISTEMA de roles, no una bolsa de 8 colores lindos:
- 1 fondo dominante (oscuro tintado o claro cálido — define el registro).
- 1 contrafondo (el opuesto del anterior, para secciones que respiran distinto).
- 1 acento primario con carácter (el color que define al sitio en 1 palabra).
- 0-1 acento secundario, subordinado, para detalle — no compite con el primario.
- Neutros derivados (2-3 grises tintados hacia la misma temperatura, para texto
  y bordes) — NO grises puros de Tailwind por default.
Si no podés decir EL color del sitio en una palabra (tell #6), la paleta no
tiene acento primario: tiene varios candidatos peleando y ninguno gana.

### 2.4.3 EL ACENTO FUERTE ES EDITORIAL, NO DECORATIVO
El acento saturado (un vino, un brass, un naranja, un terracota) se gana su
fuerza por ESCASEZ. Aplicarlo a todos los botones, links y íconos lo degrada a
ruido. Regla de Oryzo: el color fuerte es crédito editorial — momentos, no
superficies. Un acento que aparece en el 40% de la pantalla ya no es acento.

### 2.4.4 CHEQUEO CROSS-PORTFOLIO ANTES DE FIJAR (obligatorio)
Toda paleta se cruza contra `Docs/PORTFOLIO_REGISTRY.md` ANTES de cerrarse
(es también regla de M5, acá se refuerza a nivel de craft). Las paletas de
"luxury" que circulan en redes (crema+verde salvia, crema+terracota, arena+
vino) son el consenso del momento — tomarlas tal cual mete el problema de
sameness MÁS adentro, no lo resuelve. Se usan como referencia de ESTRUCTURA
(roles, temperatura, ausencia de puro), nunca de valores hex literales.

### 2.4.5 MEDICIÓN OBLIGATORIA DE RATIOS ANTES DE CERRAR (agregada 2026-07-13,
INC-2 de Cursor Café)
Una paleta NO cierra con el AA "declarado como a verificar después" — eso
convierte una condición de salida en deuda que se descubre recién en GATE 3
(o peor, nunca). M5 mide, con script real (no a ojo), el ratio WCAG de cada
par de rol antes de dar la paleta por cerrada:
- fondo ↔ texto principal (mínimo 4.5:1 texto normal / 3:1 texto grande).
- fondo ↔ acento, si el acento lleva texto encima (mismo mínimo según tamaño).
- acento ↔ texto-sobre-acento (ej. texto de un CTA relleno).
- fondo ↔ cualquier objeto gráfico SIGNIFICANTE (no decorativo) — si el
  objeto comunica contenido (una escala, un gráfico, un ícono funcional),
  aplica WCAG 1.4.11 (3:1) aunque "no sea texto". El error real que motivó
  esta regla: una escala tratada como "decoración" medía 1.51:1 — era en
  realidad el elemento que hacía legible el contenido central del sitio.
Si UN color falla contra dos fondos distintos (ej. debe leerse sobre claro Y
sobre oscuro), no se fuerza un compromiso mediocre en el medio — se declara
POR ROL: una variante del color por cada fondo contra el que necesita
funcionar (`--acento` para un fondo, `--acento-claro`/`--acento-oscuro` para
el otro), nunca un solo valor promediado que falla contra ambos.
Costo: 1 (script de ~20 líneas, reusable entre proyectos). Correrlo es más
barato que descubrir en GATE 3 que el acento del proyecto no se puede usar
donde el concepto lo necesita.

**Extensión obligatoria (INC-4, Cursor Café): declarar el UMBRAL por token,
no solo el ratio.** El mismo error de arriba se repite en otro eje si el
ratio se mide pero no se etiqueta para qué sirve — un token a 3.56:1 es
válido para un objeto gráfico (umbral 3:1) pero falla si alguien lo reusa
después para texto (umbral 4.5:1). Pasó dos veces en la misma sesión, con
dos ejes distintos de la misma clase de error (fondo-claro/fondo-oscuro,
después gráfico/texto). La tabla de paleta que sale de M5 declara, por cada
token, el USO al que está habilitado, no solo el hex y el ratio:
- `4.5` — texto normal.
- `3.0 (texto grande)` — solo si es ≥24px o ≥18.66px bold.
- `3.0 (objeto gráfico)` — SOLO para elementos no-textuales que comunican
  contenido (WCAG 1.4.11) — nunca reusar ese mismo token para texto después.
- `3.0 (límite de componente)` — bordes/estados de UI interactiva.
Un token sin uso declarado no se reusa "porque el color pega" — se mide de
nuevo para el uso nuevo, aunque sea el mismo hex. Costo: 0 (es una columna
más en la misma tabla que el párrafo anterior ya exige medir).

---

## 3. LOS 4 REQUISITOS DE SALIDA (hereda y endurece M5.5)

Ningún frontend sale de M5.5 (ni entra a producción vía M8–M9) sin los cuatro.
No son sugerencias: son condición de salida verificable ítem por ítem.

### R1 — ATMÓSFERA (fondo plano prohibido como default)
El fondo es una decisión, no una ausencia. Opciones válidas: gradiente con
dirección/luz, textura o grain, patrón geométrico derivado del mundo de la
marca, capas con profundidad (blur, transparencias), iluminación localizada
(glow, spotlight), o VACÍO DELIBERADO (un plano puro puede ser atmósfera si
está declarado como decisión y el resto del sistema lo sostiene — lujo
silencioso). `background: #fff` o un solo hex sin declaración = falla R1.

### R2 — MOMENTO MEMORABLE (uno, nombrable)
Un elemento que alguien describe 24 hs después sin ver el sitio ("el sitio del
número gigante que cuenta las canchas libres"). Se conecta con el Signature
System de M5/M9.8: la aparición PRIMARIA de la firma es el candidato natural.
Test: escribir la frase que diría el usuario. Si la frase sale genérica
("tenía animaciones lindas"), no hay momento.

### R3 — ASIMETRÍA / RUPTURA DE GRILLA INTENCIONAL
Al menos una decisión compositiva que rompa la simetría esperada: peso lateral,
elemento que cruza columnas o sangra del viewport, superposición texto/imagen,
diagonal, offset vertical entre columnas. El hero centrado-simétrico con dos
botones y tres cards abajo es la marca de agua de la IA: prohibido salvo
justificación escrita (ej. landing de conversión donde M5 lo pide — y aun ahí,
la asimetría puede vivir en otra sección).

### R4 — CONTRASTE BRUTAL DE ESCALA
La relación entre el elemento más grande y el texto base debe ser dramática y
buscada (guía: 8:1 o más en la pantalla de apertura cuando la dirección es
expresiva; en minimalismo refinado el contraste puede ser de vacío — un
elemento chico en un océano de espacio es el mismo requisito por la vía
opuesta). Todo del mismo tamaño ± 20% = falla R4.

---

## 4. ANTI-AI-SLOP CHECKLIST (accionable)

Correr sobre el artefacto REAL (screenshot/build, no la intención). Cada tell
presente = 1 punto. **3+ puntos = el build huele a IA → FALLA.**
1–2 puntos = corregir antes de mostrar a nadie.

| # | Tell | Cómo verificarlo |
|---|------|------------------|
| 1 | Body en Inter/Roboto/Arial/system (o de la lista 2.1) sin justificación escrita | Ver CSS computado |
| 2 | Fondo plano de un solo color sin declaración de vacío deliberado | Ver hero y secciones |
| 3 | Hero centrado simétrico: badge pill + H1 + sub + 2 botones apilados al centro | Ver composición |
| 4 | Grid de 3 cards iguales (ícono/emoji + título + párrafo) como primera sección | Ver estructura |
| 5 | Copy hedgey: "soluciones integrales", "todo en un solo lugar", "llevá X al siguiente nivel", "tu aliado en...", promesas sin sustantivo concreto ni número | Leer el copy en voz alta |
| 6 | Paleta tibia: acentos repartidos parejo, saturaciones medias, nada domina | ¿Podés decir EL color del sitio en 1 palabra? |
| 7 | Sin momento memorable (falla el test de la frase de R2) | Test 24 hs |
| 8 | Gradiente morado/azul sobre blanco u oscuro (el gradiente default del modelo) | Ver hero |
| 9 | Emojis como iconografía en un sitio de agencia | Ver cards/listas |
| 10 | Border-radius + sombra suave idénticos en TODOS los contenedores | Ver sistema de componentes |
| 11 | Escala uniforme: H1 apenas 2-3x el body | Medir |
| 12 | Ningún elemento sangra, se superpone ni rompe la grilla | Ver layout completo |
| 13 | Blanco puro `#FFFFFF` o negro puro `#000000` como fondo/texto principal sin excepción escrita (§2.4.1) | Ver CSS computado de fondo y texto |

Los tells 1–12 aplican a CUALQUIER categoría, exista o no Mapa de Clichés de
M5.5 para ella. Esto cubre el agujero de M8.6 (categorías sin mapa quedaban
sin verificación de drift).

**Piso técnico innegociable (no da puntos: da bloqueo directo):**
- Contraste WCAG AA en todo texto (incluido texto sobre atmósfera/imagen).
- Responsive real: la dirección sobrevive en 375px (la firma se adapta, no se
  elimina — M9.8 Sección 4, dilución 3).
- `prefers-reduced-motion` implementado: simplifica el motion, no lo borra.
- Focus visible en todo elemento interactivo.

---

## 5. INTEGRACIÓN DE LA SKILL frontend-design EN M5–M9

La skill instalada (`frontend-design`, plugin oficial) es un ACELERADOR de
criterio de craft, subordinado al sistema. Orden de autoridad:
**concepto (M4) → percepción (M4.5) → dirección (M5) → innovación (M5.5) →
este estándar → skill frontend-design como refuerzo de ejecución.**
La skill nunca decide dirección; refuerza el compromiso al ejecutarla
(misma regla que M9.3 aplica a las librerías de componentes: el criterio
primero, el acelerador después).

Mapa de uso por módulo:

- **M5 (Visual Direction):** usar su vocabulario de tonos extremos (brutally
  minimal, maximalist, retro-futuristic, luxury/refined, editorial, brutalist,
  art deco, industrial…) como disparador para NOMBRAR la dirección (§1).
  No copiar el tono: nombrarlo para este proyecto.
- **M5.5 (Visual Innovation):** sus ejes (unexpected layouts, overlap, diagonal
  flow, grid-breaking, atmospheric backgrounds) son candidatos directos para la
  variable de innovación. Los 4 requisitos (§3) son la condición de salida.
- **M8.2/M8.4 (build):** aplicar sus reglas de implementación — CSS variables
  para el sistema de color, motion CSS-first, un solo page-load orquestado con
  reveals escalonados antes que micro-efectos dispersos.
- **M9.2/M9.3 (componentes y motion):** "high-impact moments over scattered
  micro-interactions" refuerza el Motion Budget de M9.3. No agrega patrones
  nuevos: prioriza dónde gastar el budget existente.
- **M8.6 (review):** el "NEVER" de la skill (Inter/Roboto/Arial/system, purple
  gradients, predictable layouts, cookie-cutter) está operacionalizado en el
  checklist §4. M8.6 corre el checklist, no relee la skill.
- **M12:** las direcciones que la skill sugiere NO son referencias: son tonos.
  Las referencias reales siguen entrando por M12 con anti-copy.

---

## 5.1 REACT BITS — PARÁMETROS DE USO (acelerador de craft percibido)

React Bits (reactbits.dev) es una librería de **135 componentes** React animados en
4 categorías: **Text Animations (23)**, **Backgrounds (45)**, **Components (37)** y
**Animations (30)**. El catálogo completo, con la lente del sistema (qué recurso sirve a
R1/R2, qué es trend-risk/Decay, qué cuida performance/a11y) y una shortlist por intención,
está en `Docs/ReactBits_Catalog.md` — consultarlo al elegir un momento-firma, no listar de
memoria. Misma categoría y mismo orden de autoridad que la skill frontend-design
(§5): **ACELERADOR de ejecución, subordinado a
concepto→percepción→dirección→innovación→este estándar.** React Bits NUNCA decide
dirección; ejecuta un momento-firma ya decidido.

**Por qué entra al estándar (se recomienda usarlo):** su valor es craft PERCIBIDO
(R1 atmósfera, R2 momento memorable), no lógica. Eleva la percepción de calidad de
un proyecto de forma desproporcionada a su costo de código — es el cuadrante
**costo 1-2 / impacto 4-5** del Innovation Cost Matrix (M5.5). Por eso se usa CON
parámetros, no a discreción: mal usado, homogeneiza (sus componentes default son
una tendencia y se vuelven la nueva marca de agua).

**P1 — SUPERFICIE (dónde sí / dónde no).** SÍ: superficies-marca (hero, landing,
onboarding, auth, empty states, brand moments). NO por default: UI operativa densa
(dashboards, tablas, formularios, agenda) — ahí manda el Motion Budget de M9.3 y la
calma del arquetipo. Única excepción en operación: feedback funcional de estado, no decoración.

**P2 — PRESUPUESTO (cuánto).** Máximo UN momento-firma de React Bits por vista (= R2
"uno, nombrable"). No esparcir varios componentes animados por página. Si hay dos, ninguno es firma.

**P3 — COMPONENTE POR ROL (cuál para qué).**
- Text animations → el reveal del headline-firma (R2).
- Backgrounds → atmósfera del fondo (R1), SOLO recoloreados a la paleta y sin romper AA del texto encima.
- Componentes (carousels/cards con motion) → con cuentagotas; casi nunca en la operación.

**P4 — CUSTOMIZACIÓN OBLIGATORIA (anti-clon).**
- PROHIBIDO shippear un componente con sus colores/params default. Recolorear a los
  tokens de M3/M5; retimear al descriptor de motion de 3 palabras de M8.3.
- Cada proyecto usa un efecto DISTINTO (no el mismo reveal en todos → nueva marca de agua).
- El efecto debe servir al concepto (M4)/percepción (M4.5): si sacándolo la percepción no
  cambia, era decoración → se corta. Decay Test (M5.5): los componentes "tendencia del año"
  (Aurora glassy, gradient text) envejecen; preferir los atemporales o customizar fuerte.

**P5 — PISO TÉCNICO (innegociable, hereda §4).**
- prefers-reduced-motion: React Bits NO lo respeta por default → envolver para simplificar/desactivar.
- El contenido NUNCA depende de la animación para ser visible: SSR / sin-JS / motor de animación
  trabado → fallback a estado VISIBLE. (Los text-reveals arrancan en opacity 0; sin fallback, si
  el motor no corre el texto queda invisible — falla real y verificada, corrida VINCA 2026-07-07.)
- WCAG AA del texto sobre background animado. Decorativo = aria-hidden; contenido real en el DOM igual.
- Performance: backgrounds con canvas/rAF pausan fuera del viewport (IntersectionObserver, M9.3);
  no degradar LCP/INP.

**P6 — TECNOLOGÍA (React-only).** React Bits necesita React. En sitios vanilla/Astro
estáticos: portar a React solo si el proyecto lo justifica, o replicar el efecto en CSS/JS.
No agregar React solo para usar React Bits.

**Mapa de uso por módulo (hook):**
- **M5.5 (Innovation):** un componente de React Bits puede SER la variable de innovación elegida
  (texto/motion/atmósfera), evaluado en Cost Matrix + Decay Test como cualquier otra.
- **M8.3 (Motion):** el efecto hereda el descriptor de 3 palabras y el Motion Budget. No lo expande.
- **M9.8 (Signature):** el momento-firma de React Bits es candidato natural a la aparición PRIMARIA
  de la firma (R2). Uno, coherente, no disperso.
- **M8.6 (Review):** el checklist §4 corre igual sobre el build con React Bits. Un background trendy
  sin recolorear suma tells (paleta tibia / gradiente default) → se penaliza igual.

---

## 6. RELACIÓN CON EL RESTO DEL SISTEMA

- **No reabre módulos:** M3 sigue siendo dueño de la semiótica tipográfica;
  M5 de la dirección; M5.5 de la innovación; M9.8 de la firma. Este estándar
  fija PISOS que esos módulos asumían implícitos.
- **Proporcionalidad (SKILL.md §5):** en gobernanza Ligera el estándar NO se
  recorta — se ejecuta con medios baratos. Los 4 requisitos y el checklist son
  costo 1-2 del Innovation Cost Matrix (decisiones de diseño, no desarrollo):
  una dirección nombrada, un par tipográfico con carácter y un fondo con
  atmósfera cuestan lo mismo que sus versiones tibias.
- **CDL:** el CDL puede vetar una dirección extrema mal elegida. Este estándar
  no protege extremos incoherentes: protege contra la ausencia de compromiso.

## FAIL CONDITIONS
- Producir frontend sin dirección nombrada (§1 incompleto).
- Body en fuente de la lista 2.1 sin excepción escrita.
- Blanco puro `#FFFFFF` o negro puro `#000000` como fondo/texto principal sin
  excepción escrita (§2.4.1).
- Paleta sin acento primario identificable en 1 palabra, o acento fuerte usado
  como superficie en vez de momento editorial (§2.4.2 / §2.4.3).
- Paleta fijada sin cruzar contra PORTFOLIO_REGISTRY (§2.4.4).
- Paleta cerrada con el AA "declarado como a verificar después" en vez de
  medido con ratios reales de cada par de rol, incluidos objetos gráficos
  significantes (§2.4.5).
- Token de color reusado en un uso (texto/gráfico/borde) sin declarar el
  umbral que le corresponde a ESE uso, aunque el hex ya tuviera un ratio
  medido para otro uso (§2.4.5, extensión INC-4).
- Salir de M5.5 con alguno de R1–R4 ausente y sin justificación.
- Checklist §4 con 3+ tells en cualquier artefacto mostrado al humano o cliente.
- Cumplir el estándar rompiendo el piso técnico (AA, responsive, reduced-motion).
- React Bits shippeado con params/colores default (sin recolorear ni retimear) — §5.1 P4.
- Componente animado de React Bits en UI operativa densa sin justificación funcional — §5.1 P1.
- Text-reveal (React Bits u otro) sin fallback visible: contenido oculto si el motor no corre — §5.1 P5.
- Más de un momento-firma de React Bits por vista — §5.1 P2.

## PROMPT PARA CLAUDE
Actuá como director de craft frontend. Antes de escribir una línea de código:
declará la dirección estética con nombre, mundo, exclusiones y extremo.
Elegí el par tipográfico con carácter y justificalo contra alternativas.
Diseñá la atmósfera del fondo como decisión. Definí el momento memorable y
escribí la frase que diría el usuario 24 hs después. Rompé la simetría al menos
una vez con intención. Llevá el contraste de escala al extremo que la dirección
pide. Después ejecutá con precisión: AA, responsive, prefers-reduced-motion.
Antes de mostrar nada, corré el ANTI-AI-SLOP CHECKLIST sobre el resultado real.
Si da 3+, no lo muestres: rehacelo. Lo tibio no se entrega.
Si usás React Bits (§5.1): tratalo como acelerador — un solo momento-firma por
vista, en superficie-marca, recoloreado a la paleta, con reduced-motion y fallback
visible. Nunca decide la dirección; ejecuta la ya decidida.
