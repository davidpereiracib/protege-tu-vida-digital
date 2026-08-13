# 05 · Tu IA forma parte de tu vida digital

> *Antes de subir algo, pregúntate: ¿compartiría esta misma información con una persona que no conozco?*

Para que una IA nos ayude mejor, le damos más contexto. Y ese contexto es exactamente lo que constituye nuestra vida digital.

---

## ¿Qué le estás contando a tu IA?

| Tipo | Ejemplos |
|---|---|
| 💬 **Conversaciones** | Problemas, decisiones, ideas, situaciones personales |
| 📄 **Documentos** | PDF, contratos, informes, hojas de vida |
| 🖼️ **Imágenes** | Fotografías, capturas de pantalla, documentos escaneados |
| 💼 **Información laboral** | Proyectos, clientes, reuniones, información interna |
| 👤 **Datos personales** | Nombres, correos, teléfonos — **incluidos los de terceros** |

Ese último punto merece atención especial: cuando subes un documento con datos de otras personas, estás decidiendo por ellas.

### Qué revisar en cada plataforma

Todas las plataformas principales permiten controlar el historial, la memoria persistente y si tus conversaciones se usan para entrenar modelos. Búscalo en:

- **Configuración → Privacidad / Controles de datos**
- **Historial y memoria** — puedes desactivarlo o borrarlo
- **Uso para entrenamiento** — suele ser una casilla independiente

En contextos profesionales, los planes empresariales normalmente excluyen el entrenamiento por defecto. Verifícalo antes de asumirlo.

---

## Cuando la IA deja de responder y empieza a actuar

Antes le pedíamos: *"dime cuáles son los vuelos más baratos a Bogotá"*.

Ahora podemos pedirle: *"busca el mejor vuelo, resérvalo y agrégalo a mi calendario"*.

**Qué cambió:** la IA ya no solo genera una respuesta. Puede leer y gestionar correos, consultar calendarios, acceder a archivos, navegar por Internet, interactuar con servicios y **ejecutar acciones**.

Para hacerlo necesita algo muy importante: **permisos**.

```
IA + tus cuentas + permisos = capacidad de actuar en tu nombre
```

---

## No todos los permisos tienen el mismo riesgo

| Nivel | Qué implica | Ejemplo |
|---|---|---|
| 👀 **Leer** | Consultar información | Ver un calendario, buscar un archivo |
| ✏️ **Modificar** | Cambiar información existente | Editar un documento, mover una cita |
| 📤 **Compartir** | Enviar datos a terceros | Mandar un correo o un archivo |
| 💳 **Ejecutar** | Acciones con consecuencias reales | Una compra, una reserva, una transferencia |

La distancia entre *leer* y *ejecutar* es enorme. Trátalos distinto.

---

## Aplica el mínimo privilegio

Dale a la IA **solo los accesos que necesita** para la tarea concreta.

- ✅ Revisa las cuentas conectadas
- ✅ Elimina integraciones que ya no utilizas
- ✅ Limita el acceso a información sensible
- ✅ Exige confirmación antes de acciones importantes

| Dónde revisar los accesos concedidos | Enlace |
|---|---|
| **Google** | https://myaccount.google.com/connections |
| **Microsoft** | https://account.microsoft.com/privacy |
| **Apple** | https://appleid.apple.com |

---

## Navegadores con IA: un riesgo nuevo

Los navegadores que incorporan agentes pueden actuar por ti **usando tus sesiones ya iniciadas**. Eso los hace muy útiles y, a la vez, vulnerables a un ataque llamado **inyección de prompt indirecta**.

**Cómo funciona:** una página web contiene instrucciones ocultas —texto blanco sobre fondo blanco, o dentro de comentarios del código— que el agente lee y obedece como si vinieran de ti.

**Por qué es difícil de resolver:** el modelo no distingue entre *el contenido que lee* y *las órdenes que recibe*. Para él, todo es texto.

| Recurso | Enlace |
|---|---|
| **OWASP Top 10 para aplicaciones con LLM** (LLM01: Prompt Injection) | https://genai.owasp.org |

### La regla práctica

> **A un agente de IA nunca se le debe dar, al mismo tiempo:**
> **(a)** acceso a datos privados
> **(b)** exposición a contenido no confiable
> **(c)** capacidad de comunicarse hacia afuera
>
> **Dos de tres está bien. Los tres juntos es una fuga esperando ocurrir.**

**Recomendación concreta:** usa los navegadores con IA en un **perfil separado**, sin la sesión del banco ni del correo de trabajo.

---

## En contextos profesionales

Si trabajas con información de terceros —pacientes, clientes, empleados— hay una línea que no conviene cruzar:

> **Nunca introduzcas datos identificables de terceros en herramientas de IA públicas.**

En Colombia, la **Ley 1581 de 2012** clasifica los datos de salud y los datos biométricos como **sensibles**, y su tratamiento exige autorización explícita del titular. Subir un documento con esa información a un servicio público es un tratamiento de datos que probablemente no está autorizado.

Cuando necesites usar IA con información sensible, usa las herramientas aprobadas por tu organización, que están cubiertas por acuerdos de tratamiento de datos.

---

[← Anterior: Privacidad y rastreo](04-privacidad-y-rastreo.md) · [Volver al índice](README.md) · [Siguiente: Respaldo y continuidad →](06-respaldo-y-continuidad.md)
