---LAB_START---
LAB_ID: 01-00-01
---MARKDOWN---
# Investigación de competidores y clientes potenciales mediante IA

## Metadatos

| Atributo | Detalle |
|---|---|
| **Duración estimada** | 70 minutos |
| **Complejidad** | Media |
| **Nivel Bloom** | Aplicar (*Apply*) |
| **Módulo** | Módulo 1 — Investigación Comercial con IA |
| **Herramientas principales** | Microsoft 365 Copilot Chat · Microsoft Word con Copilot · OneDrive for Business |

---

## Descripción General

En esta práctica aplicarás las técnicas de prompt engineering aprendidas en la Lección 1.1 para realizar investigación comercial estructurada usando Microsoft 365 Copilot Chat. Simularás el rol de un ejecutivo de ventas que debe prepararse para una reunión con un cliente potencial, investigando competidores clave de su industria y construyendo argumentos comerciales diferenciados. Al finalizar, habrás generado un documento de inteligencia comercial completo en Microsoft Word con asistencia de Copilot, listo para usar en un escenario de venta real.

---

## Objetivos de Aprendizaje

Al completar esta práctica, serás capaz de:

- [ ] Formular prompts estructurados (con contexto, objeto, formato y alcance) en Copilot Chat para obtener análisis de competidores accionables.
- [ ] Identificar y documentar el perfil de un cliente potencial —incluyendo desafíos operativos, métricas prioritarias y preguntas de descubrimiento— usando Copilot Chat como asistente de investigación.
- [ ] Generar una hoja de argumentos comerciales personalizados en Microsoft Word utilizando Copilot integrado, basada en los hallazgos de investigación previos.
- [ ] Distinguir entre prompts genéricos y prompts efectivos, y corregir un prompt deficiente para obtener resultados de mayor calidad.
- [ ] Validar críticamente los resultados generados por Copilot, identificando qué información requiere verificación en fuentes primarias.

---

## Prerrequisitos

### Conocimiento previo requerido

- Haber completado la Lección 1.1: *Investigación de Competidores y Clientes Potenciales mediante IA*.
- Comprensión básica de la estructura de un prompt efectivo (contexto, objeto, formato, alcance).
- Familiaridad con la navegación en Microsoft Teams y Microsoft Word (nivel básico).
- Tener identificado un **sector o industria objetivo** para los ejercicios (puede ser el sector real del participante o uno de los sectores de ejemplo provistos en este laboratorio).

### Acceso y licencias requeridos

- ✅ Cuenta corporativa activa de Microsoft 365 con **licencia Copilot asignada y verificada**.
- ✅ Acceso a **Microsoft 365 Copilot Chat** (confirmado en Teams o en `microsoft365.com/copilot`).
- ✅ Acceso a **Microsoft Word** (versión Microsoft 365 Apps, canal actual 2024).
- ✅ **OneDrive for Business** sincronizado y con espacio disponible (mínimo 100 MB para archivos de práctica).
- ✅ Conexión a Internet estable (mínimo 10 Mbps).

> ⚠️ **CRÍTICO:** Si no ves el icono de Copilot en Teams o en microsoft365.com, detente y contacta al instructor antes de continuar. No es posible realizar esta práctica sin la licencia activa.

---

## Entorno de Laboratorio

### Hardware recomendado

| Componente | Mínimo | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 8ª gen / AMD equivalente | Intel Core i7 10ª gen o superior |
| RAM | 8 GB | 16 GB |
| Almacenamiento libre | 10 GB | 20 GB |
| Resolución de pantalla | 1366 × 768 px | 1920 × 1080 px |
| Conexión a Internet | 10 Mbps | 25 Mbps o superior |

### Software requerido

| Aplicación | Versión | Verificación de acceso |
|---|---|---|
| Microsoft 365 Copilot Chat | Incluido con licencia Copilot | `microsoft365.com/copilot` o Teams → Copilot |
| Microsoft Word | Microsoft 365 Apps (2024) | Abrir Word → verificar icono Copilot en cinta |
| Microsoft Edge | 120+ | Predeterminado en Windows 11 |
| OneDrive for Business | Incluido en M365 | Icono en bandeja del sistema (nube) |

### Configuración inicial del entorno

Antes de comenzar los pasos del laboratorio, ejecuta las siguientes verificaciones en orden:

**Verificación 1 — Confirmar acceso a Copilot Chat:**

```
1. Abrir Microsoft Edge
2. Navegar a: https://microsoft365.com/copilot
3. Iniciar sesión con la cuenta corporativa del curso
4. Verificar que aparece la interfaz de chat de Copilot
   (campo de texto con el mensaje "Pregúntame lo que quieras")
```

**Verificación 2 — Crear carpeta de trabajo en OneDrive:**

