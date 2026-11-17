# UD4.2 · Trabajo cooperativo con suites SaaS · Pareja BETA (Microsoft 365)

**Equipo:** Beta = Luis (Microsoft 365) · Alpha = Tensae (Google Workspace), que hace de cliente · **Encargo:** aplicación de pedidos para un restaurante · **Suite de Beta:** Microsoft 365 (Excel Online / Excel de escritorio)

> Estado: BORRADOR. Los apartados con `📸 Pendiente` se completan con las capturas reales del alumno.

## Estructura de la entrega

```
UD4/UD4.2_Alpha-Beta/
├── README.md
├── img/
└── archivos/Costes_y_plazos.xlsx   ← archivo real, no una captura
```

Vista previa (generada fuera de Excel, solo orientativa; las evidencias son las capturas del alumno):

![Vista previa de la hoja Costes](img/vista_previa_hoja_costes.png)

---

## B1 · Hoja con datos propios y cálculos correctos (3 pt)

**Contexto.** Alpha nos encarga presupuestar una aplicación de pedidos para un restaurante. Hemos descompuesto el trabajo en 8 tareas con datos propios (distintas del ejemplo del enunciado): perfiles de analista funcional, backend, frontend, diseñador UI, QA y DevOps, con tarifas de 32 a 50 €/h. La hoja **Tarifas** guarda los precios y la hoja **Costes** calcula todo lo demás con fórmulas.

![Hoja Tarifas](img/b1_tarifas.png)

> 📸 Pendiente: hoja **Tarifas** completa (6 perfiles con su precio/hora), con la pestaña visible.

![Hoja Costes con fórmulas](img/b1_costes.png)

> 📸 Pendiente: hoja **Costes** con las 8 tareas y la fila TOTAL a la vista, mostrando los valores calculados.

![Barra de fórmulas D y G](img/b1_formulas.png)

> 📸 Pendiente: dos capturas (o un montaje) con la barra de fórmulas: celda **D2** (`=BUSCARV(B2;Tarifas!$A$2:$B$7;2;FALSO)`) y celda **G2** (`=E2/$E$10`).

**Deducción.**
- La columna D no se escribe: `BUSCARV` busca el perfil de la columna B en Tarifas. Si mañana sube el precio del backend, se cambia **una sola celda** en Tarifas y se recalculan todas las tareas de ese perfil.
- El rango `Tarifas!$A$2:$B$7` es absoluto para que no se desplace al copiar la fórmula hacia abajo; igual `$E$10` en la columna G: cada porcentaje se divide siempre entre el total, no entre la fila de al lado (sin el `$` saldría un `#¡DIV/0!` o porcentajes sin sentido al copiar).
- Resultados de la versión final (tras el ajuste pactado con Alpha, ver B5): **204 horas, 7.924 € y 10 semanas**; la columna G suma **100 %**, lo que confirma que las referencias están bien. Comprobación manual: 768 + 924 + 684 + 1.368 + 1.584 + 1.064 + 832 + 700 = 7.924 €. (La primera versión de la hoja, con la API en tiempo real, era de 224 h, 8.684 € y 11 semanas.)
- La columna H marca "Revisar" solo en la **pantalla de pedido para camareros (44 h)**, porque supera 40 horas: es la que hay que justificar al cliente. La API de pedidos (36 h) estaba en "Revisar" con 56 h y pasó a "OK" al reducir su alcance: el aviso reacciona solo al cambiar las horas.

---

## B2 · Lista desplegable de perfiles (1,5 pt)

**Contexto.** Si cada persona escribe el perfil a mano ("Backend", "backend ", "Programador"...), `BUSCARV` falla y el precio desaparece. Para evitarlo hemos aplicado a B2:B9 una **validación de datos** de tipo Lista cuyo origen es `=Tarifas!$A$2:$A$7`.

![Lista desplegable](img/b2_desplegable.png)

> 📸 Pendiente: celda de la columna B con el desplegable abierto mostrando los 6 perfiles.

![Cuadro de validación de datos](img/b2_validacion.png)

> 📸 Pendiente: cuadro **Datos → Validación de datos** con Permitir: Lista y Origen `=Tarifas!$A$2:$A$7`.

![Error al escribir un perfil inexistente](img/b2_error.png)

> 📸 Pendiente: intento de escribir un perfil que no existe (p. ej. "Becario") y el mensaje de error "Perfil no válido".

