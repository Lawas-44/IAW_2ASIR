# UD4.2 · Alpha (Google Workspace) · Consultoría Alpha ⇄ Beta

**Proyecto:** aplicación de pedidos online para el restaurante El Rincón.
**Rol:** Alpha (cliente, Google Workspace) · **Pareja Beta:** Microsoft 365.
**Alumnos Alpha:** [nombre 1], [nombre 2] · **Beta:** [nombre 1], [nombre 2]

```
UD4/UD4.2_Alpha-Beta/
├── README.md
├── img/        capturas
└── archivos/   Requisitos.docx · Acuerdo.docx · Respuestas_formulario.xlsx
```

> Convención: cada captura va precedida de su **contexto** y seguida de su **deducción**. Las líneas `📸 Pendiente` indican qué hay que capturar; se borran al subir la imagen real.

---

## A1 · Requisitos compartidos y comentario resuelto (2 pts)

**Contexto.** Creamos en Google Docs el documento "Requisitos del software" (archivo `archivos/Requisitos.docx`) con índice automático, 5 requisitos en lista, tabla de prioridades y una imagen de maqueta. Lo compartimos con la pareja Beta con el rol de **editor**, solo con sus cuentas. Después Beta escribió un comentario con @mención sobre uno de los requisitos.

![Documento Requisitos en Google Docs](img/a1_requisitos_docs.png)

> 📸 Pendiente: Google Docs con el documento abierto mostrando índice, lista, tabla e imagen.

**Deducción.** El índice se genera solo a partir de los estilos de título, así que si cambian los requisitos basta con actualizarlo; no hay que reescribirlo a mano. La tabla y la lista dejan claro qué es imprescindible y qué puede esperar.

![Diálogo Compartir con Beta como editor](img/a1_compartir_editor.png)

> 📸 Pendiente: botón Compartir con el correo de Beta, rol "Editor" y la casilla de notificar; sin "cualquiera con el enlace".

**Deducción.** Compartir por correo concreto, y no por enlace abierto, hace que solo entre quien debe y que quede registrado quién edita. El rol editor es necesario aquí porque Beta debe poder comentar y, si hiciera falta, corregir.

![Comentario de Beta con @mención](img/a1_comentario_beta.png)

> 📸 Pendiente: el comentario de Beta con @mención a Alpha, visible en el margen del documento (antes de contestar).

**Contexto.** Beta nos avisó con una @mención; recibimos un correo y el comentario apareció anclado al texto concreto. Respondimos explicando la corrección y lo marcamos como resuelto.

![Respuesta de Alpha y comentario resuelto](img/a1_comentario_resuelto.png)

> 📸 Pendiente: el hilo con la respuesta de Alpha y el estado "Resuelto" (o el historial de comentarios resueltos).

**Deducción.** Beta señaló que el requisito 4 (aviso a cocina en tiempo real) es el que más pesa en su estimación (56 h, 24,5 % del coste) y que nuestra propia tabla lo marcaba como prioridad Media. Respondimos confirmando que en la primera versión basta un correo al restaurante y que la pantalla en vivo pasa a una segunda fase; corregimos el requisito 4 y su justificación en `archivos/Requisitos.docx` y marcamos el comentario como resuelto. De ahí deducimos que el comentario con @mención no solo avisa: obliga a decidir y deja constancia, y la tabla de prioridades sirve de verdad para recortar alcance. Al resolverlo, el hilo se archiva pero se conserva en el historial.

---

## A2 · Evento completo y conexión con la hoja de Beta (2 pts)

**Contexto.** Organizamos la reunión inicial en Google Calendar para el viernes 20/11/2026 a las 10:00. Añadimos videollamada Meet, aviso 1 hora antes, ubicación, invitamos a Beta y pegamos en la descripción el enlace a su hoja "Costes y plazos".

![Evento de Calendar con Meet y aviso](img/a2_evento_calendar.png)

> 📸 Pendiente: edición del evento con título, fecha/hora, enlace de Meet, "Notificación 1 hora antes", ubicación e invitados Beta.

**Deducción.** Un solo evento reúne todo lo necesario (cuándo, dónde, enlace y documentos), así que nadie tiene que preguntar por el enlace de la llamada. El aviso de 1 hora evita olvidos, y el enlace a la hoja permite abrir los costes durante la reunión.

![Respuesta de Beta a la invitación / enlace en la descripción](img/a2_invitacion_enlace.png)

> 📸 Pendiente: el evento ya publicado mostrando a Beta como invitada (estado de respuesta) y el enlace a la hoja de costes en la descripción.

**Deducción.** Ver el estado de respuesta de los invitados nos dice si la reunión está confirmada. Enlazar la hoja en lugar de adjuntar una copia garantiza que todos vean la versión actual de los costes.

---

## A3 · Acta con la sugerencia aceptada o rechazada (2 pts)

**Contexto.** Redactamos el acta "Acuerdo de colaboración" (`archivos/Acuerdo.docx`) con 3 acuerdos numerados y la compartimos con Beta. Beta cambió uno de los acuerdos usando el **modo sugerencia** de Docs.