```
1. Navegar a: https://onedrive.live.com (cuenta corporativa)
   O abrir el Explorador de archivos → OneDrive - [Empresa]
2. Crear carpeta: "Curso_Copilot_M365" > subcarpeta "Lab01"
3. Confirmar que la carpeta está sincronizada (ícono de nube verde)
```

**Verificación 3 — Confirmar Copilot en Word:**

```
1. Abrir Microsoft Word (aplicación de escritorio)
2. Crear un documento nuevo en blanco
3. Guardar en OneDrive: Curso_Copilot_M365 > Lab01
   Nombre: "Lab01_Argumentos_Comerciales.docx"
4. Verificar que aparece el botón "Copilot" en la cinta (pestaña Inicio
   o pestaña Copilot si está disponible)
```

> 📌 **Nota sobre el sector de práctica:** Este laboratorio usa como escenario base una empresa ficticia llamada **"TechFlow Soluciones"** que vende **software de automatización de inventarios para el sector retail**. Si prefieres usar tu industria real, adapta los nombres y contextos en cada prompt. Los instructores de cada sector pueden encontrar variaciones sugeridas en el Apéndice A al final de este documento.

---

## Pasos del Laboratorio

---

### Paso 1 — Explorar la interfaz de Copilot Chat y comparar prompts genéricos vs. estructurados

**Objetivo:** Familiarizarse con la interfaz de Copilot Chat y experimentar de forma directa la diferencia en calidad de respuesta entre un prompt genérico y uno estructurado, aplicando el concepto central de la Lección 1.1.

**Duración estimada:** 10 minutos

#### Instrucciones

1. Abre **Microsoft Edge** y navega a `https://microsoft365.com/copilot`. Inicia sesión con tu cuenta corporativa si se te solicita.

2. Observa la interfaz de Copilot Chat. Identifica los siguientes elementos antes de escribir cualquier prompt:
   - El campo de texto de entrada (parte inferior de la pantalla).
   - El selector de modo (si está disponible): **"Trabajo"** vs. **"Web"**. Para esta práctica, selecciona **"Web"** o **"Búsqueda en internet"** para que Copilot pueda acceder a información pública de mercado.
   - El historial de conversaciones (panel lateral izquierdo, si está visible).

3. Inicia una **nueva conversación** haciendo clic en el botón **"Nueva conversación"** o el ícono de lápiz/más (+). Esto asegura que no haya contexto previo que afecte las respuestas.

4. Escribe el siguiente prompt genérico (Prompt A) y presiona **Enter** o el botón de enviar:

   ```
   Dime algo sobre la competencia en software de inventarios.
   ```

5. Lee la respuesta. Toma nota mental (o en papel) de:
   - ¿Qué tan específica es la respuesta?
   - ¿Menciona empresas concretas?
   - ¿Incluye precios, geografía o segmento de cliente?
   - ¿Es accionable para una reunión de ventas?

6. Inicia una **nueva conversación** (importante: no continúes en el mismo hilo).

7. Ahora escribe el siguiente prompt estructurado (Prompt B) y presiona **Enter**:

   ```
   Actúa como analista de mercado especializado en tecnología B2B. 
   Necesito un resumen ejecutivo de los tres principales competidores 
   en el mercado de software de gestión y automatización de inventarios 
   para empresas retail medianas (50 a 200 tiendas) en Latinoamérica.
   
   Para cada competidor incluye:
   - Nombre de la empresa y su propuesta de valor principal (1-2 oraciones)
   - Rango de precio aproximado o modelo de cobro si está disponible 
     públicamente
   - Una debilidad o punto de crítica frecuente mencionado por usuarios
   
   Formato de salida: tabla comparativa con columnas: 
   Empresa | Propuesta de Valor | Precio/Modelo | Debilidad Percibida
   ```

8. Lee la respuesta del Prompt B y compárala con la del Prompt A.

#### Resultado Esperado

- El **Prompt A** debería producir una respuesta genérica, posiblemente mencionando categorías de software sin nombres específicos ni datos relevantes para la toma de decisiones.
- El **Prompt B** debería producir una tabla o estructura organizada con al menos 2-3 competidores identificados, sus propuestas de valor diferenciadas y alguna referencia a debilidades o críticas de usuarios.

#### Verificación

- [ ] ¿Puedes identificar claramente los 4 elementos de un prompt efectivo (contexto, objeto, formato, alcance) en el Prompt B?
- [ ] ¿La respuesta del Prompt B contiene información más específica y accionable que la del Prompt A?
- [ ] ¿Copilot generó al menos una tabla o lista estructurada en respuesta al Prompt B?

> 💡 **Reflexión:** Si la respuesta del Prompt B no fue significativamente mejor que la del Prompt A, revisa si seleccionaste el modo "Web" o "Internet" en la interfaz. Copilot en modo solo "Trabajo" puede tener acceso limitado a información pública de mercado.

---

### Paso 2 — Investigación estructurada de competidores

