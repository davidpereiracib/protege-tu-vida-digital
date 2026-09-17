# 10 · Cuando el MFA no basta

> *El objetivo real del atacante no es tu contraseña. Es conseguir una forma válida de actuar como tú.*

Activar el segundo factor es una de las mejores decisiones que puedes tomar, y este capítulo **no dice lo contrario**. Dice algo más incómodo: cuando proteges bien la puerta, el atacante deja de intentar abrirla y empieza a buscar otras formas de entrar.

Puede intentar quedarse con una **sesión ya autenticada**. Puede buscar un **token**. Puede lograr que **tú apruebes** una solicitud que él inició. Puede pedirle permisos a una aplicación en lugar de pedirte la contraseña a ti.

---

## 🍪 Robo de sesión: entrar sin volver a iniciar sesión

Cuando inicias sesión, el servicio necesita recordarte. Para eso guarda en tu navegador un **identificador de sesión** (una cookie o un token).

A partir de ese momento, **esa cadena de caracteres eres tú** para el sistema.

> OWASP lo dice sin rodeos: un identificador de sesión autenticada puede ser **temporalmente equivalente al método de autenticación** que usaste para obtenerlo.
> — [Session Management Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html)

Si ese token se roba, el atacante lo pega en su navegador y entra. **No escribe tu contraseña. No toca tu segundo factor.** El servidor no nota nada raro, porque para él todo está en orden.

### Cómo se roba en la vida real

| Vía | Cómo funciona |
|---|---|
| **Infostealer** | Un programa en tu equipo copia las cookies del navegador, las contraseñas guardadas y el historial. No rompe nada: solo se lleva lo que ya estaba ahí |
| **Adversary-in-the-Middle** | Una página intermedia retransmite tu inicio de sesión al sitio real. Tú superas el MFA de verdad, y el atacante se queda con la sesión que sale al final |
| **Equipo compartido o robado** | Sesión abierta en un computador que dejó de estar bajo tu control |

### 🔴 Lo que casi nadie sabe

**Cambiar la contraseña no expulsa a quien ya está adentro.**

En muchos servicios, cambiar la clave **no invalida las sesiones que ya estaban abiertas**. El atacante sigue trabajando con la cookie que se llevó, mientras tú crees que resolviste el problema.

El botón que sirve es otro: **"cerrar sesión en todos los dispositivos"**.

| Servicio | Dónde se cierran las sesiones |
|---|---|
| **Google** | https://myaccount.google.com/device-activity |
| **Microsoft** | https://account.microsoft.com/security |
| **Apple** | https://appleid.apple.com |
| **WhatsApp** | Ajustes → Dispositivos vinculados |
| **Instagram / Facebook** | Configuración → Centro de cuentas → Contraseña y seguridad → Dónde iniciaste sesión |

> **El orden correcto ante cualquier sospecha:**
> 1. Cerrar **todas** las sesiones
> 2. Cambiar la contraseña
> 3. Revisar las aplicaciones con acceso *(más abajo en este capítulo)*
> 4. Revisar los métodos de recuperación — el atacante pudo haberlos cambiado

---

## 🕵️ AITM: el intermediario que no ves

En un ataque **Adversary-in-the-Middle**, crees que te estás autenticando con normalidad mientras una infraestructura intermedia retransmite todo hacia el sitio real.

- El sitio falso replica la experiencia real **porque literalmente la está reenviando**
- Tus credenciales y tu sesión se capturan durante el proceso
- El código de tu autenticador **funciona de verdad**, y por eso no notas nada

**Esto no significa que el MFA sea inútil.** Significa que **no todos los factores resisten igual al phishing**:

| Factor | ¿Resiste a un sitio intermediario? |
|---|---|
| SMS | ❌ No — se retransmite igual que la contraseña |
| Código de app (TOTP) | ❌ No — también se retransmite |
| Notificación push de aprobación | ❌ No, si la apruebas |
| **Passkey / FIDO2 / llave física** | ✅ **Sí** |

La razón es sencilla y es lo único técnico que vale la pena entender: **una passkey está atada criptográficamente al dominio legítimo**. En el sitio del intermediario, sencillamente no funciona. No detecta el ataque: lo hace imposible.

| Recurso | Para qué | Enlace |
|---|---|---|
| **Passkeys · FIDO Alliance** | Qué son y cómo funcionan | https://fidoalliance.org/passkeys/ |
| **passkeys.directory** | Qué servicios ya las aceptan | https://passkeys.directory |

Cómo activarlas está en [Cuentas e identidad](01-cuentas-e-identidad.md).

---

## 🔔 Fatiga MFA: aprobar por cansancio

Hay ataques que ni siquiera intentan romper el segundo factor. Buscan que **tú mismo lo apruebes**.