![Sugerencia de Beta en el acta](img/a3_sugerencia_beta.png)

> 📸 Pendiente: el acta con la sugerencia de Beta visible (texto tachado/nuevo en color) antes de decidir.

**Contexto (qué propuso Beta).** En el acuerdo 1, Beta cambió "30 días naturales" por "45 días naturales" y justificó el cambio con un comentario: el prototipo exige entrevistas (1 semana), prototipo de pantallas (1), modelo de datos (1) y API de pedidos (3), unas 6 semanas ≈ 42 días; en 30 días solo cabría sin la API.

**Deducción.** Con el modo sugerencia el texto original no se pierde: se ve a la vez el "30" tachado y el "45" propuesto, quién lo propone y por qué. Además la sugerencia estaba respaldada por datos de la hoja de costes de Beta (11 semanas en total), no por una impresión. Beta propone y Alpha decide.

![Decisión de Alpha sobre la sugerencia](img/a3_decision.png)

> 📸 Pendiente: la sugerencia aceptada o rechazada, con el comentario de Alpha que explica el motivo.

**Contexto (decisión).** Aceptamos la sugerencia y lo explicamos en un comentario: el cálculo de 6 semanas es razonable y, a cambio, la primera versión avisa a cocina por correo y la pantalla en vivo queda para la fase 2. En `archivos/Acuerdo.docx` el acuerdo 1 ya dice 45 días y se añadió un "Registro de cambios".

**Deducción.** Aceptar con comentario deja la razón escrita junto al cambio, de modo que ni Alpha ni Beta tendrán dudas dentro de un mes. La decisión es coherente con A1: al quitar el tiempo real recortamos alcance y a cambio concedemos plazo, que es una negociación equilibrada. Además el formulario de A5 confirma que Beta no veía realistas los 30 días.

---

## A4 · Nota de tareas compartida (1 pt)

**Contexto.** Tras la reunión creamos en Google Keep una nota "Tareas tras la reunión" con 3 casillas (revisar el acta, aceptar o rechazar sugerencias, responder al formulario) y la compartimos con Beta.

![Nota de Keep con 3 casillas](img/a4_keep_nota.png)

> 📸 Pendiente: la nota con las 3 casillas, alguna marcada, y el panel de colaboradores con el correo de Beta.

**Deducción.** La nota compartida funciona como lista de tareas común: lo que una pareja marca, la otra lo ve. Evita repetir mensajes tipo "¿ya lo hiciste?".

---

## A5 · Formulario y respuestas filtradas con gráfico (2 pts)

**Contexto.** Creamos un Google Forms de 4 preguntas ("Valoración de la colaboración Alpha–Beta"): una escala de 1 a 5, dos de opción múltiple y una de párrafo. Lo enviamos a Beta y cada miembro lo contestó.

![Editor del formulario con las 4 preguntas](img/a5_form_preguntas.png)

> 📸 Pendiente: el formulario en edición con las 4 preguntas y sus tipos.

**Deducción.** Se usaron preguntas cerradas (escala y opción múltiple) porque se pueden contar y graficar; la de párrafo da el matiz que una cifra no recoge.

![Respuestas en hoja de cálculo con filtro](img/a5_respuestas_filtro.png)

> 📸 Pendiente: la hoja `Respuestas_formulario.xlsx` con el filtro activo y una columna filtrada.

![Gráfico de las respuestas](img/a5_grafico.png)

> 📸 Pendiente: el gráfico de la pregunta de opción múltiple.

**Contexto.** Respondieron las dos personas de Beta (2 respuestas, sin inventar más). Pasamos las respuestas a una hoja (`archivos/Respuestas_formulario.xlsx`), aplicamos un autofiltro y filtramos la pregunta 3 por "No" para ver quién considera irreal el plazo y qué propone. En la hoja Resumen contamos las opciones con `CONTAR.SI` y las graficamos.

**Deducción.** La claridad de los requisitos sale bien (media 4,5 sobre 5). En la P2 no hay consenso: Beta 1 señala "Confirmación y aviso a cocina" y Beta 2 "Panel de gestión", cada una con una opción, así que con tan pocas respuestas no hay una opción dominante, pero ambas confirman que la parte de cocina y gestión es la más costosa. En la P3, ninguna respondió "Sí": una dijo "Con ajustes" y otra "No". Con solo dos respuestas no podemos generalizar, pero el dato apoya la decisión de A3 (ampliar a 45 días). Los comentarios abiertos piden definir qué significa cada prioridad y fijar un día de revisión de comentarios, acciones que adoptaremos.

---

## A6 · Prueba de permisos (1 pt)

**Contexto.** Para comprobar el control de acceso abrimos nuestro documento en una ventana de incógnito (sin sesión de Google), primero con el uso compartido **restringido** y luego con "cualquiera con el enlace".

![Incógnito con acceso restringido](img/a6_incognito_restringido.png)