**Deducción.** La lista no está escrita a mano en la validación: apunta a Tarifas. Así hay **una única fuente de verdad**: si se añade un perfil nuevo en Tarifas (y se amplía el rango), aparece en el desplegable. Además Excel rechaza valores fuera de la lista, de modo que la columna D nunca devuelve `#N/D` por una errata. Es control de calidad del dato en origen, no corrección posterior.

---

## B3 · Hoja protegida salvo A, B, C y F (1,5 pt)

**Contexto.** La hoja la usará también el cliente (Alpha) para ajustar horas, y no queremos que rompa las fórmulas. Hemos desbloqueado solo A, B, C y F de las filas de datos (Formato de celdas → Protección → desmarcar *Bloqueada*) y luego **Revisar → Proteger hoja** (contraseña: `asir`, documentada solo para esta práctica).

![Celdas desbloqueadas](img/b3_desbloqueo.png)

> 📸 Pendiente: **Formato de celdas → Protección** con *Bloqueada* desmarcado en un rango A2:C9 / F2:F9 (basta una celda de muestra).

![Intento de modificar una fórmula](img/b3_bloqueada.png)

> 📸 Pendiente: intentar escribir en **E5** (o D5, G5, H5) con la hoja protegida y el aviso de Excel "la celda está protegida".

![Modificar horas y recálculo](img/b3_horas.png)

> 📸 Pendiente: cambiar las **horas de C5** (p. ej. de 36 a 42 en la API de pedidos: pasará a "Revisar") y mostrar cómo se recalculan E5, G, H y el TOTAL.

**Deducción.** Excel no deja tocar la columna E (ni D, G, H ni el total), pero sí las horas, y el coste se recalcula solo: el cliente puede ajustar los datos de entrada sin poder estropear las fórmulas. El bloqueo de celdas no hace nada hasta que se activa la protección de hoja: son dos pasos. La contraseña sencilla impide el descuido, no un ataque: es un control de integridad, no de confidencialidad.

---

## B4 · Gráfico y su lectura (1,5 pt)

**Contexto.** Para ver de un vistazo dónde se va el dinero hemos insertado un **gráfico circular** con el coste (columna E) por tarea (columna A), con porcentajes como etiquetas.

![Gráfico circular de costes](img/b4_grafico.png)

> 📸 Pendiente: gráfico circular completo, con título "Coste por tarea", leyenda y etiquetas de porcentaje, junto a la tabla.

**Lectura del gráfico.**
- La porción mayor es la **pantalla de pedido para camareros: 1.584 € (20,0 %)**, 2 de las 10 semanas y la única tarea con aviso "Revisar" (44 h). Le sigue la **API de pedidos y aviso por correo a cocina: 1.368 € (17,3 %)**, 2 semanas.
- Juntas suman **2.952 € (37,3 %)** de 7.924 €: más de un tercio del coste está en dos tareas. Y el backend completo (modelo de datos, API y TPV: 82 h, 3.116 €) pesa el 39,3 %.
- Antes de ajustar el alcance, la API en tiempo real era la mayor (2.128 €, 24,5 %). Al pasar el aviso a cocina a un simple correo (−20 h, −760 €) el gráfico cambia: la sección que más disminuye es precisamente la que se aplazó a la fase 2.
- Las tareas de análisis, datos, pruebas y despliegue pesan entre 8 y 12 % cada una; no son el riesgo.
- **Implicación:** el presupuesto es sensible a cualquier cambio de alcance en la pantalla del camarero y la API. Si Alpha recupera la pantalla de cocina en vivo (fase 2) o añade pedidos desde el móvil del cliente, ahí se disparan coste y plazo. Conviene fijar el alcance exacto de esas dos tareas y trabajar por fases (primero un mínimo viable) antes de comprometer las 10 semanas.
- El gráfico se actualiza con la tabla: si cambiamos horas, cambia el reparto.

---

## B5 · Comentario con mención y sugerencia en el acta (1,5 pt)

**Contexto (comentario).** Alpha, como cliente del restaurante "El Rincón", nos comparte `Requisitos.docx` en Google Docs. Hacemos de consultores: leemos los 5 requisitos junto a nuestra hoja de costes y comprobamos que el **R4 (confirmación y aviso a cocina, "mostrar el pedido al instante en la pantalla de cocina")** coincide con nuestra tarea más cara en ese momento (hoja v1): la API de pedidos y comandas (56 h, 2.128 €, 24,5 %, 3 semanas, aviso "Revisar"). Seleccionamos esa frase y dejamos un comentario con **@mención** a Tensae (Alpha) para que le llegue el aviso:

> @Tensae Este requisito es el que más pesa en nuestra estimación: la API de pedidos con aviso en tiempo real a cocina son 56 h (2.128 €, 24,5 % del total, 3 semanas) y en la hoja "Costes y plazos" aparece en "Revisar". En la tabla de prioridades lo marcas como Media y dice que se puede empezar con un correo. ¿Confirmas que en la primera versión basta un correo al restaurante y la pantalla en vivo queda para una segunda fase? Así se ahorrarían unas 20 h aprox. y podemos cumplir el plazo. Necesito tu respuesta antes de la reunión del viernes 20/11.

![Comentario con @mención en los requisitos](img/b5_comentario.png)

> 📸 Pendiente: el comentario sobre la frase del R4 con la @mención resaltada, y la respuesta de Alpha con el hilo **resuelto**.

**Deducción (comentario).** La mención convierte un comentario en una tarea con destinatario: Alpha recibe un correo y no depende de abrir el documento. El comentario es útil porque une el requisito con datos de nuestra hoja (horas, coste, plazo) y plantea una decisión concreta (correo ahora, pantalla en vivo después), coherente con la prioridad Media que Alpha ya puso en su tabla. Así el requisito se discute sobre cifras, no sobre opiniones, y queda constancia del historial.

**Contexto (sugerencia en el acta).** En `Acuerdo.docx` el acuerdo 1 dice que Beta entregará el prototipo funcional (carta, carrito y confirmación) en **30 días naturales**. Con la hoja en la mano, el prototipo exige entrevistas (1 sem), prototipo de pantallas (1), modelo de datos (1) y la API de pedidos (3, en la hoja v1): 6 semanas ≈ 42 días. Cambiamos en **modo Sugerencias** "30" por **"45"** y dejamos un comentario de justificación:

- Original: "...en un plazo de ~~30~~ días naturales..."
- Propuesto: "...en un plazo de **45** días naturales..."

> Proponemos 45 días. El prototipo (carta, carrito y confirmación) exige entrevistas (1 sem), prototipo de pantallas (1), modelo de datos (1) y la API de pedidos (3 sem, la tarea en "Revisar"): 6 semanas de trabajo ≈ 42 días, con margen = 45. En 30 días (≈4,3 semanas) solo cabría sin la API. El proyecto completo son 11 semanas / 224 h / 8.684 €, según Costes_y_plazos.xlsx (v1).

![Sugerencia en modo Sugerencias](img/b5_sugerencia.png)

> 📸 Pendiente: acuerdo 1 con "30" tachado y "45" propuesto (con el color/autor de la sugerencia) y el comentario de justificación al margen. Antes de hacerlo, comprobar que el desplegable de modo muestra **Sugerencias**.

![Decisión de Alpha](img/b5_decision_alpha.png)

> 📸 Pendiente: la decisión de Alpha sobre la sugerencia (aceptada o rechazada con su comentario). Si Alpha no responde, captura del mensaje o aviso enviado pidiéndolo.

**Deducción (sugerencia).** El modo sugerencia no cambia el acta: el texto original sigue ahí hasta que Alpha decide, y queda registrado quién propuso qué. Como Beta tiene permiso de edición, la herramienta nos obliga a proponer en vez de imponer; es la diferencia con el rol comentarista (que ni siquiera podría proponer el cambio en el texto). La cifra de 45 días no es arbitraria: sale de las tareas y semanas de nuestra hoja, de modo que la justificación es comprobable.

**Resultado (fase 3).** Alpha responde en el hilo del requisito 4: confirma que la versión 1 envía solo un **correo automático al restaurante** y que la pantalla de cocina en tiempo real pasa a la fase 2, reescribe el requisito (versión 1.1 de los requisitos) y **marca el comentario como resuelto**. A la vez **acepta nuestra sugerencia 30 → 45 días** (el acuerdo 1 ya dice "45 días naturales" y se añade un "Registro de cambios") con un comentario: el cálculo de 6 semanas de trabajo es razonable y 30 días solo cabían sin la API.

![Comentario resuelto y sugerencia aceptada](img/b5_resultado.png)

> 📸 Pendiente: (1) el hilo del comentario con la respuesta de Alpha y la marca de **Resuelto**; (2) el acuerdo 1 con "45" aceptado y el comentario de Alpha; (3) el requisito 4 reescrito en la versión 1.1.

