# MatrIA

Una colega de IA para el personal técnico del parque científico. Aplicación web de un solo fichero.

**Usar la app:** https://fborrasumh.github.io/matria/

**Idiomas:** español (por defecto), inglés y portugués; selector en la barra superior (o `?lang=en` / `?lang=pt` en la URL).

## Qué hace

- **Barra «¿Qué necesitas?»**: la persona escribe con sus palabras («haz el triaje de esta propuesta», «¿qué tengo pendiente hoy?») y el código —sin IA— reconoce la tarea y el proyecto por palabras clave en español, inglés y portugués. Lo que no encaja en ninguna tarea se puede guardar como nota del expediente.
- **Doce tareas clasificadas en cinco momentos del trabajo técnico**:
  - *Captación y triaje*: triaje de una propuesta (seis dimensiones con cita, radar, recomendación, preguntas y alertas) y exploración de oportunidades en la universidad (publicaciones recientes de la institución vía OpenAlex o lista propia).
  - *Evaluación*: informe de evaluación (due diligence) y guion de entrevista con un experto.
  - *Acompañamiento y seguimiento*: acta de reunión o entrevista (las acciones pasan a pendientes), revisión de seguimiento frente al expediente, hoja de ruta con servicios del parque y encaje con una convocatoria requisito a requisito.
  - *Comunicación*: respuesta a la persona emprendedora (incluido un «no» con motivo real) y memorando para comité o dirección.
  - *Memoria y aprendizaje*: preguntar al expediente (con modo tutor para personal nuevo) y prioridades del día.
- **Bucle redacta–critica–decide** (actor–crítico–jefe): en modo «Revisado» una IA redacta, otra critica y una tercera integra o rechaza cada objeción y decide si el resultado está listo (hasta tres vueltas). Cada papel puede usar un proveedor distinto (OpenAI, Gemini, Claude); si los tres son el mismo, la app lo avisa. Modo «Rápido»: una sola llamada.
- **Agenda del día calculada por el código**: pendientes vencidos y próximos, resultados sin decidir, proyectos sin actividad y tareas que faltan según la fase.
- **Expediente por proyecto**: cada tarea (entrada, resultado, revisión, modelos, comprobaciones), nota, decisión y corrección se guarda en el navegador y puede usarse como memoria en las siguientes tareas.
- **Criterio del parque**: una «constitución» editable (misión, qué se busca, líneas rojas, qué exige aprobación humana, confidencialidad, servicios, umbral del triaje) y un criterio aprendido de las correcciones del equipo, que se añaden a cada petición.
- **Salidas**: Word del resultado y del expediente, CSV de interacciones, copia JSON completa (sin claves) que se puede abrir en otro navegador y se fusiona con lo existente.
- **Ejemplo sin clave** (proyecto ficticio AquaSens con triaje revisado y acta) en los tres idiomas.

## Qué comprueba el código (y no la IA)

- Que cada cita aparece literalmente en el material o en el expediente (✓/⚠).
- Las cifras que añade la IA y no están en el material.
- En el triaje, una dimensión sin cita verificada no cuenta en la media, y se señala si la recomendación contradice el umbral del parque.
- En convocatorias, ningún requisito queda como «cumple» sin una cita del proyecto encontrada.
- En la exploración, que cada trabajo citado esté en la lista; en las prioridades, que cada proyecto exista; en la hoja de ruta, que los servicios citados figuren en la constitución.
- Los problemas detectados por el código se pasan al crítico y al jefe como hechos comprobados.

## Cómo se usa la IA

Con la propia clave de OpenAI, Google Gemini o Anthropic Claude (una por proveedor, desde el botón «IA»). Las claves se guardan solo en el navegador. No hace falta servidor. La exploración de publicaciones consulta la API pública de OpenAlex.

## Privacidad

Proyectos, interacciones, decisiones, correcciones y claves se guardan solo en este navegador (IndexedDB y localStorage). Hacia el proveedor de IA sale el material de la tarea y, si se marca, un extracto del expediente, con correos, DNI/NIE y teléfonos enmascarados; **los nombres de personas y empresas no se enmascaran**. Antes del primer envío de cada sesión se muestra una muestra de lo que sale y se pide confirmación. No se debe pegar información confidencial sin el acuerdo que corresponda.

## Límites

- No envía correos, no llama por teléfono ni actúa por su cuenta: propone y la persona decide. La «proactividad» es la agenda que se calcula al abrir la app, no un proceso que trabaje de noche.
- No reentrena ningún modelo: la constitución y el criterio aprendido se añaden como texto a cada petición.
- El clasificador de peticiones usa palabras clave; puede equivocarse y siempre ofrece alternativas.
- La verificación de citas comprueba que el texto existe, no que la interpretación sea correcta. Lo generativo (guion de entrevista, hoja de ruta, correos) no siempre lleva citas.
- Los datos viven en un navegador: sin copia JSON, borrar los datos del navegador los elimina. No es una herramienta de equipo con edición simultánea.
- Probada con IA simulada de los tres proveedores; no se ha probado con claves reales ni contra la API real de OpenAlex.
- Lee texto de Word, PDF y PowerPoint; las imágenes de esos ficheros no se envían y los PDF escaneados no se leen.

## Autoría

Fernando Borrás Rocher (Universidad Miguel Hernández de Elche).

Inspirada en las ideas de AIA y Mother descritas por Luis Pareras (InVivo Partners, 2026), *A Timeline For The Future of Venture Capital*: triaje en un minuto, bucle actor–crítico–jefe con modelos distintos, memoria persistente, constitución y colega que propone qué hacer.

ORCID: Fernando Borrás Rocher [0000-0002-5519-4573](https://orcid.org/0000-0002-5519-4573)

## Cómo citar

Borrás Rocher, F. (2026). *MatrIA* (v1.0.0) [Software]. (DOI en trámite)

## Licencia

MIT. Véase [LICENSE](LICENSE).
