# 12 · Verificar antes de confiar

> *Verificar no busca una señal mágica. Busca contradicciones.*

Este es el capítulo práctico: **qué puedes revisar tú mismo**, sin ser técnico y sin instalar nada, antes de tomar una decisión.

Nada de lo que sigue requiere permiso, cuesta dinero o toma más de un minuto.

---

## ⏱️ Los diez segundos antes del clic

| Dónde estás | Qué haces |
|---|---|
| **En computador** | Pon el cursor **encima** del enlace, sin hacer clic. La dirección real aparece abajo a la izquierda |
| **En celular** | **Mantén presionado** el enlace para previsualizarlo o copiarlo antes de abrirlo |
| **Ante un QR** | Escanea y **lee la dirección que muestra la cámara** antes de continuar |
| **Siempre** | Si el texto visible y el destino **no coinciden**, detente ahí |

> Unos segundos antes del clic revelan lo que la apariencia intenta esconder.

---

## 🔤 Leer una URL: la habilidad más rentable

Ver la dirección solo sirve si sabes qué parte importa.

```
https://login.banco.seguridad-pagos[.]com/ingreso
                    └───────┬───────┘
                     el dominio real
```

**Lee de derecha a izquierda desde la primera barra `/`.** Lo último antes de esa barra es quien controla el sitio.

- Las palabras que están **antes** pueden ser simples subdominios, y las escribe el mismo dueño
- Busca **letras sustituidas**, guiones de más, errores mínimos y extensiones inesperadas
- El candado indica **cifrado hacia ese dominio**, no que ese dominio pertenezca a la marca
- En Colombia, el Estado usa **`.gov.co`**, que no se vende libremente. `gov-co` dentro de un `.com` es un dominio comercial cualquiera

> **Primero identifica quién controla el dominio. Después evalúa el resto de la página.**

