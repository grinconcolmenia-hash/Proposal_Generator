---
name: generar-propuesta
description: Genera el archivo Word (.docx) final de la propuesta comercial con la identidad de marca ya configurada. Úsalo después de que el usuario aprobó el preview en /preview-propuesta.
---

Genera el documento `.docx` usando el motor de ProposalCraft y la identidad de marca del usuario.

## Prerequisitos — verificar antes de ejecutar

- [ ] `brand.config.json` sin campos `TODO:`
- [ ] `agent_docs/brand_identity.md` existe (onboarding completado)
- [ ] Datos de la propuesta confirmados por el usuario en el preview

Si falta alguno, detente e indica al usuario qué paso completar primero.

---

## 1. Leer la identidad de marca

Lee `agent_docs/brand_identity.md` para confirmar los colores, fuente y assets configurados.
Esto garantiza que el documento generado sea fiel a la marca del usuario.

---

## 2. Generar el documento

Ejecuta el siguiente código desde la raíz del proyecto:

```python
import sys
sys.path.insert(0, ".")

from src.brand_loader import load_brand
from src.proposal_engine import generate_proposal, ProposalData

brand = load_brand()

proposal = ProposalData(
    cliente     = "[cliente confirmado en conversación]",
    titulo      = "[TÍTULO confirmado]",
    tagline     = "[tagline confirmado]",
    resumen     = "[resumen ejecutivo confirmado]",
    modulos     = [
        # Llenar con los módulos confirmados por el usuario
        ("MÓDULO\n1", "Tema · Duración", "· Punto 1\n· Punto 2"),
    ],
    detalles    = [
        # Llenar con los detalles confirmados
        ("Modalidad",  "Virtual / Presencial"),
        ("Duración",   "X horas"),
    ],
    valor_total = "[valor confirmado]",
    forma_pago  = "[forma de pago confirmada]",
    incluye     = "[ítems incluidos confirmados]",
    # fechas se calculan automáticamente desde hoy si no se especifican
)

output = generate_proposal(brand, proposal)
print(f"Propuesta generada: {output}")
```

---

## 3. Confirmar al usuario

Reporta:
- Ruta exacta del archivo: `outputs/Propuesta_[Cliente].docx`
- Colores usados (acento principal, fondo) — para que el usuario sepa que es su marca
- Invita a abrir el archivo y revisar

Mensaje sugerido:
> "Propuesta generada en `outputs/Propuesta_[Cliente].docx` con la identidad de [company_name].
> Ábrela y si necesitas algún ajuste, dime qué cambiar."

---

## Reglas

- Todos los valores de marca (colores, logo, fuente) vienen de `brand.config.json` — nunca hardcodear
- Si `python-docx` no está instalado: `pip install python-docx`
- El archivo se guarda en `outputs/` — nunca subir esta carpeta al repo si contiene datos de clientes