**Objetivo:** Realizar una investigación completa de 2-3 competidores usando prompts en cadena (multi-turn prompting), profundizando progresivamente en la información de cada uno.

**Duración estimada:** 15 minutos

#### Instrucciones

1. Inicia una **nueva conversación** en Copilot Chat.

2. Establece el contexto de la sesión con el siguiente prompt de apertura. Cópialo y ajusta únicamente el texto entre corchetes `[ ]` si estás usando tu industria real:

   ```
   Para toda esta conversación, actúa como mi analista de inteligencia 
   competitiva. Trabajo en TechFlow Soluciones, una empresa que vende 
   software de automatización de inventarios para el sector retail en 
   Latinoamérica. Nuestros clientes objetivo son cadenas de tiendas de 
   entre 50 y 200 puntos de venta.
   
   Confirma que entendiste el contexto y dime si necesitas algún dato 
   adicional antes de comenzar el análisis.
   ```

3. Espera la confirmación de Copilot. Si solicita más información, proporciona el detalle que consideres relevante (por ejemplo, país principal de operación, tipo de producto retail, etc.).

4. Ahora solicita el análisis de competidores con este prompt:

   ```
   Analiza los siguientes competidores en el mercado de software de 
   gestión de inventarios para retail en Latinoamérica. Para cada uno 
   proporciona:
   
   1. Descripción breve de la empresa (2-3 oraciones)
   2. Características principales de su producto
   3. Segmento de cliente al que se dirige principalmente
   4. Estrategia de precio o modelo comercial conocido
   5. Fortalezas clave (máximo 3)
   6. Debilidades o áreas de mejora reportadas por usuarios (máximo 3)
   7. Mensajes de marketing o frases clave que usan en su comunicación
   
   Competidores a analizar:
   - Softland ERP
   - Bind ERP
   - [Agrega aquí un tercer competidor de tu conocimiento o pide a 
     Copilot que sugiera uno relevante]
   
   Formato: sección separada por competidor, con subtítulos claros.
   ```

   > 📌 Si no conoces un tercer competidor, reemplaza la línea del tercero con: `"Sugiere tú el tercer competidor más relevante para este mercado y analízalo."`

5. Una vez recibida la respuesta, profundiza en el competidor que consideres más relevante usando un **prompt de seguimiento** (sin iniciar nueva conversación):

   ```
   Del análisis anterior, profundiza en [nombre del competidor más 
   relevante]. Específicamente necesito:
   
   a) ¿Cuáles son las quejas más frecuentes de sus clientes actuales 
      según reseñas o foros públicos?
   b) ¿Qué tipo de empresas han migrado DESDE este competidor HACIA 
      otras soluciones, y por qué razón?
   c) ¿Cuál sería el argumento más efectivo para que un cliente de 
      [nombre del competidor] considere evaluar nuestra solución?
   ```

6. Copia o captura los resultados más relevantes. Los usarás en el Paso 4 para construir el documento final.

#### Resultado Esperado

- Una sección de análisis por cada competidor con los 7 puntos solicitados, en formato legible y estructurado.
- Un análisis profundo del competidor principal que incluya vulnerabilidades explotables desde el punto de vista comercial.
- Al menos 1-2 argumentos de diferenciación sugeridos por Copilot que puedas usar en conversaciones de venta.

#### Verificación

- [ ] ¿Obtuviste información de al menos 3 competidores con sus fortalezas y debilidades?
- [ ] ¿El análisis profundo del competidor principal incluye información sobre razones de abandono o quejas de clientes?
- [ ] ¿Copilot mantuvo el contexto de "analista de inteligencia competitiva" a lo largo de toda la conversación sin necesidad de repetirlo?

> ⚠️ **Validación crítica:** Antes de usar cualquier cifra de precios, nombre de ejecutivo o estadística en una presentación real, verifica la información directamente en el sitio web oficial del competidor o en fuentes primarias. Copilot puede generar datos aproximados o desactualizados.

---

### Paso 3 — Perfilado de cliente potencial y preparación de reunión

**Objetivo:** Usar Copilot Chat para construir un perfil detallado de un cliente potencial ficticio, identificar sus necesidades operativas y generar preguntas de descubrimiento para una reunión de ventas.

**Duración estimada:** 15 minutos

#### Instrucciones

1. Inicia una **nueva conversación** en Copilot Chat (esto evita que el contexto del análisis de competidores interfiera).

2. Define el escenario del cliente potencial con el siguiente prompt. Ajusta los datos entre corchetes según tu sector o usa los valores predeterminados del escenario TechFlow:

   ```
   Actúa como consultor de ventas B2B con experiencia en el sector retail 
   y tecnología. Voy a tener una reunión en 48 horas con la siguiente 
   persona:
   
   - Nombre: [Carlos Mendoza] (ficticio)
   - Cargo: Director de Operaciones
   - Empresa: Cadena de tiendas "ModaExpress" (ficticia)
   - Sector: Retail de moda y accesorios
   - Tamaño: 80 tiendas en México y Colombia
   - Contexto conocido: La empresa ha tenido problemas recientes con 
     desabastecimiento en temporadas altas y exceso de inventario en 
     productos de baja rotación.
   
   Ayúdame a prepararme para esta reunión.
   ```

