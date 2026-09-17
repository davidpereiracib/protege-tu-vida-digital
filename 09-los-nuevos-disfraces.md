# 09 · Los nuevos disfraces del fraude

> *Que una pieza sea legítima no significa que toda la historia que la rodea también lo sea.*

Las técnicas de este capítulo tienen algo en común: **no se apoyan en que parezcas descuidado, sino en que actúes normal**. Escanear un QR es normal. Resolver un CAPTCHA es normal. Abrir un documento compartido es normal.

---

## ▦ Quishing: el enlace que no puedes leer

El código QR elimina justo lo que sí podíamos inspeccionar: **el enlace visible**. Escaneamos primero y pensamos después.

- Llega por correo o documento, pero también **impreso en el mundo físico**
- Un adhesivo puede pegarse **encima de un QR legítimo** — nadie audita las calcomanías de un parqueadero
- La cámara **te muestra la dirección antes de abrirla**: ese segundo es toda tu defensa
- El dominio importa más que el diseño de la página que aparece después

> **Un QR no es más seguro que un enlace. Simplemente esconde mejor su destino.**

### Leer un QR sin abrirlo

| Herramienta | Qué hace | Enlace |
|---|---|---|
| **ZXing Decoder** | Subes la imagen y te devuelve la dirección en texto | https://zxing.org/w/decode.jspx |
| **CyberChef** (*Parse QR Code*) | Alternativa si ZXing no responde | https://gchq.github.io/CyberChef/ |

