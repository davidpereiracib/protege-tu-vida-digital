<p align="center">
  <img src="https://raw.githubusercontent.com/davidpereiracib/protege-tu-vida-digital/main/assets/img/secpro-color.png" alt="SecPro — Security Professionals" width="240">
</p>

# Protege tu Vida Digital

> Herramientas recomendadas para cada acción de ciberseguridad personal.
> Material de apoyo de los Focus Group **"Cómo administrar y proteger tu vida digital a nivel personal"** y **"Cómo identificar fraudes en Internet"**.

**🌐 También disponible como sitio web: [protege.secpro.co](https://protege.secpro.co)**

Tu identidad ya no necesita ser hackeada. Hoy se construye —y se roba— a partir de piezas que ya están repartidas por el mundo digital: tu nombre, tu rostro, tu voz, tu ubicación, tus dispositivos y hasta tus conversaciones con una IA.

Este repositorio recoge **las herramientas concretas** para cada una de las acciones que vimos en las sesiones. Todas son de acceso público. Ninguna requiere conocimientos técnicos avanzados.

> ### 🛡️ ¿Vienes del Focus Group sobre fraudes?
>
> Ve directo al **[Kit antifraude](fraudes.md)**: las seis acciones de esta semana y las herramientas para verificar un enlace, un perfil, una empresa o un comprobante antes de decidir.

---

## Empieza por aquí: las 7 acciones

Si solo vas a hacer siete cosas, que sean estas. Están ordenadas por impacto.

| # | Acción | Herramientas | Guía |
|---|--------|--------------|------|
| 1 | **Deja de reutilizar contraseñas** | [Bitwarden](https://bitwarden.com) · [1Password](https://1password.com) · [Proton Pass](https://proton.me/pass) | [Cuentas e identidad](01-cuentas-e-identidad.md) |
| 2 | **Mejora tu autenticación** | [Passkeys](https://passkeys.directory) · [Ente Auth](https://ente.io/auth) · [YubiKey](https://www.yubico.com) | [Cuentas e identidad](01-cuentas-e-identidad.md) |
| 3 | **Prepara tu celular para un robo** | Protección antirrobo nativa · PIN de SIM · [Find Hub](https://google.com/android/find) | [Tu teléfono](03-tu-telefono.md) |
| 4 | **Revisa quién tiene acceso** | [Google](https://myaccount.google.com/connections) · [Microsoft](https://account.microsoft.com/privacy) · [Apple](https://appleid.apple.com) | [Cuentas e identidad](01-cuentas-e-identidad.md) |
| 5 | **Reduce lo que compartes** | [Exodus Privacy](https://reports.exodus-privacy.eu.org/es/) · [My Ad Center](https://myadcenter.google.com) | [Privacidad y rastreo](04-privacidad-y-rastreo.md) |
| 6 | **Revisa lo que entregas a la IA** | Controles de privacidad de cada plataforma | [Inteligencia artificial](05-inteligencia-artificial.md) |
| 7 | **Crea un protocolo familiar** | Una palabra secreta. Gratis y es la mejor defensa contra la voz clonada | [Ingeniería social](02-ingenieria-social.md) |

**¿Por dónde empezar hoy mismo?** Busca tu correo en **[Have I Been Pwned](https://haveibeenpwned.com)**. Toma quince segundos y te dice si tus credenciales ya están circulando.

---

## Contenido por tema

| Guía | Qué encontrarás |
|---|---|
| **[01 · Cuentas e identidad](01-cuentas-e-identidad.md)** | Gestores, passkeys, segundo factor, recuperación de cuentas, permisos OAuth |
| **[02 · Ingeniería social e IA](02-ingenieria-social.md)** | Phishing y sus variantes, voz clonada, deepfakes, verificación de contenido |
| **[03 · Tu teléfono](03-tu-telefono.md)** | Blindaje antirrobo, SIM swap, spyware, qué hacer en las primeras 2 horas |
| **[04 · Privacidad y rastreo](04-privacidad-y-rastreo.md)** | Fingerprinting, trackers en apps, DNS, navegadores, alias de correo |
| **[05 · Inteligencia artificial](05-inteligencia-artificial.md)** | Qué compartes con la IA, agentes con permisos, mínimo privilegio |
| **[06 · Respaldo y continuidad](06-respaldo-y-continuidad.md)** | Regla 3-2-1, cifrado, herencia digital |
| **[07 · Si ya te pasó (Colombia)](07-si-ya-te-paso.md)** | Rutas de denuncia, conservación de evidencia, contactos oficiales |
| **[✅ Checklist imprimible](CHECKLIST.md)** | Para marcar mientras avanzas |
| **[🤝 Cómo contribuir](CONTRIBUTING.md)** | Reporta enlaces rotos o propón herramientas |

---

## 🛡️ Reconocer y verificar fraudes

Del Focus Group **"Cómo identificar fraudes en Internet"**. Si los capítulos anteriores tratan de *cerrar puertas*, estos tratan de *reconocer a quien toca*.

| Guía | Qué encontrarás |
|---|---|
| **[🛡️ Kit antifraude](fraudes.md)** | **Empieza aquí.** Las 6 acciones de esta semana y la consulta rápida por situación |
| **[08 · Anatomía del fraude](08-anatomia-del-fraude.md)** | Qué busca el atacante, por dónde entra, las ocho historias, por qué ya no sirve "buscar errores" |
| **[09 · Los nuevos disfraces](09-los-nuevos-disfraces.md)** | Quishing, **ClickFix**, sitios clonados, el CAPTCHA como señuelo, cadenas multicanal |
| **[10 · Cuando el MFA no basta](10-cuando-el-mfa-no-basta.md)** | Robo de sesión y cookies, AITM, fatiga MFA, consent phishing, el código que nunca se comparte |
| **[11 · El fraude que encuentras tú](11-el-fraude-que-encuentras.md)** | Malvertising, buscadores, perfiles falsos, falso soporte técnico, marketplaces |
| **[12 · Verificar antes de confiar](12-verificar-antes-de-confiar.md)** | **El kit completo de herramientas** y la cadena de verificación paso a paso |

### Las 3 ideas que más cuestan de aceptar

| Idea | Por qué importa |
|---|---|
| **Cambiar la contraseña no expulsa a quien ya entró** | Las sesiones abiertas sobreviven al cambio. Hay que cerrarlas aparte — [cómo](10-cuando-el-mfa-no-basta.md) |
| **Una verificación que te pide ejecutar un comando *es* el ataque** | Es la técnica ClickFix, y no hay antivirus que la detenga porque la ejecutas tú — [cómo se ve](09-los-nuevos-disfraces.md) |
| **Una imagen de una evidencia no es la evidencia** | Comprobantes, chats y certificados se editan en segundos — [qué mirar en su lugar](12-verificar-antes-de-confiar.md) |

---

## Las 15 herramientas más útiles

Si quieres una lista corta para empezar:

| Herramienta | Para qué | Costo |
|---|---|---|
| [Have I Been Pwned](https://haveibeenpwned.com) | ¿Tu correo está en una filtración? | Gratis |
| [Bitwarden](https://bitwarden.com) | Gestor de contraseñas | Gratis |
| [Ente Auth](https://ente.io/auth) | Códigos de segundo factor | Gratis |
| [passkeys.directory](https://passkeys.directory) | Qué servicios ya aceptan passkeys | Gratis |
| [Exodus Privacy](https://reports.exodus-privacy.eu.org/es/) | Rastreadores dentro de tus apps | Gratis |
| [Cover Your Tracks](https://coveryourtracks.eff.org/) | Qué tan único es tu navegador | Gratis |
| [urlscan.io](https://urlscan.io) | Analizar un enlace sospechoso sin abrirlo | Gratis |
| [VirusTotal](https://www.virustotal.com/gui/home/url) | Segunda opinión sobre enlaces y archivos | Gratis |
| [Content Credentials](https://contentcredentials.org/verify) | ¿Esta imagen fue generada con IA? | Gratis |
| [DeepFake-O-Meter](https://zinc.cse.buffalo.edu/ubmdfl/deep-o-meter/) | Detección de deepfake en imagen, video y audio | Gratis |
| [SimpleLogin](https://simplelogin.io) | Alias de correo desechables | Gratis / de pago |
| [NextDNS](https://nextdns.io) | Ver y bloquear a dónde llama tu teléfono | Gratis hasta cierto uso |
| [Cryptomator](https://cryptomator.org) | Cifrar archivos antes de subirlos a la nube | Gratis |
| [Signal](https://signal.org) | Mensajería cifrada verificable | Gratis |
| [Security Planner](https://securityplanner.consumerreports.org) | Plan personalizado según tu riesgo | Gratis |

---

## Cómo usar este repositorio

No intentes hacerlo todo en un día. La seguridad perfecta no existe; **la seguridad proporcional sí**.

1. Abre el **[checklist](CHECKLIST.md)** y marca lo que ya tienes.
2. Haz las **acciones 1 y 2** esta semana. Son las que más reducen tu riesgo.
3. Agenda una revisión **dos veces al año** para los permisos y las sesiones abiertas.
4. Define la **palabra secreta familiar** hoy mismo. No cuesta nada y es la única defensa que la IA no puede replicar.

---

## Un principio que vale más que cualquier herramienta

> **Confianza + emoción + urgencia → acción**

Esa es la fórmula de casi todo fraude, sin importar el canal. Cuando algo te apure, ese apuro *es* la señal de alarma.

Ninguna emergencia real empeora porque te tomes dos minutos para verificar por otro canal.

---

## Aviso

Este material tiene fines **educativos y de concienciación**. Las herramientas listadas son de terceros: revisa sus políticas de privacidad y términos antes de usarlas. La inclusión de una herramienta no constituye respaldo comercial ni garantía de funcionamiento.

Los enlaces se verificaron en **septiembre de 2026**. El panorama cambia rápido: si encuentras un enlace roto, una herramienta que cambió de condiciones o una alternativa mejor, **[repórtalo](https://github.com/davidpereiracib/protege-tu-vida-digital/issues/new)**. Ver [cómo contribuir](CONTRIBUTING.md).

---

## Créditos

**David Pereira** — CEO de SecPro
Investigador y consultor en ciberseguridad, +29 años
Autor de *Ciberseguridad al Alcance de Todos* y *Cyber Threat Hunters Handbook*

📧 info@secpro.co

Material de apoyo de los Focus Group **"Cómo administrar y proteger tu vida digital a nivel personal"** y **"Cómo identificar fraudes en Internet"**.

---

## Licencia

[CC BY 4.0](LICENSE) — puedes compartir y adaptar este material citando la fuente.

---

<p align="center">
  <img src="https://raw.githubusercontent.com/davidpereiracib/protege-tu-vida-digital/main/assets/img/secpro-color.png" alt="SecPro" width="150"><br>
  <sub><b>© 2026 David Pereira · SecPro — Security Professionals.</b><br>
  Material educativo de concienciación. Publicado bajo licencia
  <a href="https://creativecommons.org/licenses/by/4.0/deed.es">CC BY 4.0</a>:
  puedes compartirlo y adaptarlo citando la fuente.<br>
  <a href="https://secpro.co">secpro.co</a> · info@secpro.co</sub>
</p>