3. Después de la respuesta inicial, solicita información más específica con este prompt de seguimiento:

   ```
   Gracias. Ahora necesito que profundices en tres áreas específicas:
   
   ÁREA 1 — DESAFÍOS OPERATIVOS:
   Lista los 5 principales desafíos operativos que enfrentan típicamente 
   los directores de operaciones en cadenas de retail de moda de este 
   tamaño. Ordénalos de mayor a menor impacto en el negocio.
   
   ÁREA 2 — MÉTRICAS Y KPIs PRIORITARIOS:
   ¿Qué métricas y KPIs suele monitorear un Director de Operaciones en 
   retail? Lista al menos 6 indicadores clave y explica brevemente por 
   qué cada uno es relevante para su rol.
   
   ÁREA 3 — PREGUNTAS DE DESCUBRIMIENTO:
   Genera 5 preguntas de descubrimiento que yo (como vendedor de software 
   de automatización de inventarios) debería hacer en esta reunión para 
   entender el dolor real del cliente. Las preguntas deben ser abiertas, 
   no deben sonar como un interrogatorio y deben invitar al cliente a 
   compartir su situación actual.
   
   Formato: tres secciones separadas con numeración clara.
   ```

4. Con la información obtenida, solicita un **mini-briefing de reunión** integrado:

   ```
   Con toda la información de esta conversación, genera un briefing de 
   reunión de una sola página con el siguiente formato:
   
   ## Briefing de Reunión — [Fecha de hoy]
   
   **Cliente:** ModaExpress | Director de Operaciones: Carlos Mendoza
   
   **Contexto del cliente:** (2-3 oraciones)
   
   **Principales dolores identificados:** (lista de 3 puntos)
   
   **Métricas que le importan:** (lista de 4 KPIs clave)
   
   **Mis preguntas de apertura:** (las 3 mejores preguntas de 
   descubrimiento)
   
   **Argumento de valor principal a comunicar:** (1 párrafo que conecte 
   el dolor del cliente con nuestra solución de automatización)
   
   **Posibles objeciones y cómo responderlas:** (2 objeciones comunes 
   con su respuesta sugerida)
   ```

5. Revisa el briefing generado. Si alguna sección está incompleta o genérica, usa un prompt de refinamiento como:

   ```
   La sección de "Argumento de valor principal" quedó muy genérica. 
   Reescríbela siendo más específico sobre cómo la automatización de 
   inventarios resuelve el problema de desabastecimiento en temporadas 
   altas para una cadena de 80 tiendas. Usa un tono consultivo, no de 
   vendedor agresivo.
   ```

6. Copia el briefing final en un archivo de texto temporal o en el documento de Word que creaste en la configuración inicial. Lo integrarás formalmente en el Paso 4.

#### Resultado Esperado

- Un listado de al menos 5 desafíos operativos relevantes para el perfil del cliente.
- Al menos 6 KPIs que el Director de Operaciones monitorea.
- 5 preguntas de descubrimiento abiertas y consultivas.
- Un briefing de reunión de una página con todos los elementos solicitados.

#### Verificación

- [ ] ¿Las preguntas de descubrimiento son abiertas (no se responden con "sí" o "no")?
- [ ] ¿El argumento de valor conecta explícitamente el dolor del cliente (desabastecimiento/exceso de inventario) con la solución ofrecida?
- [ ] ¿El briefing incluye al menos 2 objeciones anticipadas con respuestas sugeridas?

---

### Paso 4 — Generación del documento de argumentos comerciales en Word con Copilot

**Objetivo:** Usar Microsoft Word con Copilot integrado para crear un documento profesional de "Hoja de Argumentos Comerciales" que consolide los hallazgos de investigación de los pasos anteriores.

**Duración estimada:** 20 minutos

#### Instrucciones

1. Abre **Microsoft Word** desde el escritorio o desde `https://office.com`.

2. Abre el archivo que creaste durante la configuración inicial:
   `OneDrive > Curso_Copilot_M365 > Lab01 > Lab01_Argumentos_Comerciales.docx`

   > Si no creaste el archivo en la configuración inicial, créalo ahora: **Archivo → Nuevo → Documento en blanco**, luego **Archivo → Guardar como → OneDrive** con el nombre indicado.

3. Verifica que el archivo esté guardado en OneDrive (la barra de título debe mostrar el ícono de nube o la ruta de OneDrive). **Copilot en Word no funciona completamente en archivos guardados localmente.**

4. Haz clic en el botón **Copilot** en la cinta de opciones (pestaña **Inicio** o pestaña **Copilot**). Se abrirá el panel de Copilot en el lado derecho del documento.