Con la dirección en la mano, pásala por [urlscan.io](https://urlscan.io) o [VirusTotal](https://www.virustotal.com/gui/home/url) antes de visitarla. Ver el [método completo de verificación](12-verificar-antes-de-confiar.md).

**Dónde desconfiar especialmente:** QR pegados a mano, QR que piden un pago inmediato, QR en correos que dicen ser de tu banco, y QR que llevan a un formulario de inicio de sesión.

---

## 🩹 ClickFix: te convencen de ejecutar el ataque tú mismo

Esta es la técnica que más creció y la que menos gente conoce. **Invierte la lógica completa del ataque.**

El atacante no explota una falla de tu equipo. Explota **tu intención de resolver un problema**.

**Cómo se ve:**

1. Aparece un error, un CAPTCHA o una "verificación humana" de aspecto normal
2. La página dice que la verificación automática falló y ofrece una **verificación manual**
3. Te indica una secuencia: copiar un código, abrir una ventana, pegar, presionar Enter
4. Tú copias, pegas y ejecutas. **El ataque ya ocurrió.**

**El detalle sucio:** lo que la página muestra en pantalla no es lo que queda en el portapapeles. El comando real se esconde detrás de decenas de espacios en blanco, de modo que en el cuadro de ejecución solo alcanzas a ver un texto inocente al final.

### Por qué esto pasa por encima de casi todas las defensas

- No hay archivo adjunto que escanear, ni macro, ni descarga automática
- El comando lo ejecutas **tú**, con **tus** permisos, desde una acción que **tú** iniciaste
- El antivirus ve a una persona escribiendo en su propia terminal, que es lo que hace todos los días

Microsoft ha reportado campañas de este tipo contra miles de dispositivos diarios. Está catalogada en MITRE ATT&CK como [T1204.004 — Malicious Copy and Paste](https://attack.mitre.org/techniques/T1204/004/).

> ## 🛑 La regla, y no tiene excepciones
>
> **Ninguna verificación humana legítima te pide abrir una terminal, pegar un comando ni presionar `Windows + R`.**
>
> Ninguna. Nunca. Si una página te lo pide, ciérrala.

Si ya lo hiciste: desconecta el equipo de la red, no apagues nada, y avisa al área de tecnología. Ver [Si ya te pasó](07-si-ya-te-paso.md).

---

## 🪞 Sitios clonados: copiar la apariencia es trivial

Comparar colores, logos y tipografías dejó de servir para decidir si estás en el sitio correcto.

- El sitio puede ser **idéntico** al original — a menudo es una copia literal del código
- **HTTPS protege la conexión, no certifica el negocio.** El candado significa que nadie va a espiar lo que le escribes al estafador
- Un dominio parecido puede incluir el nombre de la marca **sin pertenecerle**
- La dirección y **cómo llegaste hasta ahí** son señales mucho más útiles que el aspecto

### Los dos trucos que más funcionan

**1. El subdominio disfrazado.** El nombre de la marca puesto a la izquierda, donde no manda:

```
https://portal.bancolombia.com.seguridad-clientes[.]co/ingreso
                                └────────┬────────┘
                                 el dueño real
```

**2. Las letras que se parecen.** Y aquí hay dos casos muy distintos, que conviene no mezclar.

### Caso A — Letras de nuestro propio alfabeto *(el peligroso)*

No hace falta ningún truco exótico. Solo letras normales, puestas de forma que el ojo las una:

```
arnazon.com        ← r + n, a tamaño pequeño se lee como una "m"
rnicrosoft.com     ← lo mismo, al principio de la palabra
bancolornbia.com   ← r + n en mitad de la palabra
paypaI.com         ← "I" mayúscula haciéndose pasar por "l" minúscula
```

**Ningún navegador te avisa de esto**, porque no hay nada anómalo que detectar: son caracteres corrientes. La última es la peor: en muchas tipografías la **I** mayúscula y la **l** minúscula son exactamente el mismo dibujo.

> Estas direcciones son indistinguibles en la pantalla de un teléfono. En un monitor grande son obvias. El fraude cuenta con que las leas en el teléfono, con prisa.

### Caso B — Letras de otro alfabeto *(donde el navegador sí te defiende)*

Existen letras de otros alfabetos idénticas a las nuestras. La «а» cirílica y la «a» nuestra se dibujan igual pero son caracteres distintos, así que `аpple.com` y `apple.com` son **dos dominios diferentes**.

Como los dominios solo admiten caracteres ASCII, esos nombres se registran en una codificación llamada **punycode**, que empieza siempre por `xn--`:

| Lo que el atacante registra | Lo que significa |
|---|---|
| `xn--pple-43d.com` | `аpple.com` (la «a» es cirílica) |
| `xn--gogle-jye.com` | `gоogle.com` (la «o» es cirílica) |
| `xn--banclombia-hvi.com` | `bancоlombia.com` (la «o» es cirílica) |

**La buena noticia:** Chrome, Safari y Firefox ya detectan esta mezcla de alfabetos y, cuando la ven, **dejan de mostrar la palabra bonita** y enseñan el `xn--` tal cual en la barra de direcciones.

> ## 🚩 La regla práctica
>
> Si alguna vez ves una dirección que empieza por **`xn--`**, eso **no es un error de la página**.
>
> Es tu navegador avisándote de que ese dominio venía disfrazado. Cierra.

| Herramienta | Qué hace | Enlace |
|---|---|---|
| **Punycoder** | Traduce entre el `xn--` y el nombre que esconde | https://www.punycoder.com |
| **dnstwist** | Genera las variantes de un dominio y te dice **cuáles están registradas** | https://dnstwist.it |
| **ICANN Lookup** | Cuándo se registró el dominio | https://lookup.icann.org |
| **crt.sh** | Certificados emitidos para un dominio | https://crt.sh |

> La antigüedad es la contradicción más fácil de encontrar: un banco "de cincuenta años" con un dominio de tres semanas no necesita más análisis.

La técnica para leer un dominio correctamente está en [Ingeniería social](02-ingenieria-social.md#leer-un-dominio-correctamente). Si solo aprendes una cosa de todo este repositorio, que sea esa.

---

## 🎭 Cuando la confianza es el señuelo

Los atacantes también se apoyan en elementos que asociamos con **seguridad** o con **productividad**. Precisamente porque nos resultan familiares, bajamos la guardia.

| El señuelo | Por qué funciona |
|---|---|
| CAPTCHA y verificaciones humanas | Los asociamos con protección, no con ataque |
| Documentos compartidos desde servicios conocidos | SharePoint, Drive y Dropbox son legítimos… y cualquiera puede subir un archivo |
| Formularios, calendarios y almacenamiento en la nube | Infraestructura real, contenido de quien sea |
| Solicitudes de permisos que parecen parte del flujo | Ver [Cuando el MFA no basta](10-cuando-el-mfa-no-basta.md) |

**La distinción que hay que hacer:** la plataforma es legítima, el archivo no necesariamente, y quien lo compartió mucho menos. Son tres cosas separadas y solemos evaluarlas como una sola.

---

## 🔀 Cadenas: cuando el fraude salta de canal

Los fraudes más convincentes no se quedan en un solo sitio. **Cada salto añade una capa de credibilidad.**

```
Un anuncio  →  una web  →  WhatsApp  →  una llamada  →  un documento  →  un pago
```

Un "asesor" te escribe y ya conoce tu contexto. Después llega un comprobante. Después una videollamada con rostro y voz.

> **Más canales no son más pruebas si todos salen de la misma historia.**

Analizar cada pieza por separado esconde el fraude. **Reconstruir la cadena completa** casi siempre revela la contradicción: un asesor de un banco que te escribe desde un celular, una empresa cuyo dominio no coincide con su correo, una oferta que aparece en tres sitios y en ninguno oficial.

**Cada cambio de canal es también tu oportunidad.** Es el momento de salir de la historia y verificar por un canal que el atacante no controle.

---

## Lo que tienes que recordar de este capítulo

1. El QR es un enlace con la parte revisable borrada. **Mira la dirección antes de abrir.**
2. Si una verificación te pide ejecutar un comando, **es el ataque**.
3. El candado no dice de quién es el sitio. **El dominio, sí.**
4. Plataforma legítima ≠ archivo legítimo ≠ persona legítima.
5. Cuando la conversación salta de canal, **esa es tu señal para verificar aparte**.

---

[← Anterior: Anatomía del fraude](08-anatomia-del-fraude.md) · [Volver al índice](index.md) · [Siguiente: Cuando el MFA no basta →](10-cuando-el-mfa-no-basta.md)

---

<p align="center">
  <img src="https://raw.githubusercontent.com/davidpereiracib/protege-tu-vida-digital/main/assets/img/secpro-color.png" alt="SecPro" width="150"><br>
  <sub><b>© 2026 David Pereira · SecPro — Security Professionals.</b><br>
  Material educativo de concienciación. Publicado bajo licencia
  <a href="https://creativecommons.org/licenses/by/4.0/deed.es">CC BY 4.0</a>:
  puedes compartirlo y adaptarlo citando la fuente.<br>
  <a href="https://secpro.co">secpro.co</a> · info@secpro.co</sub>
</p>
