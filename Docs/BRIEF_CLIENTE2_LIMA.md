# BRIEF INTERNO — CLIENTE FICTICIO 2/5 — "LIMA Estética Integral"

> Proyecto ficticio. Práctica de sistema Webbing end-to-end. No contactar a nadie
> real. No publicar ni compartir como cliente real.
> Fecha de armado del brief: 2026-07-07.
> Primera corrida post-Experience Spec (CDL-1 v1.3) — debe producir IA Spec +
> Experience Spec en GATE 2 y verificarlas en GATE 3.

## Por qué este perfil (gaps que cierra)

- Arquetipo **#3 puro** — Turno / servicio local (CUORE era gym prospecto real;
  LIMA es ficticio pero stress-testea captación medible).
- **Experience Spec** en la práctica: el producto del sitio ES completar una reserva.
- Gobernanza **Media** — pipeline estándar sin B0-B6 (marketing + reservas, no SaaS).
- Core de escalera M13.0A (~USD 1.100) — ticket realista para PyME AR.
- Dirección visual **no genérica** en categoría estética (evitar spa rosa / Inter / 3 cards).
- Primera corrida ficticia orientada a **captación medible** (GATE 13.4-E) post-ECOS/VINCA.

---

## INSTRUCCIONES PARA CLAUDE CODE (copiar al inicio de la sesión)

```
Activá el skill Webbing (~/.claude/skills/webbing/SKILL.md).
Leé este brief completo antes de M0.

Corrida: Webbing end-to-end LIMA Estética Integral (cliente ficticio).
Aprobador delegado: Claude Code documenta cada gate; no pedir input humano
salvo contradicción bloqueante.

Orden: M0 → M1 → M2 → M3 → [GATE 1] → M4 → M4.5 → M5 → M5.5 → CDL → [GATE 2]
→ M6 → M7 → M8 → M9 → M9.8 → M8.6 → [GATE 3] → build → M10 → [GATE 4 documentado,
deploy solo si el operador lo pide].

Backend: NO activar B0-B6 (sin auth/DB/pagos propios; reservas vía Cal.com o
equivalente embebido).

Gobernanza: Media (M10.0 / M13.2).

Artefactos en repo del proyecto:
  lima-web/_webbing/00_M0_Discovery.md
  lima-web/_webbing/01_M1_Positioning.md
  ... (numeración por módulo)
  lima-web/_webbing/INCIDENTES_M14.md (desde el arranque)
  lima-web/_webbing/GATES.md (log de cada gate)

Al cerrar: corrida formal M14 (6 ejes) + registrar en Docs/M14_PROPOSAL_LOG.txt
del skill Webbing.

Input obligatorio: este archivo (Brief Interno). M0 debe igualmente verificar
competencia y categoría en vivo (Principio 9) — no confiar solo en lo escrito acá.
```

---

## 1. Identidad

| Campo | Valor |
|-------|-------|
| **ID interno** | WEB-2026-LIMA |
| **Nombre fantasía** | LIMA Estética Integral |
| **Razón social** | Lima Estética Integral S.R.L. (ficticia) |
| **Qué es** | Consultorio de estética **médica** en Belgrano, CABA |
| **Dueña / cara visible** | Dra. Marina Lima — dermatóloga (MN 89432 ficticio) |
| **Sitio actual** | https://limaestetica.wixsite.com/lima (ficticio, simular Wix 2020) |
| **Instagram** | @limaesteticaintegral (ficticio, ~2.800 seguidores) |
| **Google Business** | Existe — 4.7★, 23 reseñas, sin link de reserva |

---

## 2. Qué vende / servicios

Tratamientos **médicos** (no spa). Lista cerrada para el sitio (6 servicios):

| Servicio | Duración | Precio "desde" (ARS, orientativo) |
|----------|----------|-----------------------------------|
| Consulta diagnóstica | 30 min | $45.000 |
| Botox (zona) | 20 min | $80.000 |
| Peeling químico | 45 min | $55.000 |
| Hilos tensores | 60 min | $120.000 |
| Láser depilación (zona) | 30 min | $35.000 |
| Láser facial (rejuvenecimiento) | 45 min | $70.000 |

**Regla de negocio:** primera visita siempre recomienda consulta diagnóstica si la
paciente no tiene historial en LIMA.

---

