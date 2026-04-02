# Guía de Setup — AI Real Estate Lead Kit
### De cero a tu agente respondiendo en WhatsApp en un fin de semana

---

## Qué vas a necesitar

| Herramienta | Costo | Para qué |
|---|---|---|
| Make.com | Gratis (hasta 1,000 ops/mes) | Automatización central |
| Claude API | ~$0.50-3/mes | El cerebro del agente |
| WhatsApp Business API | Gratis (1,000 conv/mes) | Canal de comunicación |
| Meta Business Manager | Gratis | Para activar WhatsApp API |
| Google Calendar | Gratis | Agendar visitas |

**Costo total para arrancar: ~$1-5 USD/mes**

---

## Paso 1: Meta Business + WhatsApp Business API (30-60 min)

1. Ve a business.facebook.com → crea cuenta Business Manager
2. "Configuración del negocio" → "Cuentas de WhatsApp" → agregar número
   - Usa un número que NO esté en WhatsApp normal
3. Una vez verificado → "API de WhatsApp" → copia:
   - **Phone Number ID**
   - **Access Token**

---

## Paso 2: Claude API Key (5 min)

1. Ve a console.anthropic.com → crea cuenta
2. "API Keys" → "Create Key" → guarda la key

---

## Paso 3: Make.com (20-30 min)

1. Crea cuenta en make.com
2. "Scenarios" → "Import Blueprint" → sube `modulo-1-make-blueprints/scenario-whatsapp-claude.json`
3. En cada módulo, reemplaza las variables del JSON:
   - **Claude module**: pega tu API key + system prompt de `modulo-2-prompts/`
   - **WhatsApp modules**: Phone Number ID + Access Token + número del asesor
4. Copia la URL del Webhook (la necesitas en Paso 4)

---

## Paso 4: Conectar WhatsApp con Make.com (10 min)

1. Meta Business → "Configuración de WhatsApp" → "Webhooks"
2. URL: pega la URL de Make.com
3. Token de verificación: cualquier texto (ej: "mitoken123")
4. Suscríbete a: `messages` → "Verificar y guardar"

---

## Paso 5: Personalizar con tu portafolio (15-30 min)

En el system prompt, reemplaza `{{INSERTAR_AQUI_EXTRACTO_DEL_PORTFOLIO}}` con:

```
PROPIEDADES DISPONIBLES:
- Depto 2 rec, Col. Polanco, $18,500/mes, 85m², 2 baños, 1 estacionamiento
- Casa 3 rec, Lomas, $35,000/mes, 180m², jardín, 2 estacionamientos
- Studio, Roma Norte, $12,000/mes, 45m², 1 baño
```

---

## Paso 6: Prueba (5 min)

1. Make.com → activa el escenario (botón "On")
2. Mándate un WhatsApp al número de negocio
3. Deberías recibir respuesta en menos de 30 segundos

---

## Checklist

- [ ] Meta Business verificado
- [ ] WhatsApp Business API activa
- [ ] Claude API key generada
- [ ] Make.com escenario importado y configurado
- [ ] Variables reemplazadas
- [ ] Webhook conectado y verificado
- [ ] Escenario activo
- [ ] Prueba exitosa ✓

---

## Control de costos API

El blueprint ya usa `claude-haiku-4-5` con `max_tokens: 150` — el modelo más económico y más que suficiente para respuestas de 2-3 oraciones.

**Para mantener costos bajos:**
- **Portfolio**: pega máx. 5 propiedades en el system prompt, 2 líneas cada una. El portfolio completo puede multiplicar x5 el costo por mensaje.
- **No aumentes max_tokens**: 150 tokens = ~3 oraciones largas. Más no mejora las respuestas.
- **Si escalas a >500 leads/mes**: activa Prompt Caching en Anthropic (beta) — reduce 90% el costo del system prompt en conversaciones repetidas.

**Costo estimado a 1,000 mensajes/mes con esta configuración: < $0.50 USD**

---

## Troubleshooting

**WhatsApp no llega al webhook:** Verifica que el escenario esté "On" en Make.com

**Claude responde pero WhatsApp no manda:** El Access Token expiró (duran 60 días), genera uno nuevo

**El agente responde en inglés:** Verifica que pegaste el system prompt completo

**Escalación a asesor no funciona:** Verifica formato del número: 521XXXXXXXXXX

---

---

## ¿Quieres un agente 100% personalizado para tu agencia?

Este kit te da el sistema base. Si necesitas algo más avanzado — integrado con tu CRM, tu MLS, tu base de datos de propiedades, o con flujos de trabajo específicos de tu operación — podemos construirlo contigo.

**Escríbenos a juannamur@gmail.com** con el asunto "Agente Custom" y cuéntanos qué necesitas.

---

*AI Real Estate Lead Kit v1.0 — Namur CPA*