**Practica gratis:** el [quiz de phishing de Google](https://phishingquiz.withgoogle.com) son ocho ejemplos reales y toma cinco minutos.

---

## 🔍 Busca antes de creer

Cuando algo genera duda, Internet también sirve para **investigar el propio mensaje**.

- Busca **una frase distintiva entre comillas**. Si es una campaña masiva, aparecerán reportes de otras personas
- Consulta el **teléfono, correo o usuario** junto con las palabras `fraude`, `estafa` o `scam`
- Contrasta los datos de la empresa con **registros oficiales**
- **Nunca verifiques usando el mismo número o enlace que recibiste**

> **Una buena verificación introduce información que el atacante no controla.**

Ese es el criterio para saber si lo que hiciste sirvió de algo. Llamar al número del mensaje no es verificar: es seguir dentro de la historia.

---

## 🖼️ Las evidencias también se falsifican

Una de las trampas más efectivas consiste en mostrarte una **"prueba"** para que dejes de verificar. Y funciona: una prueba en pantalla apaga la duda.

- Una **captura de una transferencia** no demuestra que el dinero esté en tu cuenta
- Conversaciones y comprobantes **se editan**, y no hace falta saber diseño: cualquier navegador permite modificar el texto de una página en segundos
- Documentos, carnés y certificados **se copian o se generan**
- Con IA, también se fabrica la foto de un documento de identidad

> **Una imagen de una evidencia no es la evidencia.**

**La prueba fuerte está en el sistema de origen:** tu cuenta bancaria consultada por ti, en tu app; el registro oficial; un canal independiente. No es *"me mostró el comprobante"*. Es *"entré a mi cuenta y el dinero está ahí"*.

| Herramienta | Qué hace | Enlace |
|---|---|---|
| **Content Credentials** | Lee la procedencia criptográfica de una imagen | https://contentcredentials.org/verify |
| **FotoForensics** | Análisis de errores de compresión: revela zonas editadas | https://fotoforensics.com |
| **Forensically** | Lupa, clonación y metadatos en el navegador | https://29a.ch/photo-forensics/ |

> ⚠️ Estas herramientas **no dan veredictos**. Una imagen sin credenciales no es falsa: significa que no sabemos. Y basta con abrir y volver a guardar un archivo para borrar sus metadatos.

---

## 🧰 El kit antifraude

Ordenado por **la pregunta que te estás haciendo**, no por tipo de herramienta. Todas son gratuitas salvo donde se indica.

### Tengo un enlace, un QR o un archivo

| Herramienta | Qué te responde | Enlace |
|---|---|---|
| **VirusTotal** | Reputación del enlace, dominio o archivo en decenas de motores | https://www.virustotal.com/gui/home/url |
| **urlscan.io** | Captura y comportamiento de la página **sin que tú la visites** | https://urlscan.io |
| **Google Safe Browsing** | Qué opina Google de ese sitio concreto | https://transparencyreport.google.com/safe-browsing/search |
| **WhereGoes** | A dónde lleva un acortador, salto por salto | https://wheregoes.com |
| **URLVoid** | Segunda opinión con otro conjunto de listas | https://www.urlvoid.com |
| **ZXing Decoder** | Qué dirección esconde un QR, sin abrirla | https://zxing.org/w/decode.jspx |
| **Browserling** | Abrir un sitio en un navegador desechable, lejos de tu equipo | https://www.browserling.com |

### Quiero saber de quién es un dominio

| Herramienta | Qué te responde | Enlace |
|---|---|---|
| **ICANN Lookup** | Cuándo se registró y quién figura detrás | https://lookup.icann.org |
| **Wayback Machine** | Si el sitio existía antes o nació esta semana | https://web.archive.org |
| **archive.today** | Copia de una página que puede desaparecer | https://archive.ph |
| **Punycoder** | Si el dominio esconde letras de otro alfabeto | https://www.punycoder.com |
| **dnstwist** | Qué dominios parecidos están registrados y activos | https://dnstwist.it |
| **crt.sh** | Certificados emitidos para ese dominio | https://crt.sh |

### Recibí un correo sospechoso

| Herramienta | Qué te responde | Enlace |
|---|---|---|
| **Google · Message Header Analyzer** | De dónde salió realmente el correo, pegando sus cabeceras | https://toolbox.googleapps.com/apps/messageheader/ |
| **MXToolbox · Email Headers** | Alternativa con más detalle sobre autenticación (SPF/DKIM/DMARC) | https://mxtoolbox.com/emailheaders.aspx |
| **EmailRep** | Reputación de una dirección de correo | https://emailrep.io |
| **PhishTank** | Base colaborativa de enlaces de phishing reportados | https://phishtank.org |

> Las **cabeceras** son la parte del correo que no se ve. En Gmail: los tres puntos → *"Mostrar original"*. Ahí está quién lo envió de verdad, más allá del nombre que aparece.

### Tengo una imagen, un perfil o una cara

| Herramienta | Qué te responde | Enlace |
|---|---|---|
| **Google Lens** | Dónde más aparece esa imagen | https://lens.google.com |
| **TinEye** | Búsqueda inversa orientada al **origen** de la imagen | https://tineye.com |
| **Yandex Images** | Suele ser el más fuerte buscando rostros | https://yandex.com/images |
| **Content Credentials** | Si la imagen trae procedencia firmada (C2PA) | https://contentcredentials.org/verify |
| **FotoForensics** | Si hay zonas editadas dentro de la imagen | https://fotoforensics.com |

Para voz y video fabricados, ver [Ingeniería social e IA](02-ingenieria-social.md).

### Me ofrecen algo: una empresa, una tienda, una inversión

| Herramienta | Qué te responde | Enlace |
|---|---|---|
| **RUES** | Si la empresa existe formalmente en Colombia y desde cuándo | https://www.rues.org.co |
| **Superintendencia Financiera** | Si está autorizada para captar dinero del público | https://www.superfinanciera.gov.co |
| **Rama Judicial · Consulta de procesos** | Si esa "demanda en tu contra" existe de verdad | https://consultaprocesos.ramajudicial.gov.co |
| **ScamAdviser** | Puntaje de confianza de una tienda en línea | https://www.scamadviser.com |
| **Chainabuse** | Si una dirección de criptomonedas fue reportada por estafa | https://www.chainabuse.com |
| **Ads Transparency Center** | Quién paga el anuncio que te trajo hasta ahí | https://adstransparency.google.com |
| **Meta · Biblioteca de Anuncios** | Anuncios activos de un anunciante en Facebook e Instagram | https://www.facebook.com/ads/library |

### Quiero revisar mis propias cuentas

| Herramienta | Qué te responde | Enlace |
|---|---|---|
| **Have I Been Pwned** | En qué filtraciones aparece tu correo | https://haveibeenpwned.com |
| **HIBP · Passwords** | Cuántas veces apareció una contraseña en filtraciones | https://haveibeenpwned.com/Passwords |
| **Google · Apps con acceso** | Qué aplicaciones tienen llave de tu cuenta | https://myaccount.google.com/permissions |
| **Google · Dispositivos** | Qué sesiones están abiertas, y cómo cerrarlas todas | https://myaccount.google.com/device-activity |
| **Microsoft · Seguridad** | Lo mismo, en el entorno corporativo | https://account.microsoft.com/security |
| **Google · Resultados sobre ti** | Qué datos tuyos salen en el buscador y cómo pedir su remoción | https://myactivity.google.com/results-about-you |

### Protegerme antes de tener que dudar

| Herramienta | Qué hace | Enlace |
|---|---|---|
| **Passkeys** | El factor que no se puede dictar por teléfono ni reutilizar en un sitio falso | https://passkeys.directory |
| **NumenShield** | Capa de protección durante la navegación cotidiana | https://numenshield.com |
| **uBlock Origin** | Bloquea anuncios, y con ellos buena parte del malvertising | https://ublockorigin.com |
| **Quiz de phishing de Google** | Entrena el ojo con ocho ejemplos reales | https://phishingquiz.withgoogle.com |

---

## 🔗 La cadena completa: autopsia de un enlace en seis minutos

Cuando algo de verdad te preocupe, encadénalo así. **Sin abrir el enlace en ningún momento.**

| # | Paso | Herramienta |
|---|---|---|
| 1 | Expande el acortador y mira toda la cadena de saltos | [WhereGoes](https://wheregoes.com) |
| 2 | Aísla el dominio: lee de derecha a izquierda | A ojo |
| 3 | Consulta su reputación | [VirusTotal](https://www.virustotal.com/gui/home/url) |
| 4 | Mira la página sin visitarla | [urlscan.io](https://urlscan.io) |
| 5 | Comprueba la antigüedad del dominio | [ICANN Lookup](https://lookup.icann.org) |
| 6 | Mira su historia | [Wayback Machine](https://web.archive.org) |
| 7 | Busca una frase del mensaje entre comillas | Google |
| 8 | Comprueba el estado según el navegador | [Safe Browsing](https://transparencyreport.google.com/safe-browsing/search) |

> **Ninguna de estas herramientas da un veredicto.** Un sitio recién creado puede salir limpio en VirusTotal simplemente porque nadie lo ha reportado todavía. Lo que buscas no es una luz verde: son **contradicciones** entre lo que te cuentan y lo que encuentras.

Si al terminar sigues sin estar seguro, esa duda **ya es la respuesta**. Ninguna oportunidad legítima se pierde por verificarla.

> En urlscan, si la dirección contiene algo identificable, marca la visibilidad como **Unlisted**. Los escaneos públicos quedan visibles para cualquiera.

---

## Las seis acciones de esta semana

Si de todo este material solo vas a hacer seis cosas:

1. **Cierra todas las sesiones** de tu correo principal y de tu banco. No basta con cambiar la contraseña
2. **Revisa qué aplicaciones tienen acceso** a tu cuenta y revoca lo que no reconozcas
3. **Acuerda una palabra clave** con tu familia y con tu equipo — en persona, hoy, nunca por chat
4. **Guarda los marcadores** de los tres sitios donde mueves dinero, y entra solo por ahí
5. **Busca tu correo** en Have I Been Pwned y cambia lo que salga repetido
6. **Aprende a leer de derecha a izquierda.** Es gratis y sirve veinte veces al día

Todo esto está en el [checklist imprimible](CHECKLIST.md).

---

[← Anterior: El fraude que encuentras tú](11-el-fraude-que-encuentras.md) · [Volver al índice](index.md) · [Checklist →](CHECKLIST.md)

---

<p align="center">
  <img src="https://raw.githubusercontent.com/davidpereiracib/protege-tu-vida-digital/main/assets/img/secpro-color.png" alt="SecPro" width="150"><br>
  <sub><b>© 2026 David Pereira · SecPro — Security Professionals.</b><br>
  Material educativo de concienciación. Publicado bajo licencia
  <a href="https://creativecommons.org/licenses/by/4.0/deed.es">CC BY 4.0</a>:
  puedes compartirlo y adaptarlo citando la fuente.<br>
  <a href="https://secpro.co">secpro.co</a> · info@secpro.co</sub>
</p>
