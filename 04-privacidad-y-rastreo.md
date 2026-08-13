# 04 · Privacidad y rastreo

> *Borrar las cookies ya no significa desaparecer.*

Durante años pensamos: "borro las cookies y empiezo de cero". Hoy el seguimiento digital usa muchas otras señales: dirección IP, identificadores del dispositivo, ubicación, cuentas donde iniciaste sesión, datos generados por aplicaciones y actividad entre servicios distintos.

---

## El modo incógnito: qué hace y qué no

**Sí hace:** evita que parte del historial y las cookies queden guardados localmente en tu dispositivo al cerrar la sesión.

**No hace:**
- ❌ Volverte anónimo en Internet
- ❌ Ocultar tu actividad a los sitios que visitas
- ❌ Evitar todas las formas de seguimiento

> El incógnito protege de la persona que use tu computador **después** de ti. De nadie más.

---

## Tu navegador tiene una huella

Por separado, estos datos parecen insignificantes: resolución de pantalla, navegador y versión, sistema operativo, idioma, zona horaria, características gráficas, fuentes instaladas.

Pero al combinarlos —`1920×1080 + Windows + Firefox + español + GMT-5 + configuración gráfica`— forman un **fingerprint** que puede reconocerte sin necesitar una sola cookie.

| Herramienta | Qué te muestra | Enlace |
|---|---|---|
| **Cover Your Tracks** (EFF) | Qué tan único es tu navegador, en lenguaje claro | https://coveryourtracks.eff.org/ |
| **AmIUnique** | Desglose atributo por atributo | https://amiunique.org/fingerprint |
| **BrowserLeaks** | El más técnico: Canvas, WebGL, fuentes, WebRTC | https://browserleaks.com/ |
| **PrivacyTests** | Comparativa de navegadores, muy visual | https://privacytests.org |

**Pruébalo:** corre el test en tu navegador habitual y luego en uno con protección anti-fingerprinting. La diferencia se ve de inmediato.

---

## Navegadores y bloqueo

| Herramienta | Enfoque | Enlace |
|---|---|---|
| **Brave** | Bloqueo de rastreadores por defecto | https://brave.com |
| **Mullvad Browser** | Anti-fingerprinting serio | https://mullvad.net/browser |
| **DuckDuckGo** | Buscador y navegador con menos rastreo | https://duckduckgo.com |
| **uBlock Origin** | La extensión de bloqueo de referencia | https://ublockorigin.com |

---

## Las aplicaciones también te observan

Cuando instalas una app, no solo importa qué hace. Importa **a qué le diste acceso**:

- **Ubicación** — ¿la necesita siempre o solo mientras la usas?
- **Micrófono y cámara** — ¿tiene sentido para su función?
- **Contactos** — ¿realmente necesita tu agenda completa?
- **Fotos y archivos** — ¿toda la galería o solo lo que selecciones?
- **Notificaciones** — pueden revelar información sensible en la pantalla bloqueada

### Lo que no ves: los SDK de terceros

Muchas apps integran componentes de terceros para analítica, publicidad, medición, reporte de errores y atribución. **Esos SDK no son de la app**: son de empresas que le pagan al desarrollador por dejarlos entrar.

| Herramienta | Qué revela | Enlace |
|---|---|---|
| **Exodus Privacy** | Rastreadores y permisos dentro de apps de Android | https://reports.exodus-privacy.eu.org/es/ |
| **AppCensus** | Comportamiento real de red de las aplicaciones | https://appcensus.io |

**Haz la prueba:** busca en Exodus una app que uses a diario. Compara lo que encuentres con lo que declara su ficha de "Seguridad de los datos" en Google Play o "Privacidad de la app" en la App Store.

> Ninguna de esas apps te hackeó. Todas te pidieron permiso, y dijiste que sí.

---

## Ver a dónde llama tu teléfono

| Herramienta | Qué hace | Enlace |
|---|---|---|
| **NextDNS** | Registra y bloquea las consultas DNS de tus dispositivos | https://nextdns.io |
| **Control D** | Alternativa equivalente | https://controld.com |

Se configura en el teléfono en dos minutos (iPhone: perfil de configuración; Android: DNS privado). Después puedes ver, **en tiempo real**, a qué dominios se conecta tu dispositivo incluso mientras duermes.

Es la forma más rápida de hacer visible lo invisible. Y bloquear rastreadores no requiere cambiar de teléfono ni instalar antivirus: es una línea de configuración.

---

## Lo que buscas también dice quién eres

Hay cosas que nunca publicarías en una red social, pero sí las buscarías en Internet: síntomas y medicamentos, créditos y deudas, planes de viaje, intenciones de compra, temas de vida personal, necesidades locales.

Una búsqueda aislada puede significar poco. Pero una secuencia como *"dolor de rodilla" → "ortopedista cerca" → "precio resonancia"* revela mucho más contexto que cualquiera por separado.

### Recupera el control

| Acción | Dónde |
|---|---|
| **Ver y borrar tu actividad** | https://myactivity.google.com |
| **Activar borrado automático** (3 meses) | https://myactivity.google.com/activitycontrols |
| **Ver los temas con los que te perfilan** | https://myadcenter.google.com |
| **Actividad de Maps** | https://myactivity.google.com/product/maps |
| **Descargar todo lo que tienen de ti** | https://takeout.google.com |
| **Privacidad de Microsoft** | https://account.microsoft.com/privacy |

> **Nota sobre la ubicación:** Google retiró la Cronología web en junio de 2025 y movió los datos al dispositivo. El recorrido en mapa hoy solo está en la app de Google Maps del celular → foto de perfil → *Tu cronología*. En la migración solo se conservaron los últimos 90 días: mucha gente perdió años de historial sin enterarse. No hace falta un atacante para perder tus datos; basta con que la empresa cambie de opinión.

---

## Compartimentar: alias de correo

Un correo distinto por servicio te da dos cosas: privacidad y **trazabilidad**. Si mañana llega spam a un alias concreto, sabes exactamente quién vendió tu dato.

| Herramienta | Enlace |
|---|---|
| **SimpleLogin** | https://simplelogin.io |
| **Firefox Relay** | https://relay.firefox.com |
| **DuckDuckGo Email Protection** | https://duckduckgo.com/email |
| **Ocultar mi correo** (Apple) | Integrado en iCloud+ |

Lo mismo aplica a las **tarjetas virtuales** que ofrecen varios bancos: un número distinto por suscripción, con tope de monto. Cuando quieras cancelar un servicio y no te dejen, matas la tarjeta.

---

## Mensajería verificable

| Herramienta | Por qué | Enlace |
|---|---|---|
| **Signal** | Cifrado extremo a extremo **comprobable** | https://signal.org |

Abre un chat → toca el nombre del contacto → **Ver número de seguridad**. Si ambos escanean el código del otro en persona, tienen **prueba criptográfica** de que nadie está en el medio. No se trata de confiar en la aplicación: se trata de poder verificarlo.

---

## Limpia lo que ya no usas

Aplicaciones abandonadas, cuentas de tiendas, foros y juegos antiguos, servicios que probaste una vez. Todo eso sigue siendo parte de tu superficie digital, y cada uno es una filtración potencial con tus datos dentro.

**Hazlo dos veces al año.**

---

[← Anterior: Tu teléfono](03-tu-telefono.md) · [Volver al índice](README.md) · [Siguiente: Inteligencia artificial →](05-inteligencia-artificial.md)
