---
name: preview-propuesta
description: Muestra un preview estructurado de la propuesta antes de exportar a Word. Úsalo para revisar y aprobar el contenido con el usuario antes de generar el .docx.
---

Presenta un preview completo de la propuesta en texto formateado para que el usuario revise y apruebe antes de generar el archivo Word.

Lee primero `brand.config.json` para obtener los datos del proponente y la empresa.

## Formato del Preview

Muestra la propuesta con esta estructura en markdown, usando los datos recopilados y los valores de `brand.config.json`:

---

```
════════════════════════════════════════════════════
  [NOMBRE DEL SERVICIO EN MAYÚSCULAS]
  [Tagline del servicio]
════════════════════════════════════════════════════

  PROPUESTA COMERCIAL
  Preparada para: [Nombre del cliente / empresa]

────────────────────────────────────────────────────
  RESUMEN EJECUTIVO
────────────────────────────────────────────────────
  [Descripción concisa del servicio — 2 a 3 oraciones,
   orientada a beneficios y resultados]

────────────────────────────────────────────────────
  ALCANCE DEL SERVICIO
────────────────────────────────────────────────────
  Modalidad: [presencial / virtual / híbrido]
  Metodología: [descripción breve]

  Módulos / Entregables:
  · [Ítem 1]
  · [Ítem 2]
  · [Ítem N]

────────────────────────────────────────────────────
  DETALLES DEL PROGRAMA
────────────────────────────────────────────────────
  Duración total:       [X horas / días / semanas]
  Número de sesiones:   [N sesiones]
  Horario / Fechas:     [según acuerdo]
  Participantes:        [N personas]

────────────────────────────────────────────────────
  INVERSIÓN
────────────────────────────────────────────────────
  Valor total:    $ [monto] [moneda desde brand.config]
  Forma de pago:  [condiciones]
  Incluye:
  · [Qué está incluido]

────────────────────────────────────────────────────
  VIGENCIA DE LA PROPUESTA
────────────────────────────────────────────────────
  Fecha de emisión:  [DD/MM/AAAA]
  Válida hasta:      [DD/MM/AAAA]  (N días calendario)

────────────────────────────────────────────────────
  PROPONENTE Y FIRMA
────────────────────────────────────────────────────

  ________________________________
  [brand.proponent_name]
  [brand.proponent_id_full]
  [brand.company_name]

════════════════════════════════════════════════════
```

---

## Después del Preview

Pregunta al usuario:

> **¿El contenido está correcto?**
> 1. ✅ Sí, generar el Word → usa `/generar-propuesta`
> 2. ✏️ Necesito ajustar algo → indica qué cambiar

No generes el `.docx` hasta recibir confirmación explícita del usuario.
