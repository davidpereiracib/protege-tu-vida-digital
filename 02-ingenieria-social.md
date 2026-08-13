# 02 · Ingeniería social potenciada por IA

> *El mensaje peligroso no siempre parece sospechoso. Puede parecer escrito especialmente para ti.*

El clásico *"Estimado usuario, su cuenta será bloqueada"* es cada vez menos necesario. Hoy un engaño puede incluir tu nombre y cargo, dónde trabajas, quiénes son tus familiares, dónde estuviste recientemente y qué te interesa. La IA convierte ese contexto en mensajes naturales y convincentes en segundos.

---

## Cuatro canales, una misma estrategia

| Modalidad | Llega por | Pretextos habituales |
|---|---|---|
| 🎣 **Phishing** | Correo electrónico | Enlaces, archivos, cambios de contraseña |
| 📱 **Smishing** | SMS o mensajería | Entregas, bancos, multas, pagos urgentes |
| 📞 **Vishing** | Llamadas o notas de voz | Soporte técnico, bancos, familiares, autoridades |
| ▦ **Quishing** | Códigos QR | Menús, pagos, parqueaderos, promociones |

**La fórmula es siempre la misma:**

```
Confianza + emoción + urgencia → acción
```

Si algo te apura, **ese apuro es la señal**.

---

## Entrenar el ojo

| Herramienta | Qué hace | Enlace |
|---|---|---|
| **Google Phishing Quiz** | Ocho ejemplos reales para practicar | https://phishingquiz.withgoogle.com |

---

## Analizar un enlace sospechoso sin abrirlo

| Herramienta | Qué te muestra | Enlace |
|---|---|---|
| **urlscan.io** | Captura de pantalla del sitio, IP, país, dominios que contacta | https://urlscan.io |
| **VirusTotal** | Cuántos motores de seguridad lo marcan | https://www.virustotal.com/gui/home/url |
| **Google Safe Browsing** | Estado del sitio según Google | https://transparencyreport.google.com/safe-browsing/search |

> En urlscan, si la dirección contiene algo identificable, marca la visibilidad como **Unlisted**. Los escaneos públicos quedan visibles para cualquiera.

### Leer un dominio correctamente

Esta técnica sola evita la mayoría de los engaños:

```
https://bancolombia.seguridad-cliente[.]co/login
                    └──────────┬─────────┘
                    el dueño real del dominio
```

**Lee de derecha a izquierda desde la primera barra.** Lo último antes del primer `/` es el dominio real. Aquí el dueño es `seguridad-cliente[.]co`, no el banco.

*(Los corchetes son la convención de "defanging": impiden que un enlace malicioso sea clicable por accidente. Úsala cuando compartas ejemplos.)*

---

## Tu voz también es una credencial

Durante años, escuchar a alguien bastaba para pensar *"sí, es él, reconozco su voz"*. Hoy una voz puede clonarse a partir de muestras breves de audio, reproduciendo tono, forma de hablar, acento, ritmo y entonación.

**¿De dónde sale tu voz?** Videos, redes sociales, notas de voz, entrevistas, podcasts, cualquier contenido público.

### 🔑 La palabra secreta familiar

**Es la mejor defensa que existe contra la voz clonada, y es gratis.** La IA puede imitar una voz y recrear un rostro, pero no puede conocer un secreto que nunca publicaste.

Características de una buena palabra clave:

- **Privada** — solo conocida por las personas de confianza
- **Fácil de recordar, difícil de deducir**
- **No relacionada contigo** — nada de mascotas, cumpleaños, colegios ni información que esté en redes

**¿Cuándo usarla?** Ante cualquier solicitud inesperada relacionada con:
- 💰 Dinero
- 🚨 Emergencias
- 📄 Información sensible
- 🔑 Accesos o códigos

**Defínela hoy con tu familia.** Toma dos minutos y es lo único de esta lista que no requiere instalar nada.

---

## Ver ya no es creer: deepfakes en videollamada

La IA permite manipular o generar en tiempo real el rostro, la voz, los gestos y la conversación completa. El riesgo aumenta cuando la solicitud es sensible:

> *"Envíame este documento." · "Compárteme el código." · "Necesito acceso ahora."*

### Herramientas de detección

| Herramienta | Analiza | Enfoque | Enlace |
|---|---|---|---|
| **Deepware Scanner** | 🎥 Video | Manipulación facial | https://scanner.deepware.ai/ |
| **DeepFake-O-Meter** | 📷 Imagen · 🎥 Video · 🎙 Audio | Plataforma académica que compara varios algoritmos | https://zinc.cse.buffalo.edu/ubmdfl/deep-o-meter/ |
| **Resemble Detect** | 🎙 Audio · 📷 Imagen · 🎥 Video | Especialmente fuerte en clonación de voz | https://www.resemble.ai/detect/ |
| **Reality Defender** | 🎙 Audio · 📷 Imagen · 🎥 Video | Solución profesional; no pensada para consumidor | https://www.realitydefender.com/ |

> ⚠️ **Ningún detector es infiable.** Todos producen falsos positivos y falsos negativos. Úsalos como una señal más, nunca como veredicto.

### Verificación en directo, sin herramientas

Si estás en una videollamada y algo no cuadra:

- Pide que **gire la cabeza 90 grados**
- Pide que **se pase la mano por delante de la cara**

Los modelos de sustitución facial todavía se rompen de perfil y con oclusiones.

**Y a nivel organizacional:** ninguna transferencia ni entrega de credenciales se aprueba por videollamada. **Doble canal, siempre.**

---

## Probar la autenticidad del contenido

El futuro no es detectar lo falso, es **poder probar lo auténtico**.

| Herramienta | Qué hace | Enlace |
|---|---|---|
| **Content Credentials** | Lee la procedencia criptográfica de una imagen | https://contentcredentials.org/verify |
| **C2PA** | El estándar detrás (Adobe, Google, OpenAI, Microsoft, Sony, Leica, BBC) | https://c2pa.org |
| **SynthID** | Marca de agua invisible de Google que sobrevive a recortes y compresión | https://deepmind.google/technologies/synthid/ |

> **El matiz que importa:** que una imagen **no** tenga credenciales no significa que sea falsa. Significa que no sabemos. Y basta con abrir y volver a guardar un archivo para borrar esos metadatos.

---

## La regla que resume todo

Cuando una solicitud sea inusual o sensible, **confirma la identidad por un segundo canal que tú ya conozcas**. No por el que te contactaron.

Cuelga y devuelve la llamada al número que tú tienes guardado. Nunca al número entrante.

---

[← Anterior: Cuentas e identidad](01-cuentas-e-identidad.md) · [Volver al índice](README.md) · [Siguiente: Tu teléfono →](03-tu-telefono.md)