## 3. A quién vende

- **Paciente ideal:** mujer 32-55, Belgrano/Núñez/Caba norte, ingresos medio-altos.
- **Motivación:** confianza médica + resultados naturales (no "transformación extrema").
- **Comportamiento actual:** descubre por IG o referida; escribe DM o WhatsApp;
  muchas abandonan si no hay respuesta el lunes antes de las 11hs.

---

## 4. Situación actual (dolor — usar en M0/M15)

1. **Turnos perdidos:** ~8-12 consultas/mes estimadas perdidas por DM sin respuesta
   rápida (dato declarado por Marina — tratar como hipótesis; M0 no lo toma como verdad).
2. **Formulario roto:** el form Wix no envía email; Marina revisa manualmente 1 vez/día.
3. **Google no convierte:** perfil GBP completo pero sin CTA reserva → tráfico a IG.
4. **Competencia:** Dermablanco (Belgrano) tiene Calendly + WhatsApp; Skin Lab (Palermo)
   tiene sitio rápido + reserva online.
5. **Marina no quiere:** e-commerce, blog, descuentos tipo Groupon, lenguaje "anti-edad
   agresivo".

---

## 5. Objetivo del proyecto (Webbing Core)

**Instalar un sistema de captación:**

- Sitio web nuevo (marketing, arquetipo #3)
- Reservas online funcionando (Cal.com u otro — sin backend propio Webbing)
- WhatsApp con mensaje prefill
- Google Business Profile vinculado al link de reserva
- SEO local básico (Belgrano + servicios principales)
- Baseline de captación documentado al entregar (GATE 13.4-E)

**Objetivo dominante:** reservar turno / generar consulta calificada.

**NO es objetivo:** percepción luxury puro (arquetipo 4) ni ecommerce (arquetipo 1).

---

## 6. Negocio Webbing (M13 — pre-cerrado para la corrida)

| Campo | Valor |
|-------|-------|
| Canal origen | Referido (paciente de Marina → otra dermato) + M15 simulado |
| Qualification score | 19/25 — avanzar |
| Producto | Core (sistema de captación instalado) |
| Gobernanza M10.0 | **Media** |
| Precio acordado (ficticio) | USD 1.100 — 50% inicio / 50% pre-deploy |
| GATE 13.4-A | Prueba de compromiso (fase arranque ficticia) |
| Retainer propuesto al entregar | USD 120/mes (hosting, ajustes, reporte reservas) |

### Scope IN
- Home + servicios (6) + sobre Marina + reservas + FAQ + contacto + legal
- Integración reservas (Cal.com embed o API simple)
- WhatsApp flotante mobile
- GA4 + evento `booking_complete`
- OG + metadata local
- Handoff: accesos, mini manual "cómo ver turnos"

### Scope OUT
- Blog / contenido SEO masivo
- E-commerce productos homecare
- App nativa
- Mercado Pago / cobro online de tratamientos
- CRM / GHL (North Star futuro, no esta corrida)
- Fotos profesionales — usar placeholders documentados + brief de shot list para Marina

---

## 7. Captación — baseline y éxito (GATE 13.4-E)

| Campo | Valor |
|-------|-------|
| **Métrica principal** | Reservas online completadas / mes |
| **Fuente** | Cal.com dashboard + GA4 event `booking_complete` |
| **Baseline pre-sitio** | 0 reservas online (100% DM/WhatsApp manual) |
| **Meta 90 días** | ≥ 12 reservas online / mes |
| **Métricas secundarias** | Clicks WhatsApp (GA4), llamadas desde GBP |

---

## 8. Restricciones técnicas y de marca

- **Stack:** seguir defaults Webbing 2026-07-06 — Astro o Next.js (static/SSG),
  NO vanilla HTML sin justificación.
- **Idioma:** español rioplatense, voseo moderado, sin lunfardo.
- **Compliance:** no prometer resultados milagro; incluir legales consultorio médico AR.
- **Accesibilidad:** WCAG AA, mobile-first 375px (Experience Spec obligatoria).
- **Fotos:** consultorio ficticio — placeholders con tratamiento visual definido en M5
  (no stock de mujer genérica tocándose la cara).

---

## 9. Material existente (ficticio)

### Copy aprobado por Marina (usar como base M0, no verbatim en hero)

> "Soy dermatóloga. Antes de recomendar un tratamiento, te escucho y evalúo tu piel.
> En LIMA no vendemos paquetes: vendemos criterio médico."

### Testimonios (ficticios, usar 2 en sitio)

1. *"Reservé online un martes a la noche y el miércoles ya tenía turno. Antes mandaba
   mensaje y esperaba días."* — Laura M., Belgrano
2. *"Me explicó opciones sin presionarme. Se nota que es médica, no vendedora."*
   — Carolina R., Núñez

### Datos de contacto (ficticios)

- **Dirección:** Av. Cabildo 2187, Piso 4, Belgrano, CABA
- **WhatsApp:** +54 11 4321-9876 (ficticio)
- **Email:** hola@limaestetica.com.ar (ficticio)
- **Horarios:** Lun-Vie 10-19, Sáb 10-14

---

## 10. Hipótesis estratégicas (M0 debe verificar — Principio 9)

| Claim | Tratar como |
|-------|-------------|
| "Somos las mejores de Belgrano" | Superlativo no verificable — NO usar como eje |
| "10 años de experiencia" | Verificar (ficticio: sí, desde 2016) |
| "Pacientes siempre vuelven" | Hipótesis — buscar en reseñas |
| "8-12 turnos perdidos/mes" | Hipótesis — razonable pero no dato cerrado |
| Competidores listados | Verificar existencia/nombres en research vivo |

---

## 11. Dirección creativa — semilla (M5 debe nombrar y extremar; no copiar tal cual)

**Semilla propuesta:** *"clínica editorial suiza"*

- Mundo: revistas médicas europeas + recepción consultorio (madera clara, lino, luz natural)
- Excluye: rosa/gradiente spa, iconos line-art genéricos, Inter/Roboto, 3 cards iguales
- Tipografía sugerida (M3 confirma): Cormorant Garamond + Figtree
- Momento memorable (M5.5): ficha clínica expandible en servicios (signature M9.8)

CDL-1 debe derivar IA Spec + **Experience Spec** (flujo reserva 5 pasos, estados,
mobile-first) — ver CDL-1 v1.3.

---

## 12. IA Spec esperada (CDL-1 — verificar en corrida, no asumir cerrada)

**Arquetipo:** #3 Turno / servicio local

**Orden de secciones esperado (~8):**
1. Hero — problema + CTA reservar
2. Credenciales — Marina + MN + enfoque médico
3. Servicios — 6 tratamientos
4. Prueba — reseñas + casos
5. **Reservar** — turnos + mapa + horarios ← sección crítica (~5/8)
6. FAQ
7. Contacto
8. Footer legal

**Experience Spec — flujo crítico esperado:**
Trigger hero/sticky → elegir servicio → día/hora → datos mínimos → confirmación
→ email + WhatsApp. Estados: vacío, loading, error, éxito.

---

## 13. Ubicación del proyecto

Crear repo/carpeta:

```
C:\Users\joaqu\lima-web\
  _webbing\          ← artefactos Webbing (MD por módulo)
  src\               ← código del sitio (stack derivado en M8.1)
  INCIDENTES_M14.md  ← opcional en raíz o dentro _webbing
```

Dominio ficticio producción: `limaestetica.com.ar`

---

## 14. Puntos que ESTA corrida debe forzar explícitamente

1. **Experience Spec completa en CDL-1** — primera corrida con CDL-1 v1.3; documentar
   en GATE 2 y verificar implementación en GATE 3.
2. **Regla falsabilidad M0** — no usar "las mejores de Belgrano" como posicionamiento.
3. **Frontend Craft** — dirección nombrada + 0 tells AI-slop en M8.6.
4. **Reserva mobile 375px** — flujo completable sin scroll infinito; sticky CTA.
5. **Cal.com (o equivalente)** — documentar pre-flight M9.3 si usa acelerador/librería.
6. **M14 formal al cierre** — registrar propuestas en M14_PROPOSAL_LOG.txt.

---

## 15. Claims / contacto — recordatorio

**Ficticio. No contactar. No publicar como cliente real.**

---

## Próximo paso

Abrir Claude Code en `lima-web/` (o crearlo), pegar las instrucciones de la sección
"INSTRUCCIONES PARA CLAUDE CODE", adjuntar este brief, y arrancar **M0**.
