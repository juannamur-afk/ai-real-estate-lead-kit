# Checklist Rápido — AI Real Estate Lead Kit
### Imprime esto y ve marcando

---

## ANTES DE EMPEZAR

- [ ] Tengo un número de teléfono dedicado para WhatsApp Business (no en uso)
- [ ] Tengo acceso a Meta Business Manager (o puedo crear cuenta)
- [ ] Tengo tarjeta de crédito para crear cuenta en Anthropic (Claude API)
- [ ] Tengo cuenta de Google para Google Calendar

---

## PASO 1: Meta Business + WhatsApp API

- [ ] Cuenta de Meta Business Manager creada
- [ ] Número de WhatsApp Business agregado y verificado
- [ ] **Phone Number ID** copiado y guardado: `_______________________`
- [ ] **Access Token** generado y guardado (seguro): `_______________________`

---

## PASO 2: Claude API

- [ ] Cuenta en console.anthropic.com creada
- [ ] Método de pago agregado ($5 USD mínimo)
- [ ] **API Key** generada y guardada (seguro): `sk-ant-_______________________`

---

## PASO 3: Make.com

- [ ] Cuenta en make.com creada
- [ ] Blueprint `scenario-whatsapp-claude.json` importado
- [ ] Módulo Claude: API key y system prompt configurados
- [ ] Módulo WhatsApp: Phone Number ID y Access Token configurados
- [ ] Número del asesor humano configurado: `521_______________________`
- [ ] **URL del Webhook** copiada: `https://hook.make.com/_______________________`

---

## PASO 4: Conectar WhatsApp ↔ Make.com

- [ ] Webhook configurado en Meta Business > Configuración de WhatsApp
- [ ] URL del webhook pegada correctamente
- [ ] Token de verificación guardado: `_______________________`
- [ ] Suscripción a `messages` activada
- [ ] Webhook verificado exitosamente (aparece ✅ en Meta)

---

## PASO 5: Personalizar el agente

- [ ] System prompt elegido: Andrea / Pedro / Sofía
- [ ] `{{NOMBRE_AGENCIA}}` reemplazado con: `_______________________`
- [ ] `{{CIUDAD}}` reemplazado con: `_______________________`
- [ ] Portafolio de propiedades agregado al system prompt

---

## PASO 6: Activar y probar

- [ ] Escenario activado en Make.com (botón "On")
- [ ] Mensaje de prueba enviado al número de WhatsApp Business
- [ ] Respuesta del agente recibida en menos de 30 segundos ✅
- [ ] Prueba de escalación: enviar "necesito hablar con un asesor" → asesor notificado ✅

---

## ¡LISTO! El agente está funcionando 🎉

**Tiempo total estimado:** 2-4 horas la primera vez

**Costo mensual:** ~$10-20 USD (API Claude) + $0 Make.com tier gratis

---

*Si algo no funciona → ver `guia-de-setup.md` sección Troubleshooting*
