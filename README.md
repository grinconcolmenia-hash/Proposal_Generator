# ProposalCraft — Generador de Propuestas Comerciales con IA

Agente de IA especializado en crear propuestas comerciales profesionales en Word (`.docx`), con la identidad visual de tu empresa. Funciona dentro de **Claude Code**.

---

## ¿Qué hace?

- Recopila los datos de la propuesta en conversación natural
- Aplica tu marca (colores, logo, tipografía) automáticamente
- Genera un `.docx` listo para enviar al cliente

---

## Estructura del proyecto

```
ProposalCraft/
├── CLAUDE.md                  # Instrucciones del agente para Claude Code
├── brand.config.json          # Configuración de tu marca (editable)
├── generar_demos.py           # Script para generar propuestas de demo
├── src/
│   ├── brand_loader.py        # Carga la configuración de marca
│   └── proposal_engine.py     # Motor de generación de documentos Word
├── .claude/
│   ├── commands/
│   │   └── configurar-marca.md   # Skill: configurar marca
│   └── skills/
│       ├── generar-identidad.md  # Skill: regenerar identidad visual
│       ├── preview-propuesta.md  # Skill: previsualizar propuesta
│       └── generar-propuesta.md  # Skill: generar .docx final
├── outputs/                   # Propuestas generadas (.docx)
├── activos_de_marca/          # Logo y banner de tu empresa (privado)
└── agent_docs/                # Identidad generada (privado)
```

---

## Requisitos

```bash
pip install python-docx pillow
```

---

## Configuración inicial

1. Clona el repositorio
2. Abre la carpeta en **Claude Code**
3. Ejecuta el comando `/configurar-marca` — el agente te guía paso a paso
4. ¡Listo! Ya puedes generar propuestas

---

## Uso

Abre la carpeta en Claude Code y escribe lo que necesitas:

> "Necesito una propuesta para el cliente Acme Corp, servicio de consultoría de marketing digital..."

El agente pregunta los datos que falten, muestra un preview y genera el `.docx`.

---

## Skills disponibles

| Comando | Función |
|---|---|
| `/configurar-marca` | Primera vez — configura tu marca |
| `/generar-identidad` | Regenera la identidad si cambia la marca |
| `/preview-propuesta` | Previsualiza antes de generar |
| `/generar-propuesta` | Genera el `.docx` final |

---

## Temas visuales incluidos

| Tema | Descripción |
|---|---|
| `T1_DarkPrestige` | Oscuro clásico — elegante y premium |
| `T2_ForestCorporate` | Verde corporativo — fresco y profesional |
| `T3_NeonDuality` | Tech azul/neón — moderno y dinámico |

---

## Recursos adicionales

- [Tutorial en video — Cómo usar ProposalCraft](tutorial/README.md) ([Ver en YouTube](https://www.youtube.com/watch?v=7YFhEZ2oXRw))

---

## Licencia

MIT — libre de usar, modificar y distribuir.