**Ajuste de la hoja.** Alpha pide quitar la parte de tiempo real. En `Costes_y_plazos.xlsx` la tarea pasa de "API de pedidos y comandas de cocina" (56 h, 3 semanas) a **"API de pedidos y aviso por correo a cocina" (36 h, 2 semanas)**: -20 h y -760 €. Totales: de 224 h / 8.684 € / 11 semanas a **204 h / 7.924 € / 10 semanas**, y la API deja de aparecer en "Revisar" (36 h < 40).

![Hoja antes y después del ajuste](img/b5_hoja_ajustada.png)

> 📸 Pendiente: la hoja Costes ya ajustada (fila de la API con 36 h, TOTAL 204 h / 7.924 € / 10 semanas, aviso "OK" en la API y "Revisar" solo en la pantalla de camareros) y el gráfico recalculado.

**Deducción (resultado).** Comentario y sugerencia cierran el ciclo: lo que empezó como una pregunta con cifras acabó en un cambio de alcance (requisito reescrito), un cambio de plazo (45 días) y un cambio de coste (-760 €) en nuestra hoja, todo con rastro de quién propuso y quién decidió. Que el plazo de 45 días siga valiendo con la hoja ajustada (la ruta del prototipo pasa a 5 semanas = 35 días, con 10 días de margen) da holgura que Alpha dijo que revisaría en la reunión semanal. La hoja demuestra su utilidad: al cambiar solo horas, coste, porcentajes, avisos, total y gráfico se recalculan solos.

### Colaboración: formulario de Alpha respondido

**Contexto.** Tras la reunión, Alpha nos envía un Google Forms "Valoración de la colaboración Alpha–Beta" (4 preguntas: claridad de requisitos, requisito más complicado, plazos de 30 días, qué mejorar). Luis (Beta) lo responde desde su cuenta.

| Pregunta | Respuesta de Luis |
|---|---|
| 1. Claridad de los requisitos (1–5) | 4 |
| 2. Requisito más complicado | Confirmación y aviso a cocina |
| 3. ¿Plazos de 30 días realistas? | Con ajustes |
| 4. Qué mejoraríais | Los requisitos son claros, pero falta decir qué incluye cada "Alta/Media/Baja" en horas o alcance; propondría una plantilla común de comentarios para no duplicar avisos. |

![Formulario respondido por Luis](img/b5_forms_beta.png)

> 📸 Pendiente: pantalla de confirmación de envío (o el formulario ya rellenado) de Luis.

**Deducción.** La respuesta es coherente con lo trabajado: señala el aviso a cocina (la API en tiempo real) como lo más difícil y ve el plazo de 30 días ajustado, que es justo lo que defendemos con la sugerencia de 45. El formulario recoge la opinión individual de forma estructurada: las preguntas de opción múltiple permiten a Alpha filtrarlas y hacer un gráfico, y la de párrafo da el matiz.

---

## B6 · Prueba de permisos (1 pt)

**Contexto.** Probamos qué ve alguien ajeno a la organización con nuestro archivo `Costes_y_plazos.xlsx` en OneDrive/SharePoint, en tres estados: compartido solo con personas concretas, "cualquiera con el enlace" y de nuevo restringido.

![Archivo en ventana de incógnito con acceso restringido](img/b6_incognito_restringido.png)

> 📸 Pendiente: abrir el enlace del archivo en **ventana de incógnito/InPrivate** (sin sesión) con acceso restringido: pide iniciar sesión o deniega.

![Cambio a cualquiera con el enlace](img/b6_cualquiera.png)

> 📸 Pendiente: **Compartir → Configuración del vínculo → Cualquier persona con el vínculo**, con el permiso elegido (ver/editar) visible.

![Archivo abierto en incógnito con enlace público](img/b6_incognito_publico.png)

> 📸 Pendiente: el mismo enlace en incógnito, ahora abre sin iniciar sesión.

![Vuelta a restringido](img/b6_restringido_final.png)

> 📸 Pendiente: configuración final restringida (solo personas concretas) y de nuevo bloqueo en incógnito.

**Deducción.** Con acceso restringido, el incógnito (que no tiene nuestra sesión) no puede entrar: el control va ligado a la identidad. Con "cualquiera con el enlace" abre sin cuenta: **el enlace funciona como contraseña**. Riesgo: si se reenvía, se publica o se indexa, cualquiera accede sin que sepamos quién; no hay trazabilidad por persona y, si el permiso es de edición, puede alterar o borrar costes (datos comerciales sensibles). Por eso se vuelve a restringir al terminar y, si hace falta enlace abierto, se pone solo lectura y con caducidad.

