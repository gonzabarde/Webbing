# BRIEF INTERNO — CLIENTE FICTICIO 1/5 — "VINCA"

> Proyecto ficticio. Práctica de sistema Webbing (continuación de Glow Factor /
> CUORE / Runa / Ecos). No se contacta a nadie real. No se publica ni se comparte.
> Fecha de armado del brief: 2026-07-06.
> Ver TRASPASO 2026-07-06 para el contexto completo de la etapa (objetivo:
> 5 clientes ficticios nuevos, de a uno, cada uno cubriendo terreno no testeado).

## Por qué este perfil (gaps que cierra)

- Arquetipo #6 puro — Plataforma/Producto funcional (Ecos fue híbrido 1+4;
  nunca se corrió un #6 puro).
- Backend real de punta a punta, SIN bloquear la funcionalidad (Ecos la bloqueó
  adrede; acá el core loop del producto se construye entero).
- Multi-tenancy (Modelo A/B/C de B0) decidido en la práctica por primera vez.
- Gobernanza COMPLETA (dato NIVEL 3-4) — todo lo corrido hasta ahora fue
  Ligera/Media.
- Bonus: toca a propósito el borde NIVEL 2 vs NIVEL 4 que B0 ya documenta
  (dato cuasi-médico) — buen caso de stress test para esa regla concreta.

## 1. Identidad

- **Nombre fantasía:** VINCA
- **Qué es:** software de gestión (SaaS B2B) para estudios boutique de fitness
  y estética — agenda por profesional, ficha de cliente, cobros, panel para
  el dueño del estudio.
- **No confundir** con CUORE (gym real prospecteado, sin contacto) ni con
  Espacio Tita (cliente real de Webbing): VINCA es una empresa de software.
  Vende A estudios como CUORE; no ES un estudio.

## 2. Qué vende

- Plataforma de gestión multi-tenant. Cada estudio suscripto es un tenant con
  sus propios usuarios (dueño/admin, staff/profesionales), su propia agenda,
  su propia base de clientes y su propia facturación.
- Módulos: agenda y turnos por profesional/sala; ficha de cliente (incluye
  notas del profesional del tipo "viene por dolor lumbar", "contraindicación
  de tal ejercicio" — DELIBERADO, para forzar el borde NIVEL 2/4 en B0); cobro
  de sesiones/paquetes; panel de métricas para el dueño (ocupación,
  recurrencia, facturación).
- Pagos con doble cara (primera vez que el sistema resuelve esto):
  1. VINCA cobra suscripción mensual a cada estudio (B2B SaaS billing).
  2. Cada estudio cobra a sus clientes finales por sesión/paquete dentro de
     la plataforma (pagos en nombre de terceros — no es el checkout simple
     de Glow Factor).

## 3. A quién vende

- **Cliente que paga la suscripción:** dueño de un estudio boutique de
  fitness o estética con 1-5 profesionales, hoy gestionando turnos por
  WhatsApp + Excel o libreta.
- **Usuario final del estudio:** cliente del estudio, recibe recordatorios y
  turnos. Por default NO tiene login propio — es "sujeto de datos / contacto"
  (categoría de B0), no usuario autenticado, salvo que B0 derive lo contrario
  con justificación.
- **Mercado:** PyMEs de servicios boutique en Argentina — mismo universo que
  CUORE/Espacio Tita, pero acá se vende software, no un sitio.

## 4. Objetivo dominante

- Uso del producto (arquetipo 6), no marketing. Si en algún punto aparece una
  landing de venta del SaaS, es un proyecto aparte (arquetipo 2, Lead
  Alta-Consideración) — no mezclar en esta corrida.
- Foco de esta corrida: el shell de la app — auth → onboarding de un tenant
  nuevo → core loop de agendar / cobrar / ver panel.

## 5. Tipo de negocio / contexto

- SaaS B2B multi-tenant, mercado argentino, cobros en pesos vía Mercado Pago.
  Evaluar explícitamente en B0/B2 si Stripe Connect (el patrón típico de
  pagos con doble cara) es viable en el contexto AR o si corresponde un
  desvío justificado del default — no asumir Stripe Connect por costumbre.
- Sin marca/material existente. Generar lo mínimo indispensable para no
  bloquear el build de producto: esta corrida no es sobre dirección visual
  profunda (eso ya se testeó a fondo en Ecos).

## 6. Restricciones y notas para quien corra esto

- Webbing de punta a punta sin input humano en los gates (Claude Code como
  aprobador delegado, documentando cada decisión) — salvo que Gonza pida lo
  contrario para este caso.
- `INCIDENTES_M14.md` en caliente desde el arranque.
- M14 formal (6 ejes) al cerrar, ANTES de pasar al cliente 2 de 5. No dejarlo
  pendiente (como quedó con Runa).
- Verificar cada propuesta de M14 contra los archivos reales de Webbing antes
  de aplicar nada.
- Registrar TODAS las propuestas (aplicadas / rechazadas / postergadas) en
  `Docs/M14_PROPOSAL_LOG.txt`.
- No mostrar, publicar ni contactar a nadie real con este proyecto.
- No forzar stack: dejar que CDL-1 (arquetipo), M8.1 y B0 deriven solos con
  los defaults ya ajustados hoy.

**Puntos que ESTA corrida debe forzar a decidir de forma explícita y
justificada (no dejar en default sin argumentar):**

1. Modelo de multi-tenancy (A/B/C) — esperable Modelo A dado el perfil, pero
   que B0 lo derive y lo justifique, no asumirlo de antemano.
2. Nivel de sensibilidad de la ficha de cliente (2 vs 4) — aplicar el
   criterio del borde documentado en B0 explícitamente, no promediar.
3. Arquitectura de pagos con doble cara — primera vez que el sistema la
   resuelve; no es el checkout simple ya cubierto por Glow Factor.
4. Auth B2B con organizaciones (dueño + staff por tenant) — primera vez que
   se decide en serio un proveedor con soporte de Organizations.

## 7. Ubicación sugerida del proyecto

- Crear `C:\Users\joaqu\vinca-web\_webbing\` siguiendo la convención de
  CUORE/Runa/Ecos (numeración `00_M0_Discovery...`, etc.) al arrancar la
  corrida formal.
- Este archivo es el Brief Interno (input obligatorio de M0), no lo
  reemplaza: M0 debe correr research real (competencia tipo Booksy, Fresha,
  Zenoti, GymMaster — patrones de categoría) antes de pasar a M1.

## Próximo paso

Correr M0 (Discovery & Research) sobre este brief en una sesión de Claude
Code con el skill Webbing cargado.