- Llegan muchas notificaciones de autenticación que no iniciaste
- La repetición busca cansancio, confusión o un toque accidental
- A veces llega acompañada de una llamada de "soporte" que te pide aprobar "para que paren"
- Suele ocurrir de madrugada, cuando quieres que el teléfono deje de vibrar

> **Si tú no iniciaste el acceso, no hay nada que aprobar.**

Una solicitud de MFA inesperada **no es una molestia: es una alarma**. Significa que alguien ya tiene tu contraseña y solo le falta esto. Deniégala, y ve a cambiar esa contraseña de inmediato.

---

## 🔓 Consent phishing: cuando el acceso se lo das tú

Esta es la más elegante y la más difícil de detectar, porque **no hay nada roto en ningún momento**.

OAuth es la función que permite que una aplicación pida permisos sobre tu cuenta — lo que ocurre cada vez que usas "Iniciar sesión con Google". Es legítima, es útil, y también puede ser el centro del engaño.

**Cómo se ve:**

1. Inicias sesión en el servicio **real** — Google, Microsoft. Todo correcto
2. Aparece una pantalla pidiendo autorizar una aplicación
3. Aceptas
4. Esa aplicación ahora puede leer tu correo, tus archivos o tus contactos **sin tu contraseña y sin tu segundo factor**, hasta que se lo revoques

> **Autenticarte correctamente no impide que autorices algo incorrecto.**

### Qué revisar antes de pulsar "Permitir"

- **Quién publica la aplicación** — no el nombre que se puso, sino el editor verificado
- **Si el nombre imita a uno conocido** — "Google Drive Sync", "Microsoft Office Viewer"
- **El alcance de los permisos** — lee la frase completa, aunque sea larga
- **Si tiene sentido** — un editor de PDF que pide leer todo tu correo no lo tiene

### Revisa lo que ya autorizaste

Casi nadie recuerda esta lista, y casi siempre es más larga de lo esperado.

| Servicio | Dónde se revisa | Enlace |
|---|---|---|
| **Google** | Aplicaciones con acceso a tu cuenta | https://myaccount.google.com/permissions |
| **Google** | Revisión de seguridad guiada | https://myaccount.google.com/security-checkup |
| **Microsoft** | Mis aplicaciones | https://myapps.microsoft.com |
| **Microsoft** | Seguridad de la cuenta | https://account.microsoft.com/security |
| **Apple** | Iniciar sesión con Apple | https://appleid.apple.com |

**Hazlo dos veces al año.** Revoca todo lo que no reconozcas o ya no uses: es gratis y no rompe nada que te importe.

---

## 🔢 El código que nunca deberías dar

Los códigos de un solo uso aparecen justo cuando estás haciendo algo sensible. Por eso el atacante intenta conseguirlos **en tiempo real**.

- **No dictes** códigos recibidos por SMS, app o correo a alguien que te contactó
- **No apruebes** una solicitud que no iniciaste
- Un supuesto banco o soporte usa ese código para completar **su propia** operación, en ese mismo instante
- Ante la duda: **termina el contacto y entra tú** por el canal oficial

> **El código valida una acción. No valida a quien te lo está pidiendo.**

Ningún banco, ninguna empresa y ningún soporte técnico necesita que le leas un código. Si te lo piden, la conversación terminó. Sin discutir y sin pena: se cuelga.

**Dato útil para reconocerlo:** el mensaje del código casi siempre incluye la frase *"no compartas este código con nadie"*. Está ahí precisamente porque esta estafa es masiva.

---

## Lo que tienes que recordar de este capítulo

1. La sesión abierta vale tanto como la contraseña. **Aprende dónde se cierran todas.**
2. Cambiar la clave **no** expulsa a nadie. Cerrar sesiones, sí.
3. No todos los segundos factores resisten igual. **Las passkeys sí.**
4. Una solicitud de MFA que no pediste es una alarma, no un estorbo.
5. Revisa dos veces al año **qué apps tienen llave de tu cuenta**.
6. El código de seis dígitos no se dicta nunca. A nadie.

---

[← Anterior: Los nuevos disfraces](09-los-nuevos-disfraces.md) · [Volver al índice](index.md) · [Siguiente: El fraude que encuentras tú →](11-el-fraude-que-encuentras.md)

---

<p align="center">
  <img src="https://raw.githubusercontent.com/davidpereiracib/protege-tu-vida-digital/main/assets/img/secpro-color.png" alt="SecPro" width="150"><br>
  <sub><b>© 2026 David Pereira · SecPro — Security Professionals.</b><br>
  Material educativo de concienciación. Publicado bajo licencia
  <a href="https://creativecommons.org/licenses/by/4.0/deed.es">CC BY 4.0</a>:
  puedes compartirlo y adaptarlo citando la fuente.<br>
  <a href="https://secpro.co">secpro.co</a> · info@secpro.co</sub>
</p>
