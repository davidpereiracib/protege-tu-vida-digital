# 03 · Tu teléfono es el objetivo

> *Tu celular puede tener acceso al correo que recupera la contraseña del banco y, al mismo tiempo, al segundo factor que confirma que eres tú.*

En un único dispositivo conviven tu correo, tu dinero, tu autenticación, tu identidad social, tus fotos y tu ubicación. Por eso el teléfono dejó de ser un objetivo de robo común para convertirse en la llave de todo lo demás.

---

## Configúralo pensando en el día que caiga en manos equivocadas

### Ambos sistemas

| Medida | Por qué importa |
|---|---|
| **PIN fuerte** | Evita `123456`, fechas de nacimiento y patrones fáciles de observar por encima del hombro |
| **Biometría** | Rostro o huella para proteger acciones sensibles |
| **Ocultar contenido de notificaciones** | Que no se vean códigos ni mensajes con la pantalla bloqueada |
| **Localización remota activada** | Para localizar, bloquear o borrar |
| **Copia de seguridad** | Debes poder borrar el teléfono sin perder lo importante |

### iPhone

| Función | Ruta | Enlace |
|---|---|---|
| **Protección de Dispositivo Robado** | Ajustes → Face ID y código | https://support.apple.com/es-co/HT212510 |
| **Verificación de Seguridad** | Ajustes → Privacidad y seguridad | https://support.apple.com/es-co/guide/personal-safety/ipsd7c4f7b4a/web |
| **Protección de Datos Avanzada** (cifrado E2E de iCloud) | Ajustes → tu nombre → iCloud | https://support.apple.com/es-co/108756 |
| **Modo Extremo** (Lockdown Mode) | Ajustes → Privacidad y seguridad | https://support.apple.com/es-co/105120 |
| **Buscar** | Localización, bloqueo y borrado remoto | https://www.icloud.com/find |

**Protección de Dispositivo Robado es la más importante y la menos conocida.** Con ella activada, aunque le roben el teléfono **con el código puesto**, el ladrón no puede cambiar tu contraseña de Apple ni desactivar Buscar: exige Face ID sin alternativa de código, más una espera de una hora fuera de tus ubicaciones habituales. Es la diferencia entre perder un teléfono y perder tu vida digital.

**Sobre el Modo Extremo:** no es para todos. Rompe funciones a propósito y está pensado para periodistas, activistas y personas expuestas a spyware dirigido.

### Android

| Función | Ruta | Enlace |
|---|---|---|
| **Protección Avanzada** | Ajustes → Seguridad y privacidad | https://support.google.com/android/answer/16339980?hl=es-419 |
| **Detección de Robo por IA** | Ajustes → Seguridad → Protección contra robo | — |
| **Espacio Privado** | Ajustes → Seguridad y privacidad | — |
| **Find Hub** | Localización, bloqueo y borrado remoto | https://google.com/android/find |

**Detección de Robo por IA**: si el teléfono detecta el movimiento brusco típico de un arrebato, bloquea la pantalla por sí solo.

**Espacio Privado**: un contenedor oculto para las apps más sensibles, como las de banca.

### Detección de rastreadores no deseados

Los rastreadores tipo AirTag pueden usarse para seguir a personas. Ambos sistemas los detectan:

- **iPhone**: Buscar → Elementos → *Elementos que me pueden seguir*
- **Android**: Ajustes → Seguridad y privacidad → *Alertas de rastreadores desconocidos* → **Buscar ahora**

---

## SIM Swap: cuando tu número deja de ser tuyo

Tu número telefónico también forma parte de tu identidad digital. En un SIM swap, un tercero consigue que tu línea sea transferida a otra SIM o eSIM bajo su control.

**Qué ocurre:**
- Tu celular pierde la línea — dejas de recibir llamadas y SMS
- El atacante recibe tu número y las comunicaciones asociadas
- Puede recibir **códigos por SMS**, si todavía los usas para autenticación
- Puede intentar **recuperar cuentas** vinculadas al número

**Cómo reducir el riesgo:**

| Medida | Cómo |
|---|---|
| **PIN de la SIM** | iPhone: Ajustes → Datos móviles → PIN de la SIM · Android: Ajustes → Seguridad → Bloqueo de tarjeta SIM |
| **Bloqueo de portabilidad** | Solicítalo a tu operador. Es gratis y casi nadie lo hace |
| **Sal del SMS** | Migra a app TOTP o passkeys donde sea posible |
| **Anota tu IMEI hoy** | Marca `*#06#`. Cuando te roben el teléfono no vas a poder consultarlo |

> Si te roban el teléfono y la SIM no tiene PIN, la sacan, la ponen en otro aparato y reciben todos tus códigos de verificación.

---

## Spyware: cuando no necesitas hacer clic

Existen ataques **zero-click** donde la víctima no necesita abrir un enlace, instalar nada ni aceptar un archivo. Aprovechan vulnerabilidades en servicios que procesan información automáticamente: mensajería, llamadas, imágenes, servicios del sistema.

Un spyware avanzado podría acceder a mensajes, micrófono, cámara, ubicación, archivos y actividad del dispositivo.

**Pero en perspectiva:** este tipo de amenaza suele estar asociada a **objetivos de alto valor y ataques muy dirigidos**. Para la mayoría de las personas, mantener el sistema actualizado y activar los modos de protección reforzada es suficiente.

La defensa más subestimada sigue siendo la más simple: **mantén el sistema operativo al día**.

---

## 🚨 Me robaron el celular: las primeras 2 horas

Cada minuto cuenta. Actúa **en este orden**:

| # | Acción | Detalle |
|---|---|---|
| 1 | **Localiza y bloquea el dispositivo** | Buscar / Find Hub desde otro equipo. Márcalo como perdido. **No intentes recuperarlo personalmente** si puede ponerte en riesgo |
| 2 | **Contacta a tu operador** | Bloquea la SIM/eSIM y reporta el equipo para evitar el uso de tu línea |
| 3 | **Protege tu correo principal** | Revisa accesos recientes, dispositivos conectados y sesiones desconocidas |
| 4 | **Contacta a tus entidades financieras** | Bloquea temporalmente productos o accesos si hay riesgo |
| 5 | **Revisa tus cuentas críticas** | Apple/Google · gestor de contraseñas · WhatsApp · redes sociales · nube |
| 6 | **Alerta a tus contactos** | Si alguien puede estar usando tu identidad, avisa para evitar fraudes a familiares y amigos |
| 7 | **Denuncia** | Ver [Si ya te pasó](07-si-ya-te-paso.md) |

> **No empieces cambiando 50 contraseñas al azar.** Protege primero las cuentas que controlan a las demás: tu correo principal es la puerta de recuperación de casi todo lo demás.

---

[← Anterior: Ingeniería social](02-ingenieria-social.md) · [Volver al índice](index.md) · [Siguiente: Privacidad y rastreo →](04-privacidad-y-rastreo.md)
