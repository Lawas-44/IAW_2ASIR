# Guion de la exposición oral — Grupo 5 (3 minutos, 3 personas)

> Sirve para **ensayar**, no para leerlo delante de la clase: lo que se evalúa es explicarlo **sin leer**. Cada persona habla **1 minuto**. Si os pasáis de tiempo, recortad los ejemplos, no las ideas clave.

## Persona 1 · Cliente y qué ofrece cada suite (≈ 1 min)
- "Somos una consultora y nuestro cliente es un **ayuntamiento de 40 empleados** que tiene **un solo informático** y debe cumplir el **ENS**."
- "Comparamos **Nextcloud Hub** y **ownCloud**. Tienen el mismo origen: Nextcloud nació en 2016 como bifurcación de ownCloud. Hoy son productos muy distintos."
- **Nextcloud** es una suite completa: archivos, chat y videollamadas (Talk), correo y calendario (Groupware) y ofimática (Office).
- **ownCloud** se centra en **compartir archivos**. No trae correo, calendario ni chat.
- **Pase:** "Pero, ¿se puede trabajar a la vez en un documento y dónde quedan los datos? Os lo explica [persona 2]."

## Persona 2 · Edición, licencia y datos (≈ 1 min)
- **Edición simultánea:** las dos lo permiten. Nextcloud trae su propio editor, Nextcloud Office. A ownCloud hay que conectarle uno externo, como Collabora u ONLYOFFICE.
- **Licencia:** Nextcloud usa **AGPLv3**, totalmente libre; el soporte Enterprise es opcional y de pago. ownCloud Infinite Scale tiene el código en **Apache 2.0**, pero sus binarios oficiales llevan una licencia que no es libre. Además, lo compró **Kiteworks** en 2023.
- **Datos:** en los dos casos están **en el servidor que elija el ayuntamiento**, no en una nube extranjera.
- **Pase:** "Con todo esto, ¿cuál le recomendamos? Os lo cuenta [persona 3]."

## Persona 3 · Recomendación (≈ 1 min)
- "Recomendamos **Nextcloud Hub con soporte Enterprise**, en el CPD municipal o en un proveedor español que cumpla el ENS."
- **Por qué:**
  1. Con una sola herramienta cubre todo (archivos, correo, videollamadas y documentos).
  2. Los datos se quedan en España, bajo control municipal, y eso facilita cumplir el ENS.
  3. El soporte compensa que solo haya un informático.
- **Por qué no ownCloud:** habría que montar y mantener aparte el correo, el chat y la ofimática, y eso es demasiado para una sola persona.
- **Cierre:** "Por eso, Nextcloud. ¿Alguna pregunta?"

---

## Preguntas que os pueden hacer (respuestas con argumentos)

> Repartidlas antes: cada persona se prepara las preguntas de su parte. Así, sea cual sea la pregunta, responde quien más sabe de ese tema.

| Pregunta | Responde |
|---|---|
| ¿Qué diferencia hay entre Nextcloud y ownCloud? / ¿Qué ventaja tiene ownCloud? | Persona 1 |
| ¿Qué es la licencia AGPL? / ¿Por qué no Google o Microsoft? | Persona 2 |
| ¿Nextcloud "cumple el ENS"? / ¿No es mucho trabajo para un solo informático? | Persona 3 |

**¿Qué ventaja tiene ownCloud entonces?**
Es más ligero y rápido. Si el cliente solo necesitara compartir archivos sería una buena opción, pero un ayuntamiento necesita más cosas.

**¿Qué es la licencia AGPL?**
Es una licencia libre y *copyleft*: puedes usar y modificar el programa, pero si lo ofreces a otros por red, tienes que compartir también el código modificado.

**¿Por qué no Google Workspace o Microsoft 365, que son más fáciles?**
Porque los datos estarían en manos de una empresa estadounidense, sujeta a leyes de EE. UU. como la CLOUD Act. Para una administración pública la soberanía de los datos es prioritaria. Además, la licencia de Nextcloud es libre y no se paga por usuario y aplicación.

**¿Nextcloud "cumple el ENS"?**
El ENS no se certifica sobre un producto, sino sobre el **sistema** de la organización. Nextcloud ayuda porque es autoalojado: el ayuntamiento controla dónde están los datos, el cifrado, las copias de seguridad y los registros de acceso, que son medidas que pide el ENS. Lo que se certifica es la instalación del ayuntamiento.

**Si solo hay un informático, ¿no es demasiado trabajo autoalojar?**
Sí, por eso recomendamos la suscripción **Enterprise** o que lo aloje un proveedor español. Así el soporte se encarga de las actualizaciones y los parches de seguridad.