5. En el panel de Copilot de Word, escribe el siguiente prompt para generar la estructura base del documento:

   ```
   Crea un documento titulado "Hoja de Argumentos Comerciales — 
   TechFlow Soluciones" con la siguiente estructura:
   
   1. Resumen Ejecutivo (2 párrafos): descripción de TechFlow Soluciones 
      y su propuesta de valor para el sector retail
   
   2. Análisis Competitivo (tabla): comparativa de 3 competidores con 
      columnas: Empresa, Propuesta de Valor, Debilidades, Oportunidad 
      de Diferenciación para TechFlow
   
   3. Perfil del Cliente Objetivo: descripción del cliente ideal 
      (cadena de retail 50-200 tiendas), sus principales desafíos 
      operativos y KPIs que prioriza
   
   4. Argumentos Comerciales Diferenciadores (lista numerada de 5 
      argumentos): cada argumento debe conectar un dolor del cliente 
      con una capacidad específica de nuestra solución
   
   5. Preguntas de Descubrimiento Recomendadas: lista de 5 preguntas 
      abiertas para reuniones de prospección
   
   6. Manejo de Objeciones Comunes: tabla con 3 objeciones frecuentes 
      y respuestas sugeridas
   
   Usa un tono profesional y consultivo. Aplica formato con títulos, 
   subtítulos y viñetas donde corresponda.
   ```

6. Haz clic en **Generar** (o presiona Enter según la interfaz). Copilot generará el contenido en el documento.

7. Revisa el contenido generado. Identifica al menos **2 secciones** que puedas mejorar con la información específica que obtuviste en los Pasos 2 y 3.

8. Para mejorar la sección de **Análisis Competitivo**, selecciona el texto de esa sección en el documento, haz clic derecho y selecciona **Copilot** → **Reescribir con Copilot**, o usa el panel de Copilot con el siguiente prompt:

   ```
   Reescribe la sección de Análisis Competitivo incorporando los 
   siguientes datos específicos que obtuve de mi investigación:
   
   [Pega aquí los datos más relevantes del análisis de competidores 
   del Paso 2 — al menos los nombres de los competidores y sus 
   debilidades principales]
   
   Mantén el formato de tabla y asegúrate de que la columna 
   "Oportunidad de Diferenciación" sea específica y accionable, 
   no genérica.
   ```

9. Para mejorar la sección de **Argumentos Comerciales**, usa el panel de Copilot:

   ```
   Mejora la sección "Argumentos Comerciales Diferenciadores" 
   usando el siguiente contexto de cliente real que investigué:
   
   Cliente objetivo: Director de Operaciones de cadena de retail 
   de moda con 80 tiendas. Problemas principales: desabastecimiento 
   en temporadas altas y exceso de inventario en productos de baja 
   rotación. KPIs que monitorea: [lista 3-4 KPIs del Paso 3].
   
   Cada argumento debe seguir el formato:
   PROBLEMA DEL CLIENTE → CAPACIDAD DE TECHFLOW → RESULTADO ESPERADO
   
   Ejemplo de formato:
   "Cuando [problema específico], nuestra solución [capacidad concreta] 
   lo que resulta en [beneficio medible]."
   ```

10. Una vez satisfecho con el contenido, aplica formato final al documento:
    - Agrega un encabezado con el nombre de tu empresa y la fecha.
    - Aplica estilos de título (Título 1, Título 2) a las secciones principales.
    - Asegúrate de que las tablas tengan bordes visibles y encabezados en negrita.

11. Guarda el documento (Ctrl+S). Verifica que se guarda automáticamente en OneDrive.

#### Resultado Esperado

- Un documento Word de 3-5 páginas titulado "Hoja de Argumentos Comerciales — TechFlow Soluciones".
- El documento incluye las 6 secciones solicitadas con contenido relevante y específico.
- La sección de Análisis Competitivo contiene datos reales (o verosímiles) de los competidores investigados en el Paso 2.
- Los 5 argumentos comerciales siguen el formato PROBLEMA → CAPACIDAD → RESULTADO.

#### Verificación

- [ ] ¿El archivo está guardado en OneDrive (no en el disco local)?
- [ ] ¿El documento tiene al menos las 6 secciones estructuradas con títulos?
- [ ] ¿Los argumentos comerciales conectan explícitamente el dolor del cliente con una capacidad de la solución?
- [ ] ¿La tabla de objeciones incluye al menos 3 objeciones con respuestas específicas (no genéricas)?

---

### Paso 5 — Refinamiento iterativo y validación del contenido

**Objetivo:** Practicar el refinamiento de prompts y desarrollar el hábito de validación crítica de los resultados generados por Copilot antes de usar el contenido en un contexto comercial real.

**Duración estimada:** 10 minutos

#### Instrucciones