---

## Autoevaluación

**1. ¿Qué diferencia hay entre rol comentarista y modo sugerencia?**
El *rol* es un permiso sobre el archivo: el comentarista puede comentar pero **no modificar** el contenido. El *modo sugerencia* es una forma de trabajar de alguien que sí puede editar: sus cambios no se aplican, quedan propuestos (tachado/subrayado) hasta que el autor los acepta o rechaza. Uno limita lo que se puede hacer; el otro controla cómo entran los cambios.

**2. ¿Qué riesgo tiene "cualquiera con el enlace"?**
Que el acceso depende solo de conocer la URL: se puede reenviar o filtrar, no exige identificarse ni deja constancia de quién entra, y con permiso de edición cualquiera puede cambiar o borrar. Es una fuga de información potencial (precios, datos del cliente) y un incumplimiento de protección de datos si hay datos personales.

**3. ¿Qué haría falta para no depender de Google ni de Microsoft?**
Una alternativa propia o de código abierto autoalojada (Nextcloud + OnlyOffice/Collabora, para ficheros, edición colaborativa, calendario y formularios), con servidor, copias de seguridad, usuarios y permisos gestionados por nosotros, y formatos abiertos (ODF, CSV) para poder migrar. A cambio, asumimos mantenimiento, seguridad y disponibilidad que en SaaS lleva el proveedor.

---

## Pasos que debe hacer el alumno en Microsoft 365

- [ ] Entrar en Microsoft 365 con la cuenta del centro y comprobar acceso a Excel y OneDrive.
- [ ] Comprobar `git push` a tu repositorio de la organización.
- [ ] Subir `archivos/Costes_y_plazos.xlsx` a OneDrive y abrirlo en Excel (Online o escritorio). Comprobar que fórmulas, desplegable y gráfico funcionan (si usas Excel en inglés, las fórmulas se traducen solas).
- [ ] Capturas B1: Tarifas, Costes con total, barra de fórmulas de D2 y G2. Guardar en `img/`.
- [ ] Capturas B2: desplegable, cuadro de validación y mensaje de error.
- [ ] Capturas B3: desbloqueo, intento en celda bloqueada, cambio de horas con recálculo (contraseña de protección: `asir`; para el cuadro de desprotección: Revisar → Desproteger hoja).
- [ ] Captura B4: gráfico circular visible junto a la tabla.
- [ ] Compartir el xlsx con Alpha como **editor** (solo con su cuenta/correo) y capturar la invitación. Si Alpha no comparte lo suyo, documentar el intento con una captura.
- [ ] **Comentario con @mención (B5):** abre `Requisitos.docx` en Google Docs con tu cuenta (te lo comparte Alpha como editor/comentarista) → selecciona la frase "mostrar el pedido al instante en la pantalla de cocina" del requisito 4 → icono **Añadir comentario** (o Ctrl+Alt+M) → escribe `@` y elige a la persona de Alpha (el correo se autocompleta; si Docs pregunta, dale permiso de comentar) → pega el texto del comentario → **Comentar**. Captura el comentario con la mención y, cuando Alpha responda, el hilo resuelto.
- [ ] **Sugerencia en el acta (B5):** abre `Acuerdo.docx` → arriba a la derecha cambia de **Edición** a **Sugerencias** → en el acuerdo 1 borra "30" y escribe "45" → selecciona el cambio y añade un comentario con la justificación → captura (el "30" tachado y el "45" de otro color). Cuando Alpha acepte o rechace, captura su decisión y su comentario.
- [ ] **Formulario (B5):** abre el enlace del Forms de Alpha con tu cuenta, responde las 4 preguntas (ver tabla) → **Enviar** → captura la confirmación. Si el formulario no llega, captura el mensaje pidiéndolo a Alpha.
- [ ] B6: incógnito restringido, "cualquiera con el enlace", incógnito de nuevo, volver a restringir; capturas.
- [ ] Sustituir cada `📸 Pendiente` por la captura real y completar contexto y deducción con lo que se ve de verdad (nombres, fechas, mensajes de Excel).
- [ ] `git add UD4/UD4.2_Alpha-Beta` · `git commit -m "UD4.2: evidencias Beta"` · `git push`.