> 📸 Pendiente: ventana de incógnito abriendo el enlace con el documento restringido (pantalla "Necesitas permiso" o similar).

**Deducción.** Sin iniciar sesión con una cuenta autorizada no se ve nada: la restricción funciona por identidad, no por conocer la URL.

![Cambio a cualquiera con el enlace](img/a6_cualquiera_enlace.png)

> 📸 Pendiente: diálogo Compartir con "Cualquiera con el enlace" y su rol (lector).

![Incógnito con enlace público](img/a6_incognito_publico.png)

> 📸 Pendiente: la misma ventana de incógnito ya mostrando el documento.

**Deducción.** Con la opción abierta, cualquiera con la URL entra sin identificarse. Después volvimos a **Restringido** (captura final para dejar constancia).

![Vuelta a restringido](img/a6_restringido_final.png)

> 📸 Pendiente: diálogo Compartir de nuevo en "Restringido".

---

## Autoevaluación

**¿Qué diferencia hay entre rol comentarista y modo sugerencia?**
El **rol** es un permiso sobre el archivo: el comentarista puede leerlo y comentar, pero no cambiar el contenido. El **modo sugerencia** es una forma de editar (la tiene quien es editor): los cambios no sustituyen el texto, quedan propuestos y el autor los acepta o rechaza. En resumen, el rol limita lo que puedes hacer; la sugerencia es una manera de proponer cambios.

**¿Qué riesgo tiene "cualquiera con el enlace"?**
Que el acceso deja de depender de la identidad: quien tenga la URL entra, aunque no sea a quien se lo diste. El enlace se puede reenviar, quedar en un correo reenviado o en un historial, o indexarse si se publica, y no sabemos quién ha accedido. Si el rol es editor, además cualquiera podría modificar o borrar el contenido. Para información del cliente conviene dejarlo restringido y compartir por correo.

**¿Qué haría falta para no depender de Google ni de Microsoft?**
Alojar nosotros la suite: un servidor propio (o contratado) con una plataforma como **Nextcloud** como almacenamiento y compartición, junto con **ONLYOFFICE** o **Collabora Online** para editar documentos, hojas y presentaciones en el navegador. Haría falta un servidor, dominio y certificado HTTPS, usuarios y permisos, copias de seguridad y actualizaciones, y alguien que lo mantenga. Se gana control y privacidad de los datos y se evita el bloqueo del proveedor, a cambio de asumir el trabajo y el coste de administración.

---

## Pasos que debe hacer el alumno en Google Workspace

Marca cada paso y sube la captura indicada a `img/`.

### Fase 1
- [ ] Subir `archivos/Requisitos.docx` a Drive y abrirlo con Google Docs (Archivo → Guardar como Documentos de Google). Comprobar índice, lista, tabla e imagen. 📸 `a1_requisitos_docs.png`
- [ ] Compartirlo con Beta como **Editor** (solo con sus correos). 📸 `a1_compartir_editor.png`
- [ ] Esperar el comentario de Beta con @mención. 📸 `a1_comentario_beta.png`
- [ ] Responder el comentario, corregir lo pedido y pulsar **Resolver**. 📸 `a1_comentario_resuelto.png`

### Fase 2
- [ ] Crear el evento en Calendar con los datos de `alpha_ronda1.md` (Meet, aviso 1 h antes, ubicación, invitar a Beta, enlace a su hoja). 📸 `a2_evento_calendar.png`, `a2_invitacion_enlace.png`
- [ ] Subir `archivos/Acuerdo.docx` a Drive, abrirlo con Docs y compartirlo con Beta como editor. Esperar su sugerencia. 📸 `a3_sugerencia_beta.png`
- [ ] Aceptar o rechazar la sugerencia y añadir un comentario con el motivo. 📸 `a3_decision.png`
- [ ] Crear la nota de Keep con 3 casillas y compartirla con Beta. 📸 `a4_keep_nota.png`

### Fase 3
- [ ] Crear el Google Forms con las 4 preguntas de `alpha_ronda1.md` y enviarlo a Beta. 📸 `a5_form_preguntas.png`
- [ ] Cuando respondan, vincular a hoja de cálculo, aplicar filtro y crear gráfico. 📸 `a5_respuestas_filtro.png`, `a5_grafico.png`
- [ ] Si Beta no responde, documentar el intento (invitación enviada, formulario sin respuestas): no se penaliza.

### Cierre
- [ ] Abrir el documento en ventana de incógnito con acceso restringido. 📸 `a6_incognito_restringido.png`
- [ ] Cambiar a "cualquiera con el enlace" (lector) y repetir. 📸 `a6_cualquiera_enlace.png`, `a6_incognito_publico.png`
- [ ] Volver a **Restringido**. 📸 `a6_restringido_final.png`
- [ ] Rellenar nombres en este README, borrar las líneas "📸 Pendiente" y completar las deducciones marcadas.
- [ ] Subir a Git:
  ```
  git add UD4/UD4.2_Alpha-Beta
  git commit -m "UD4.2: evidencias Alpha"
  git push
  ```