1. Regresa a **Copilot Chat** (`microsoft365.com/copilot`). Inicia una nueva conversación.

2. Practica el refinamiento de un prompt deficiente. Escribe primero este prompt y observa la respuesta:

   ```
   ¿Cuáles son los precios de Softland ERP?
   ```

3. Ahora refina el mismo prompt aplicando la estructura aprendida:

   ```
   Actúa como investigador de mercado. Necesito entender el modelo 
   de precios de Softland ERP para el módulo de gestión de inventarios, 
   orientado a empresas retail medianas en México y Colombia.
   
   Por favor indica:
   1. ¿Tiene precios públicos disponibles en su sitio web? En caso 
      afirmativo, ¿cuáles son?
   2. ¿Qué modelo de licenciamiento usa (suscripción mensual, licencia 
      perpetua, por usuario, por módulo)?
   3. Si no hay precios públicos, ¿qué rangos de precio son típicos 
      para soluciones ERP de este tipo en ese mercado?
   4. ¿Qué factores suelen influir en el precio final?
   
   Si no tienes información actualizada, indícalo claramente y sugiere 
   cómo podría obtenerla.
   ```

4. Observa la diferencia en las respuestas. Presta especial atención a si Copilot indica cuándo la información puede no estar actualizada o cuando sugiere verificación en fuentes primarias.

5. Ahora practica la **validación crítica**. En la misma conversación, escribe:

   ```
   De toda la información que me has dado en esta conversación sobre 
   competidores y precios, ¿qué datos específicos deberían ser 
   verificados en fuentes primarias antes de usarlos en una 
   presentación comercial formal? Organiza tu respuesta en:
   
   - DATOS DE ALTA CONFIANZA: información que probablemente sea 
     precisa y estable
   - DATOS A VERIFICAR: información que puede haber cambiado o 
     que proviene de fuentes secundarias
   - DATOS NO DISPONIBLES: información que Copilot no puede 
     proporcionar con certeza
   ```

6. Lee la respuesta de Copilot. Este ejercicio desarrolla el hábito de usar Copilot como acelerador de investigación mientras se mantiene el criterio profesional sobre la confiabilidad de los datos.

7. Agrega una sección final al documento Word llamada **"Notas de Validación"** donde documentes al menos 3 datos del documento que requieren verificación antes de usar en una presentación real. Puedes pedirle a Copilot en Word que te ayude a redactar esta sección.

#### Resultado Esperado

- Comprensión práctica de cómo un prompt refinado produce resultados significativamente mejores.
- Una clasificación clara de qué información generada por Copilot es de alta confianza vs. qué requiere verificación.
- La sección "Notas de Validación" agregada al documento Word.

#### Verificación

- [ ] ¿Puedes articular con tus propias palabras por qué el segundo prompt produjo mejores resultados que el primero?
- [ ] ¿El documento Word tiene ahora la sección "Notas de Validación" con al menos 3 elementos identificados?
- [ ] ¿Copilot indicó en algún momento que cierta información podría no estar actualizada?

---

## Validación y Pruebas Finales

Al completar todos los pasos del laboratorio, realiza las siguientes verificaciones de cierre:

### Lista de verificación de entregables

| Entregable | Criterio de éxito | ¿Completado? |
|---|---|---|
| **Comparación de prompts (Paso 1)** | Puedes explicar la diferencia entre Prompt A y Prompt B con ejemplos concretos de las respuestas obtenidas | ☐ |
| **Análisis de 3 competidores (Paso 2)** | Tienes fortalezas, debilidades y oportunidades de diferenciación para al menos 3 competidores | ☐ |
| **Briefing de reunión (Paso 3)** | El briefing incluye desafíos del cliente, KPIs, preguntas de descubrimiento, argumento de valor y manejo de objeciones | ☐ |
| **Documento Word completo (Paso 4)** | Archivo guardado en OneDrive con las 6 secciones y contenido específico (no solo texto genérico) | ☐ |
| **Sección de validación (Paso 5)** | Al menos 3 datos identificados que requieren verificación en fuentes primarias | ☐ |

### Prueba de integración final

Para verificar que el aprendizaje es transferible, realiza este ejercicio de cierre (5 minutos):

Abre una nueva conversación en Copilot Chat y escribe el siguiente prompt **sin copiar/pegar** de los ejemplos anteriores — redáctalo tú mismo aplicando lo aprendido:

```
[Redacta un prompt desde cero para investigar UN competidor de tu 
industria real, aplicando los 4 elementos: contexto, objeto, 
formato y alcance. El prompt debe solicitar al menos 3 tipos de 
información distintos y especificar el formato de salida.]
```

Si el resultado es más específico y útil que un prompt genérico, has demostrado dominio del objetivo de aprendizaje principal de esta práctica.

---

## Solución de Problemas

### Problema 1 — Copilot Chat no responde o muestra error de acceso

