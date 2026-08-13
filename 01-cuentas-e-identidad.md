# 01 · Protección de cuentas e identidad

> *La contraseña sola ya no puede defenderte.*

Una vez que inicias sesión, tu contraseña deja de ser la única forma en que un servicio confía en ti. Tu acceso también depende de **sesiones activas**, **dispositivos reconocidos** y **métodos de recuperación**. Proteger una cuenta es más que proteger su contraseña.

---

## ¿Tus credenciales ya están circulando?

| Herramienta | Qué hace | Enlace |
|---|---|---|
| **Have I Been Pwned** | Busca tu correo en filtraciones conocidas | https://haveibeenpwned.com |
| **Pwned Passwords** | Comprueba si una contraseña ya apareció en brechas | https://haveibeenpwned.com/Passwords |
| **Notificaciones automáticas** | Te avisa si apareces en filtraciones futuras | https://haveibeenpwned.com/NotifyMe |
| **Dashboard (stealer logs)** | Registros de equipos infectados que capturaron tu correo | https://haveibeenpwned.com/Dashboard |

**Sobre Pwned Passwords:** el sitio nunca recibe tu contraseña completa. Tu navegador calcula un hash y envía solo los primeros caracteres; la comparación final ocurre en tu equipo. Se llama *k-anonymity*.

**Sobre los stealer logs:** requieren que verifiques tu correo en el Dashboard, y con razón. Una filtración expone la base de datos de una empresa; un *stealer log* expone **tu propio equipo**: las direcciones exactas, el usuario y la contraseña que tenías guardados en el navegador.

---

## Gestores de contraseñas

Recordar una contraseña distinta para cada cuenta es imposible. Para eso existe el gestor.

| Herramienta | Notas | Enlace |
|---|---|---|
| **Bitwarden** | Código abierto, plan gratuito muy completo | https://bitwarden.com |
| **1Password** | La mejor experiencia con passkeys | https://1password.com |
| **Proton Pass** | Enfocado en privacidad, incluye alias de correo | https://proton.me/pass |
| **KeePassXC** | Totalmente local, sin nube | https://keepassxc.org |

**Lo que casi nadie aprovecha:** el gestor **detecta phishing antes que tú**. Si estás en una página falsa, el dominio no coincide y el autocompletado sencillamente no ofrece la credencial. Esa ausencia es una señal.

> ⚠️ **La contraseña maestra es la única que debes memorizar.** Debe ser larga, única y protegida con segundo factor. Si la pierdes, **nadie** puede recuperártela. Escríbela en papel y guárdala donde guardas los documentos importantes de tu casa.

---

## Passkeys: iniciar sesión sin contraseña

Verifican tu identidad con el mecanismo de seguridad de tu propio dispositivo: huella, rostro o PIN.

| Recurso | Para qué | Enlace |
|---|---|---|
| **passkeys.directory** | Catálogo de servicios que ya las aceptan — busca tu banco | https://passkeys.directory |
| **passkeys.io** | Demostración para probar cómo funciona | https://www.passkeys.io |
| **webauthn.io** | Detalle técnico del estándar | https://webauthn.io |

**Por qué resisten el phishing:** la llave privada nunca sale de tu dispositivo, y está **atada al dominio correcto**. Si el sitio es un impostor, tu dispositivo sencillamente no ofrece la llave. No es que el usuario sea más cuidadoso: es que el navegador no le deja cometer el error.

---

## Segundo factor: no todos valen lo mismo

**Jerarquía, de más a menos seguro:**

```
Passkey  >  Llave física  >  App TOTP  >  Notificación push  >  SMS  >  nada
```

| Herramienta | Tipo | Enlace |
|---|---|---|
| **Ente Auth** | App TOTP, cifrada, con respaldo y multiplataforma | https://ente.io/auth |
| **Aegis** | App TOTP para Android, código abierto | https://getaegis.app |
| **YubiKey** | Llave física | https://www.yubico.com |

### El problema del MFA por SMS

El código del SMS depende de algo que también puede comprometerse: **tu número telefónico**.

- **SIM swap** — un tercero consigue trasladar tu línea a otra SIM o eSIM
- **Ingeniería social** — te engañan para que reveles el código
- **Recuperación de cuentas** — muchos servicios aún usan el número para restablecer accesos

**¿Debes desactivarlo?** No. Un segundo factor sigue siendo mejor que solo una contraseña. Pero cuando el servicio ofrezca algo más resistente, cámbiate. Tu número no debería ser la única barrera entre un atacante y tu identidad.

---

## Adversary-in-the-Middle: cuando el 2FA no basta

Tener doble factor no convierte una página falsa en una página segura. En estos ataques el sitio falso actúa como **intermediario** entre tú y el servicio legítimo:

1. Recibes un enlace que parece legítimo
2. Introduces tus credenciales — el intermediario las reenvía al servicio real
3. Completas correctamente tu segundo factor — también se reenvía
4. Incluso terminas viendo el servicio real

El segundo factor **funcionó**. Pero la sesión ya autenticada quedó en manos del atacante.

**Las tres reglas:**
- No apruebes un inicio de sesión que tú no comenzaste
- No accedas a cuentas sensibles desde enlaces recibidos por correo, SMS o mensajería
- Ante la duda, abre la aplicación directamente o escribe tú mismo la dirección

---

## Revisa quién tiene acceso a tus cuentas

Con los años acumulamos permisos que olvidamos que existen. El día que **esa empresa** sea vulnerada, el atacante entra a tus datos sin tocar tu contraseña y sin disparar tu segundo factor.

| Plataforma | Dónde revisar |
|---|---|
| **Google** | https://myaccount.google.com/connections |
| **Google · revisión de seguridad** | https://myaccount.google.com/security-checkup |
| **Microsoft** | https://account.microsoft.com/privacy |
| **Apple** | https://appleid.apple.com → *Iniciar sesión con Apple* |
| **Facebook** | Configuración → *Apps y sitios web* |

> Es la limpieza de mayor impacto por minuto invertido que existe. Hazla **dos veces al año**.

---

## Prepárate antes de necesitar recuperar una cuenta

Cambiaste de teléfono. Perdiste la SIM. El dispositivo dejó de funcionar. Y de repente **tú tampoco puedes demostrar que eres tú**.

- **Correo de recuperación** — debe seguir activo, protegido y bajo tu control
- **Número de recuperación** — mantenlo actualizado y elimina números antiguos
- **Códigos de recuperación** — guárdalos **fuera** del dispositivo que usas para autenticarte. Imprímelos.
- **Dispositivos vinculados** — revisa periódicamente cuáles pueden acceder

**Empieza por tus cuentas críticas:** correo principal · gestor de contraseñas · Apple/Google/Microsoft · bancos · nube.

> Perder el acceso por no tener los códigos de recuperación pasa **más** que ser hackeado.

---

## Tu exposición pública

Ver qué información tuya circula ya es parte de proteger tu identidad.

| Herramienta | Qué revela | Enlace |
|---|---|---|
| **Resultados sobre ti (Google)** | Monitoriza y solicita remover datos personales de las búsquedas | https://myactivity.google.com/results-about-you |
| **Formulario de remoción** | Solicitar retiro de resultados | https://support.google.com/websearch/answer/9673730 |
| **WhatsMyName** | Dónde existe tu nombre de usuario habitual | https://whatsmyname.app |
| **Epieos** | Qué servicios están asociados a un correo | https://epieos.com |

> **Importante:** remover un resultado de Google **no borra el dato**. La página original sigue existiendo. El orden correcto es: primero pedirle al sitio que lo baje, después pedirle a Google que lo desindexe.

⚠️ Usa estas herramientas **sobre ti mismo**. Investigar a terceros sin su consentimiento puede constituir un delito y, como mínimo, vulnera la Ley 1581 de 2012.

---

[← Volver al índice](README.md) · [Siguiente: Ingeniería social e IA →](02-ingenieria-social.md)