**Síntoma:** Al navegar a `microsoft365.com/copilot` o intentar usar Copilot en Teams, aparece un mensaje de error como *"Tu organización no tiene acceso a Copilot"*, *"Licencia requerida"*, o la interfaz de chat simplemente no aparece.

**Causa probable:** La licencia de Microsoft 365 Copilot no está asignada a la cuenta del usuario, o fue asignada recientemente y aún no se ha propagado (puede tardar hasta 24 horas). También puede ocurrir que el administrador del tenant haya restringido el acceso a Copilot para ciertos grupos de usuarios.

**Solución:**

```
Paso 1: Verificar licencia asignada
- Navegar a: https://myaccount.microsoft.com
- Ir a: Suscripciones o Licencias
- Verificar que aparece "Microsoft 365 Copilot" en la lista de licencias activas

Paso 2: Si la licencia no aparece
- Contactar al instructor o al administrador de TI inmediatamente
- Proporcionar: nombre de usuario, tenant de Microsoft 365
- El administrador debe ir a: Centro de administración M365 → 
  Usuarios → [usuario] → Licencias → Agregar "Microsoft 365 Copilot"

Paso 3: Si la licencia fue asignada recientemente
- Cerrar sesión completamente: Ctrl+Shift+Del → limpiar caché
- Esperar 15-30 minutos y volver a intentar
- Alternativamente: abrir Edge en modo InPrivate y volver a iniciar sesión

Paso 4: Solución temporal durante el laboratorio
- Si el problema persiste, trabajar en pareja con un compañero que 
  tenga acceso activo, observando y contribuyendo a los prompts
- El instructor puede compartir su pantalla para demostración grupal
```

---

### Problema 2 — El botón de Copilot no aparece en Microsoft Word o genera error al usarlo

**Síntoma:** Al abrir el documento Word guardado en OneDrive, el botón "Copilot" no aparece en la cinta de opciones, aparece en gris (deshabilitado), o al hacer clic genera el error *"Copilot no está disponible para este documento"* o *"Guarda el archivo en la nube para usar Copilot"*.

**Causa probable:** El archivo Word está guardado localmente en el disco duro del equipo (no en OneDrive for Business), o la versión de Word instalada no es la del canal actual 2024 de Microsoft 365 Apps. Copilot en Word requiere obligatoriamente que el archivo esté en OneDrive for Business o SharePoint Online.

**Solución:**

```
Paso 1: Verificar ubicación del archivo
- Revisar la barra de título de Word
- Si dice "C:\Users\..." o similar → el archivo está guardado localmente
- Si dice "OneDrive - [Nombre de empresa]" → está en la nube (correcto)

Paso 2: Mover el archivo a OneDrive
- En Word: Archivo → Guardar una copia → OneDrive - [Empresa]
- Navegar a la carpeta: Curso_Copilot_M365 > Lab01
- Guardar con el nombre: Lab01_Argumentos_Comerciales.docx
- Cerrar el archivo local y abrir el que está en OneDrive

Paso 3: Verificar versión de Word
- En Word: Archivo → Cuenta → Información del producto
- Debe mostrar "Microsoft 365 Apps" y versión 2024 (build 17xxx o superior)
- Si la versión es antigua: Archivo → Cuenta → Opciones de actualización 
  → Actualizar ahora

Paso 4: Verificar que Copilot aparece en la cinta
- Pestaña "Inicio" → buscar botón "Copilot" (ícono de estrella/chispa)
- Si no aparece: Ver → Personalizar cinta → verificar que "Copilot" 
  esté habilitado
- Reiniciar Word completamente si el botón sigue sin aparecer

Paso 5: Alternativa si el problema persiste
- Usar Word Online (office.com → Word) en lugar de la aplicación de 
  escritorio, que también tiene Copilot integrado y elimina el problema 
  de almacenamiento local
```

---

## Limpieza del Entorno

Al finalizar el laboratorio, realiza las siguientes acciones para mantener el entorno organizado:

### Acciones requeridas

1. **Guardar y cerrar el documento Word:**
   - Asegúrate de que el documento `Lab01_Argumentos_Comerciales.docx` esté guardado en OneDrive (Ctrl+S).
   - El archivo debe permanecer en OneDrive para ser utilizado como referencia en prácticas posteriores del curso.

2. **Organizar el historial de Copilot Chat:**
   - En Copilot Chat, las conversaciones se guardan automáticamente en el historial.
   - No es necesario eliminarlas; sin embargo, si el administrador del tenant tiene políticas de retención de datos, sigue las instrucciones específicas de tu organización.

3. **Verificar la estructura de carpetas en OneDrive:**
   ```
   OneDrive for Business
   └── Curso_Copilot_M365
       └── Lab01
           └── Lab01_Argumentos_Comerciales.docx  ✅ (debe existir)
   ```

4. **Cerrar pestañas del navegador** relacionadas con el laboratorio, manteniendo abierta solo la sesión de Microsoft 365 si se continuará con otras prácticas.

### Lo que NO se debe eliminar

- ✅ **Conservar** el archivo `Lab01_Argumentos_Comerciales.docx` — se usará como base en la Práctica 2.
- ✅ **Conservar** la carpeta `Curso_Copilot_M365` en OneDrive — se usará en todos los laboratorios del curso.

---

## Resumen

### Lo que aprendiste en esta práctica

En este laboratorio aplicaste los conceptos fundamentales de la Lección 1.1 en un flujo de trabajo comercial completo:

1. **Prompt engineering efectivo:** Experimentaste de forma directa la diferencia entre un prompt genérico y uno estructurado, y comprobaste cómo los cuatro elementos (contexto, objeto, formato, alcance) transforman la calidad de los resultados de Copilot Chat.

2. **Investigación de competidores:** Usaste prompts en cadena (*multi-turn*) para construir un análisis competitivo progresivo, estableciendo contexto al inicio de la conversación y profundizando iterativamente en la información más relevante.

3. **Perfilado de clientes potenciales:** Generaste un briefing de reunión completo —incluyendo desafíos operativos, KPIs, preguntas de descubrimiento y manejo de objeciones— en minutos, replicando un proceso que normalmente requiere horas de investigación manual.

4. **Documentación con Copilot en Word:** Creaste un documento profesional de argumentos comerciales usando Copilot integrado en Word, refinando el contenido con prompts específicos y datos reales de tu investigación.

5. **Validación crítica:** Desarrollaste el hábito de clasificar la información generada por IA según su nivel de confiabilidad, identificando qué datos requieren verificación antes de usarse en contextos comerciales formales.

### Conceptos clave para recordar

| Concepto | Definición práctica |
|---|---|
| **Prompt estructurado** | Instrucción que incluye contexto + objeto + formato + alcance para obtener respuestas específicas y accionables |
| **Multi-turn prompting** | Técnica de usar múltiples prompts en la misma conversación para profundizar progresivamente, aprovechando que Copilot mantiene el contexto |
| **Modo Web vs. Trabajo** | Web = acceso a información pública en internet; Trabajo = acceso a archivos internos de la organización |
| **Validación crítica** | Proceso de identificar qué datos de Copilot son de alta confianza vs. cuáles requieren verificación en fuentes primarias |
| **Copilot en Word** | Requiere obligatoriamente archivo guardado en OneDrive/SharePoint; permite generar y refinar contenido directamente en el documento |

### Recursos adicionales

- 📖 [Documentación oficial de Microsoft Copilot Chat](https://support.microsoft.com/es-es/copilot)
- 📖 [Microsoft Learn: Fundamentos de Microsoft 365 Copilot](https://learn.microsoft.com/es-es/copilot/microsoft-365/microsoft-365-copilot-overview)
- 📖 [Guía de prompts efectivos — Microsoft Adoption Center](https://adoption.microsoft.com/es-es/copilot/)
- 📖 [Biblioteca de prompts de Copilot para ventas — Microsoft](https://adoption.microsoft.com/es-es/copilot/prompt-gallery/)

### Conexión con la siguiente práctica

En la **Práctica 2** utilizarás el documento `Lab01_Argumentos_Comerciales.docx` generado hoy como punto de partida para crear comunicaciones comerciales efectivas: correos de prospección, catálogos de productos y presentaciones en PowerPoint, aplicando las capacidades generativas de Copilot en Word, Outlook y PowerPoint.

---

## Apéndice A — Sectores Alternativos para el Escenario de Práctica

Si tu industria es diferente al retail, puedes adaptar todos los prompts de este laboratorio usando las siguientes variaciones:

| Sector | Empresa ficticia sugerida | Producto/Servicio | Cliente objetivo |
|---|---|---|---|
| **Manufactura** | "ProducTech Industrial" | Software de planificación de producción (MRP) | Director de Planta / Gerente de Operaciones |
| **Servicios financieros** | "FinServ Analytics" | Plataforma de análisis de riesgo crediticio | Director de Riesgos / CFO |
| **Salud** | "MedLogix Soluciones" | Software de gestión de insumos médicos | Director Administrativo de hospital/clínica |
| **Construcción** | "BuildFlow Tech" | Plataforma de gestión de proyectos y presupuestos | Director de Proyectos / Gerente de Obra |
| **Educación** | "EduAdmin Pro" | Sistema de gestión académica y administrativa | Director Académico / Rector |

Para adaptar el laboratorio a cualquiera de estos sectores, reemplaza en todos los prompts:
- "TechFlow Soluciones" → nombre de la empresa ficticia del sector
- "software de automatización de inventarios para retail" → producto/servicio del sector
- "Director de Operaciones de cadena de retail" → cargo y perfil del cliente objetivo del sector

---

*Fin del Laboratorio 01-00-01*

---
LAB_END---
