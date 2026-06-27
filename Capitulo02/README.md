# Comunicación comercial y catálogos

## Metadatos

| Atributo | Detalle |
|---|---|
| **Duración estimada** | 70 minutos |
| **Complejidad** | Media |
| **Nivel Bloom** | Crear |
| **Módulo** | 2 — Comunicación Comercial y Catálogos |
| **Versión del laboratorio** | 1.0 (2024) |

---

## Descripción General

En esta práctica aplicarás las capacidades generativas de Microsoft 365 Copilot para crear comunicaciones comerciales de alto impacto. Trabajarás en tres bloques secuenciales: redacción de correos en Outlook adaptados a distintos perfiles de cliente, construcción de un catálogo de productos en PowerPoint asistido por Copilot, y transformación de un mensaje base en tres variantes para diferentes etapas del ciclo de ventas. El laboratorio simula un flujo de trabajo real de un equipo de ventas B2B, donde la velocidad de respuesta y la personalización del mensaje son factores críticos de éxito.

---

## Objetivos de Aprendizaje

Al finalizar esta práctica, serás capaz de:

- [ ] Redactar correos electrónicos comerciales efectivos en Outlook con Copilot, ajustando el tono y el enfoque según el perfil del destinatario (prospecto frío, cliente activo, decisor ejecutivo).
- [ ] Crear un catálogo de productos o servicios en PowerPoint utilizando Copilot para generar diapositivas desde un brief de producto con descripciones de valor estructuradas.
- [ ] Adaptar un mensaje comercial base a tres variantes distintas (seguimiento, propuesta inicial y reactivación) usando las funciones de reescritura y refinamiento de Copilot.
- [ ] Aplicar técnicas de prompt engineering orientadas a comunicación persuasiva, incorporando los componentes clave: rol del emisor, perfil del destinatario, objetivo, tono e información contextual.
- [ ] Guardar y organizar todos los entregables en OneDrive for Business, simulando un flujo de trabajo colaborativo de ventas.

---

## Requisitos Previos

### Conocimientos

- Haber completado la **Práctica 1** del curso o contar con un perfil de cliente y argumentos comerciales de referencia propios.
- Conocimiento básico de navegación en Microsoft Outlook para redacción y envío de correos.
- Familiaridad básica con Microsoft PowerPoint para edición de diapositivas.
- Comprensión de los cuatro elementos de un correo comercial efectivo: asunto atractivo, apertura relevante, propuesta de valor y llamada a la acción (contenido de la Lección 2.1).

### Acceso y Licencias

- Cuenta corporativa Microsoft 365 con licencia **Microsoft 365 Copilot activa** (add-on habilitado por el administrador del tenant).
- Acceso a **Outlook** con Copilot habilitado (función "Redactar con Copilot" visible en la barra de herramientas al crear un nuevo correo).
- Acceso a **PowerPoint** con Copilot habilitado (panel de Copilot visible en la pestaña Inicio).
- Acceso a **OneDrive for Business** con al menos 500 MB de espacio disponible.
- Carpeta de trabajo del curso creada en OneDrive (se verifica en la sección de configuración del entorno).

> ⚠️ **Nota crítica de licenciamiento:** Si al abrir Outlook o PowerPoint no aparece el ícono o panel de Copilot, detente y contacta al instructor antes de continuar. Sin la licencia activa, ningún paso de este laboratorio puede ejecutarse.

---

## Entorno del Laboratorio

### Hardware Recomendado

| Componente | Mínimo | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 8ª gen / AMD equivalente | Intel Core i7 10ª gen o superior |
| Memoria RAM | 8 GB | 16 GB |
| Almacenamiento libre | 10 GB | 20 GB |
| Resolución de pantalla | 1366 × 768 px | 1920 × 1080 px |
| Conexión a Internet | 10 Mbps | 25 Mbps o superior |

### Software Requerido

| Aplicación | Versión | Notas |
|---|---|---|
| Microsoft Outlook | Microsoft 365 Apps 2024 (canal actual) | Desktop o Outlook New |
| Microsoft PowerPoint | Microsoft 365 Apps 2024 (canal actual) | Con panel Copilot activo |
| Microsoft Word | Microsoft 365 Apps 2024 (canal actual) | Ejercicio complementario Bloque 1 |
| OneDrive for Business | Incluido en Microsoft 365 | Sincronización activa requerida |
| Microsoft Edge | 120+ | Navegador recomendado para microsoft365.com |
| Microsoft 365 Copilot | Licencia add-on activa | Verificar antes de iniciar |

### Configuración del Entorno (Pre-laboratorio)

Completa los siguientes pasos de configuración **antes** de iniciar los bloques de práctica. Tiempo estimado: 5 minutos.

**Paso 1 — Crear la carpeta de trabajo en OneDrive:**

1. Abre el navegador Microsoft Edge y navega a: `https://onedrive.com` (inicia sesión con tu cuenta corporativa si se solicita).
2. En el panel izquierdo, haz clic en **Mi OneDrive**.
3. Haz clic en **+ Nuevo** → **Carpeta**.
4. Nombra la carpeta: `Curso_Copilot_M365 > Modulo2`

   > Si ya existe la carpeta `Curso_Copilot_M365` de la Práctica 1, solo crea la subcarpeta `Modulo2` dentro de ella.

5. Confirma que la carpeta aparece en tu OneDrive antes de continuar.

**Paso 2 — Verificar Copilot en Outlook:**

1. Abre **Microsoft Outlook** (aplicación de escritorio).
2. Haz clic en **Nuevo correo** (o `Ctrl + N`).
3. Verifica que en la barra de herramientas del correo aparece el botón **Copilot** (ícono de Copilot) o la opción **Redactar con Copilot**.
4. Cierra el correo sin guardar (`Esc`).

**Paso 3 — Verificar Copilot en PowerPoint:**

1. Abre **Microsoft PowerPoint**.
2. Crea una presentación en blanco.
3. Verifica que en la pestaña **Inicio** o en la barra lateral aparece el botón o panel **Copilot**.
4. Cierra la presentación sin guardar.

**Paso 4 — Preparar el brief de producto (archivo base):**

Crea un nuevo documento de texto en Bloc de notas o Word con el siguiente contenido ficticio. Lo usarás como referencia durante todo el laboratorio:

```
BRIEF DE PRODUCTO — INVENTARÍA PRO
=====================================
Empresa: Inventaría Solutions S.A. de C.V.
Producto: InventaríaPro — Plataforma de gestión de inventarios con IA
Industria objetivo: Retail, distribución, manufactura ligera

CARACTERÍSTICAS PRINCIPALES:
- Predicción de demanda con IA (reduce quiebres de stock hasta 35%)
- Integración nativa con SAP, Oracle y sistemas ERP locales
- Dashboard en tiempo real con alertas automáticas
- Módulo de reabastecimiento automático
- App móvil para supervisores de tienda
- Implementación en la nube en menos de 30 días
- Soporte 24/7 en español

PRECIOS REFERENCIALES:
- Plan Básico: $8,500 MXN/mes (hasta 5 tiendas)
- Plan Profesional: $18,000 MXN/mes (hasta 20 tiendas)
- Plan Enterprise: Precio a convenir (más de 20 tiendas)

CASOS DE ÉXITO:
- Cadena de 12 tiendas en Monterrey: redujo quiebres de stock 38%
- Distribuidora en CDMX: mejoró rotación de inventario 22%
- Empresa de retail en Guadalajara: redujo costos de almacenamiento 15%

PROPUESTA DE VALOR CENTRAL:
InventaríaPro convierte los datos de inventario en decisiones inteligentes,
reduciendo pérdidas por exceso o falta de stock y liberando tiempo del
equipo logístico para actividades de mayor valor.
```

5. Guarda este archivo como `Brief_InventariaPro.txt` en la carpeta `OneDrive > Curso_Copilot_M365 > Modulo2`.

---

## Instrucciones Paso a Paso

---

### Bloque 1: Redacción de Correos Comerciales con Copilot en Outlook

**Duración estimada del bloque:** 25 minutos

**Objetivo del bloque:** Generar tres correos comerciales distintos usando Copilot en Outlook, cada uno dirigido a un perfil de cliente diferente, aplicando técnicas de prompt engineering de la Lección 2.1.

---

#### Paso 1.1 — Correo de Primer Contacto (Prospecto Frío)

**Objetivo:** Redactar un correo de prospección para una Gerente de Logística usando Copilot en Outlook con un prompt estructurado.

**Instrucciones:**

1. Abre **Microsoft Outlook** y haz clic en **Nuevo correo** (`Ctrl + N`).

2. En la barra de herramientas del correo nuevo, haz clic en el botón **Copilot** → selecciona **Redactar con Copilot**.

   > Si usas Outlook New (versión web), el botón Copilot aparece en la parte inferior del área de redacción.

3. En el panel de Copilot que se abre, copia y pega el siguiente prompt en el campo de texto:

   ```
   Actúa como ejecutivo de ventas de Inventaría Solutions, empresa que 
   ofrece InventaríaPro, una plataforma de gestión de inventarios con IA. 
   Redacta un correo de primer contacto dirigido a la Gerente de Logística 
   de una cadena de retail con 15 tiendas en México (Ciudad de México). 
   El objetivo es agendar una llamada de exploración de 20 minutos. 
   Usa un tono profesional pero cercano. Menciona que empresas similares 
   han reducido sus quiebres de stock hasta un 35 %. 
   Extensión máxima: 150 palabras. Incluye un asunto atractivo.
   ```

4. Haz clic en **Generar** y espera el borrador (aproximadamente 10–15 segundos).

5. Lee el borrador generado. Evalúa si cumple con los cuatro elementos: asunto atractivo, apertura relevante, propuesta de valor y llamada a la acción.

6. Si el asunto no es suficientemente atractivo, usa la función **Refinar** (o escribe en el chat de Copilot):

   ```
   Cambia el asunto para que sea más directo y genere curiosidad. 
   Que no supere 60 caracteres.
   ```

7. Una vez satisfecho con el borrador, haz clic en **Conservar** (o **Insertar en correo**) para que el texto se coloque en el cuerpo del mensaje.

8. En el campo **Para:**, escribe una dirección de correo ficticia: `gerente.logistica@retailmx-demo.com`

9. **No envíes el correo.** Haz clic en **Archivo** → **Guardar como borrador** (o `Ctrl + S`).

   > Alternativamente, copia el texto del correo a un documento Word y guárdalo en OneDrive como `Correo_01_ProspectoFrio.docx`.

**Resultado esperado:**

Un correo de entre 120–150 palabras con:
- Asunto que menciona un beneficio cuantificable o genera curiosidad (ej.: *"¿Y si reduces un 35 % los quiebres de stock en tus 15 tiendas?"*)
- Apertura que reconoce el desafío logístico del retail sin sonar genérica
- Mención específica del caso de éxito o dato de impacto
- Llamada a la acción clara para agendar una llamada de 20 minutos
- Tono profesional sin ser excesivamente formal

**Verificación:**

- [ ] El correo tiene asunto definido y atractivo.
- [ ] El cuerpo no supera 150 palabras (puedes usar el contador de palabras de Word para verificar).
- [ ] Incluye una propuesta de valor específica (porcentaje de reducción de quiebres).
- [ ] Termina con una llamada a la acción concreta.
- [ ] El archivo fue guardado como borrador o en OneDrive.

---

#### Paso 1.2 — Correo de Seguimiento (Cliente Activo)

**Objetivo:** Generar un correo de seguimiento post-demo para un cliente que ya conoce el producto, con tono más consultivo.

**Instrucciones:**

1. Abre un **Nuevo correo** en Outlook (`Ctrl + N`).

2. Abre **Redactar con Copilot** y usa el siguiente prompt:

   ```
   Actúa como ejecutivo de ventas de Inventaría Solutions. 
   Redacta un correo de seguimiento dirigido al Gerente de Operaciones 
   de una empresa distribuidora en Monterrey (cliente activo que asistió 
   a una demo de InventaríaPro hace 3 días). 
   El objetivo es resolver dudas pendientes y proponer una reunión para 
   revisar la propuesta económica personalizada. 
   Menciona brevemente los puntos que más le interesaron en la demo: 
   la integración con su ERP actual y el módulo de reabastecimiento automático. 
   Tono: consultivo y orientado a resultados. 
   Extensión: entre 120 y 160 palabras. Incluye asunto.
   ```

3. Genera el borrador y revísalo.

4. Aplica un refinamiento adicional solicitando a Copilot:

   ```
   Agrega una línea que mencione que la implementación puede completarse 
   en menos de 30 días, sin interrumpir las operaciones actuales.
   ```

5. Inserta el texto refinado en el correo.

6. Guarda el correo como borrador o expórtalo a Word como `Correo_02_Seguimiento.docx` en OneDrive (`Modulo2`).

**Resultado esperado:**

Un correo de seguimiento que:
- Hace referencia explícita a la demo reciente (personalización)
- Menciona los puntos de interés del cliente (integración ERP + reabastecimiento automático)
- Incluye el dato de implementación en 30 días
- Propone un paso concreto (reunión para revisar propuesta económica)
- Tiene tono consultivo, no de presión de ventas

**Verificación:**

- [ ] El correo referencia la demo previa de forma natural.
- [ ] Menciona al menos dos características específicas del producto.
- [ ] Incluye la línea de implementación en 30 días (resultado del refinamiento).
- [ ] Propone un siguiente paso claro.
- [ ] Guardado en OneDrive o como borrador.

---

#### Paso 1.3 — Correo para Decisor Ejecutivo (Director General / CFO)

**Objetivo:** Adaptar el mensaje de InventaríaPro para un perfil de alto nivel, enfocando el argumento en impacto financiero y estratégico.

**Instrucciones:**

1. Abre un **Nuevo correo** en Outlook y activa **Redactar con Copilot**.

2. Usa el siguiente prompt:

   ```
   Actúa como ejecutivo senior de ventas de Inventaría Solutions. 
   Redacta un correo ejecutivo dirigido al Director de Finanzas (CFO) 
   de una empresa de retail con 20 tiendas en México. 
   El CFO no ha tenido contacto previo con nosotros, pero fue referido 
   por el Gerente de Logística de su empresa. 
   El objetivo es obtener 15 minutos de su agenda para presentar 
   cómo InventaríaPro impacta directamente en la reducción de costos 
   de inventario y mejora el flujo de caja. 
   Tono: ejecutivo, conciso y orientado al ROI. 
   No uses tecnicismos operativos. 
   Extensión máxima: 120 palabras. Incluye asunto ejecutivo.
   ```

3. Genera el borrador. Observa cómo Copilot cambia el enfoque del mensaje respecto a los correos anteriores (de operaciones/logística a finanzas/ROI).

4. Pide a Copilot el siguiente refinamiento:

   ```
   Reescribe el párrafo central para incluir un dato concreto: 
   empresas similares han reducido costos de almacenamiento un 15 % 
   y mejorado la rotación de inventario un 22 %.
   ```

5. Inserta el texto final en el correo.

6. Guarda como `Correo_03_DecidorEjecutivo.docx` en OneDrive (`Modulo2`).

**Resultado esperado:**

Un correo ejecutivo que:
- No supera 120 palabras
- Menciona la referencia del Gerente de Logística como punto de conexión
- Enfoca el valor en términos financieros (costos, ROI, flujo de caja)
- Incluye al menos un dato cuantificable de impacto
- Tiene asunto ejecutivo y directo (sin emojis ni lenguaje operativo)

**Verificación:**

- [ ] El correo no supera 120 palabras.
- [ ] El enfoque es financiero/estratégico, no operativo.
- [ ] Incluye datos cuantificables (15 % reducción de costos, 22 % rotación).
- [ ] El tono es ejecutivo y conciso.
- [ ] Guardado en OneDrive.

> 💡 **Reflexión del instructor:** Al finalizar el Bloque 1, pide a los participantes que comparen los tres correos en paralelo. La diferencia de enfoque (logístico → consultivo → financiero) ilustra directamente el concepto de adaptación estratégica del mensaje de la Lección 2.1.

---

### Bloque 2: Creación de Catálogo Comercial en PowerPoint con Copilot

**Duración estimada del bloque:** 25 minutos

**Objetivo del bloque:** Crear una presentación de catálogo de producto estructurada y visualmente organizada usando Copilot en PowerPoint, partiendo del brief de InventaríaPro.

---

#### Paso 2.1 — Generar la Presentación Base desde un Prompt

**Objetivo:** Usar Copilot en PowerPoint para crear una presentación de catálogo de 6–8 diapositivas a partir de un prompt descriptivo del producto.

**Instrucciones:**

1. Abre **Microsoft PowerPoint** y selecciona **Presentación en blanco**.

2. **Antes de hacer cualquier edición**, guarda el archivo en OneDrive:
   - Haz clic en **Archivo** → **Guardar como** → **OneDrive — [nombre de tu organización]**
   - Navega a la carpeta `Curso_Copilot_M365 > Modulo2`
   - Nombre del archivo: `Catalogo_InventariaPro`
   - Haz clic en **Guardar**

   > ⚠️ **Crítico:** Copilot en PowerPoint solo funciona completamente cuando el archivo está guardado en OneDrive o SharePoint. Si el archivo está en el disco local, el panel de Copilot estará limitado o inactivo.

3. Una vez guardado, abre el panel de **Copilot** (botón en la pestaña **Inicio** o en la barra lateral derecha).

4. En el campo de texto del panel Copilot, escribe el siguiente prompt:

   ```
   Crea una presentación de catálogo comercial para InventaríaPro, 
   una plataforma de gestión de inventarios con inteligencia artificial 
   para empresas de retail y distribución en México. 
   
   Incluye las siguientes secciones en diapositivas separadas:
   1. Portada con nombre del producto y tagline
   2. El problema: quiebres de stock y exceso de inventario en retail
   3. Nuestra solución: InventaríaPro y sus capacidades clave
   4. Características principales (predicción IA, integración ERP, 
      dashboard en tiempo real, reabastecimiento automático, app móvil)
   5. Casos de éxito con datos cuantificables
   6. Planes y precios (Básico, Profesional, Enterprise)
   7. ¿Por qué InventaríaPro? Propuesta de valor diferenciada
   8. Llamada a la acción: próximos pasos para comenzar
   
   Usa un tono profesional y orientado a resultados de negocio. 
   Incluye bullets concisos, no párrafos largos.
   ```

5. Haz clic en **Generar** y espera a que Copilot cree la presentación (puede tomar 30–60 segundos).

6. Revisa las diapositivas generadas. Copilot creará entre 6 y 10 diapositivas con contenido, diseño de tema y estructura básica.

**Resultado esperado:**

Una presentación con:
- Mínimo 6 diapositivas con las secciones solicitadas
- Contenido en bullets concisos (no párrafos)
- Tema visual aplicado automáticamente por Copilot
- Títulos claros por diapositiva
- Datos de los casos de éxito (38 % quiebres, 22 % rotación, 15 % costos)

**Verificación:**

- [ ] La presentación tiene al menos 6 diapositivas.
- [ ] Existe una diapositiva de portada con nombre del producto.
- [ ] Existe una diapositiva de características con bullets.
- [ ] Existe una diapositiva de casos de éxito con datos.
- [ ] Existe una diapositiva de precios o planes.
- [ ] El archivo está guardado en OneDrive (verificar en la barra de título: debe mostrar el ícono de nube).

---

#### Paso 2.2 — Refinar y Enriquecer Diapositivas con Copilot

**Objetivo:** Usar Copilot para mejorar diapositivas específicas, agregar descripciones de valor y ajustar el contenido generado.

**Instrucciones:**

1. Navega a la diapositiva de **Características Principales** (generalmente la diapositiva 3 o 4).

2. Haz clic en el área de texto principal de esa diapositiva para seleccionarla.

3. En el panel de Copilot, escribe:

   ```
   Reescribe el contenido de esta diapositiva para que cada característica 
   incluya una descripción de beneficio en una línea adicional. 
   Formato: [Característica] — [Beneficio concreto para el negocio]. 
   Máximo 6 características. Tono orientado al cliente de negocio, 
   no al equipo técnico de TI.
   ```

4. Aplica el cambio sugerido por Copilot.

5. Navega a la diapositiva de **Casos de Éxito**.

6. En el panel de Copilot, solicita:

   ```
   Agrega a esta diapositiva un subtítulo que diga: 
   "Resultados reales en empresas mexicanas similares a la tuya." 
   Además, formatea los tres casos de éxito como tarjetas visuales 
   con: Empresa (anónima), Resultado principal y Tiempo de implementación.
   ```

7. Aplica los cambios.

8. Navega a la diapositiva de **Llamada a la Acción** (última diapositiva).

9. En el panel de Copilot, escribe:

   ```
   Reescribe esta diapositiva como una llamada a la acción ejecutiva 
   con tres pasos claros: (1) Solicitar demo gratuita, (2) Revisión de 
   propuesta personalizada, (3) Inicio de implementación en 30 días. 
   Incluye un texto de cierre motivador de una sola línea.
   ```

10. Aplica los cambios y guarda la presentación (`Ctrl + S`).

**Resultado esperado:**

- Diapositiva de características con formato `[Característica] — [Beneficio]`
- Diapositiva de casos de éxito con subtítulo y estructura de tarjetas
- Diapositiva de cierre con tres pasos de acción claros y texto motivador
- Presentación guardada automáticamente en OneDrive

**Verificación:**

- [ ] La diapositiva de características usa el formato solicitado.
- [ ] Los casos de éxito tienen el subtítulo agregado.
- [ ] La última diapositiva tiene tres pasos numerados.
- [ ] El archivo está guardado (ícono de nube sin indicador de cambios pendientes).

---

#### Paso 2.3 — Agregar una Diapositiva de Comparativa de Planes

**Objetivo:** Crear manualmente una diapositiva adicional de comparativa de precios y solicitar a Copilot que genere el contenido comparativo.

**Instrucciones:**

1. Al final de la presentación, agrega una nueva diapositiva: haz clic en **Nueva diapositiva** en la pestaña **Inicio**.

2. Selecciona el diseño **En blanco** o **Título y contenido**.

3. En el panel de Copilot, escribe:

   ```
   Crea el contenido para una diapositiva de comparativa de planes 
   de InventaríaPro con tres columnas: Plan Básico, Plan Profesional 
   y Plan Enterprise. 
   
   Incluye para cada plan:
   - Precio mensual (Básico: $8,500 MXN, Profesional: $18,000 MXN, 
     Enterprise: A convenir)
   - Número de tiendas incluidas
   - Características diferenciadas (2 por plan)
   - Ideal para (tipo de empresa)
   
   Formato sugerido: tabla o tarjetas comparativas. 
   Destaca el Plan Profesional como la opción más popular.
   ```

4. Copia el contenido generado por Copilot y pégalo en la nueva diapositiva. Ajusta el formato visualmente si es necesario.

5. Guarda la presentación (`Ctrl + S`).

**Resultado esperado:**

Una diapositiva de comparativa con:
- Tres columnas o secciones (Básico, Profesional, Enterprise)
- Precios correctos según el brief
- Al menos dos características diferenciadas por plan
- Indicación visual del plan recomendado (Profesional)

**Verificación:**

- [ ] La diapositiva de comparativa existe y tiene tres planes.
- [ ] Los precios coinciden con el brief de producto.
- [ ] El Plan Profesional está destacado de alguna forma.
- [ ] La presentación total tiene entre 8 y 11 diapositivas.
- [ ] Guardada en OneDrive.

> 💡 **Tip:** Si Copilot genera el contenido como texto corrido en lugar de tabla, puedes pedirle: *"Reformatea el contenido anterior como una tabla de tres columnas con las mismas filas para cada plan."*

---

### Bloque 3: Adaptación de Mensajes para el Ciclo de Ventas

**Duración estimada del bloque:** 15 minutos

**Objetivo del bloque:** Tomar un correo base y transformarlo en tres variantes para diferentes etapas del ciclo de ventas usando Copilot en Word, aplicando el concepto de adaptación estratégica del mensaje.

---

#### Paso 3.1 — Preparar el Mensaje Base

**Objetivo:** Crear el correo base en Word que servirá como punto de partida para las tres variantes.

**Instrucciones:**

1. Abre **Microsoft Word** y crea un nuevo documento en blanco.

2. **Guarda inmediatamente** en OneDrive: `Curso_Copilot_M365 > Modulo2 > Adaptacion_Mensajes.docx`

3. Escribe o pega el siguiente mensaje base en el documento:

   ```
   Asunto: InventaríaPro — Solución inteligente para tu inventario

   Estimado/a [NOMBRE],

   Me comunico con usted para presentarle InventaríaPro, nuestra 
   plataforma de gestión de inventarios con inteligencia artificial, 
   diseñada para empresas de retail y distribución en México.

   InventaríaPro permite reducir quiebres de stock hasta un 35 %, 
   optimizar el reabastecimiento de forma automática y obtener 
   visibilidad en tiempo real de todo su inventario.

   Empresas similares a la suya han logrado reducir costos de 
   almacenamiento un 15 % y mejorar la rotación de inventario un 22 % 
   en los primeros 90 días de implementación.

   Me gustaría explorar cómo podríamos ayudarle a obtener 
   resultados similares. ¿Tendría disponibilidad para una 
   conversación breve esta semana?

   Quedo a sus órdenes,
   [NOMBRE_EJECUTIVO]
   Inventaría Solutions
   ```

4. Selecciona **todo el texto** del correo (`Ctrl + A`).

5. Abre el panel de **Copilot** en Word (pestaña **Inicio** → botón **Copilot**).

**Resultado esperado:**

Documento Word guardado en OneDrive con el mensaje base listo para ser transformado.

**Verificación:**

- [ ] El documento está guardado en OneDrive (ícono de nube en la barra de título).
- [ ] El mensaje base está completo con todos los elementos.

---

#### Paso 3.2 — Generar las Tres Variantes con Copilot

**Objetivo:** Transformar el mensaje base en tres variantes distintas para: (A) propuesta inicial a prospecto frío, (B) seguimiento post-reunión y (C) reactivación de cliente inactivo.

**Instrucciones:**

1. Con el documento abierto en Word y el panel Copilot activo, escribe el siguiente prompt:

   ```
   Basándote en el correo base que está en este documento, 
   genera TRES variantes del mismo mensaje para diferentes 
   etapas del ciclo de ventas. 
   
   VARIANTE A — Propuesta inicial a prospecto frío:
   El destinatario no nos conoce. Tono: desafiante y curioso. 
   Abre con una pregunta o dato impactante. Máximo 130 palabras.
   
   VARIANTE B — Seguimiento post-reunión (cliente activo):
   El destinatario asistió a una demo hace 5 días y mostró interés 
   en la integración con SAP. Tono: consultivo y de continuidad. 
   Referencia la demo. Máximo 150 palabras.
   
   VARIANTE C — Reactivación de cliente inactivo:
   El destinatario fue contactado hace 6 meses pero no respondió. 
   Tono: empático, sin presión, con novedad. Menciona una nueva 
   funcionalidad (app móvil para supervisores) como gancho. 
   Máximo 140 palabras.
   
   Presenta las tres variantes claramente separadas con encabezados.
   ```

2. Haz clic en **Generar** y espera el resultado.

3. Revisa las tres variantes generadas. Verifica que cada una:
   - Tiene un tono diferenciado
   - Hace referencia al contexto específico de cada etapa
   - Incluye un asunto adaptado

4. Si alguna variante no cumple con las especificaciones, usa el chat de Copilot para refinarla individualmente. Por ejemplo:

   ```
   La Variante C suena muy similar a la Variante A. 
   Reescríbela para que sea claramente empática con el tiempo 
   transcurrido y mencione explícitamente la app móvil como novedad.
   ```

5. Una vez satisfecho con las tres variantes, guarda el documento (`Ctrl + S`).

**Resultado esperado:**

Un documento Word con cuatro secciones claramente separadas:
- **Mensaje Base** (original)
- **Variante A** — Prospecto frío (tono desafiante/curioso, ≤130 palabras)
- **Variante B** — Seguimiento post-demo (tono consultivo, referencia SAP, ≤150 palabras)
- **Variante C** — Reactivación (tono empático, menciona app móvil, ≤140 palabras)

**Verificación:**

- [ ] Las tres variantes están claramente diferenciadas con encabezados.
- [ ] Cada variante tiene un tono notablemente distinto al leer en secuencia.
- [ ] La Variante B menciona la demo y la integración con SAP.
- [ ] La Variante C menciona la app móvil como novedad.
- [ ] El documento está guardado en OneDrive.

---

#### Paso 3.3 — Reflexión y Comparativa de Variantes

**Objetivo:** Analizar las diferencias entre las tres variantes para consolidar el aprendizaje sobre adaptación estratégica del mensaje.

**Instrucciones:**

1. Al final del documento `Adaptacion_Mensajes.docx`, agrega una nueva sección con el título: **Análisis Comparativo**.

2. En el panel de Copilot, escribe:

   ```
   Basándote en las tres variantes de correo que están en este documento, 
   genera una tabla comparativa con las siguientes columnas:
   - Variante
   - Perfil del destinatario
   - Tono principal
   - Elemento diferenciador clave
   - Llamada a la acción
   
   Añade debajo de la tabla un párrafo breve (máximo 80 palabras) 
   que explique por qué la misma solución requiere mensajes diferentes 
   según la etapa del ciclo de ventas.
   ```

3. Inserta la tabla y el párrafo generados en la sección **Análisis Comparativo** del documento.

4. Guarda el documento final (`Ctrl + S`).

**Resultado esperado:**

Una tabla comparativa de 3 filas × 5 columnas con las diferencias entre las variantes, seguida de un párrafo explicativo sobre la adaptación estratégica del mensaje.

**Verificación:**

- [ ] La tabla comparativa tiene las cinco columnas solicitadas.
- [ ] El párrafo explicativo está presente y es coherente.
- [ ] El documento completo está guardado en OneDrive.

---

## Validación y Pruebas

Al concluir los tres bloques, realiza las siguientes verificaciones finales para confirmar que todos los entregables están completos y correctamente almacenados.

### Lista de Entregables del Laboratorio

| # | Archivo | Ubicación en OneDrive | Estado |
|---|---|---|---|
| 1 | `Correo_01_ProspectoFrio.docx` | `Modulo2/` | ☐ Completado |
| 2 | `Correo_02_Seguimiento.docx` | `Modulo2/` | ☐ Completado |
| 3 | `Correo_03_DecidorEjecutivo.docx` | `Modulo2/` | ☐ Completado |
| 4 | `Catalogo_InventariaPro.pptx` | `Modulo2/` | ☐ Completado |
| 5 | `Adaptacion_Mensajes.docx` | `Modulo2/` | ☐ Completado |
| 6 | `Brief_InventariaPro.txt` | `Modulo2/` | ☐ Completado |

### Verificación de Calidad de Contenido

Abre cada entregable y confirma lo siguiente:

**Correos (entregables 1–3):**
- [ ] Cada correo tiene un enfoque diferente (logístico, consultivo, financiero).
- [ ] Los tres correos respetan los límites de palabras indicados.
- [ ] Cada correo incluye asunto, cuerpo y llamada a la acción.

**Catálogo PowerPoint (entregable 4):**
- [ ] La presentación tiene entre 8 y 11 diapositivas.
- [ ] Incluye portada, problema, solución, características, casos de éxito, precios y cierre.
- [ ] La diapositiva de comparativa de planes está presente.
- [ ] El archivo abre correctamente y no tiene diapositivas en blanco sin contenido.

**Adaptación de mensajes (entregable 5):**
- [ ] El documento tiene el mensaje base y las tres variantes.
- [ ] La tabla comparativa está presente en la sección de Análisis.
- [ ] Las variantes son notablemente distintas entre sí.

### Prueba de Flujo de Trabajo Simulado

Para simular un flujo de trabajo real de ventas:

1. Abre **OneDrive** en el navegador (`https://onedrive.com`).
2. Navega a `Curso_Copilot_M365 > Modulo2`.
3. Verifica que los 6 archivos están listados.
4. Haz clic derecho en `Catalogo_InventariaPro.pptx` → **Compartir**.
5. En el cuadro de compartir, selecciona **Copiar vínculo** → **Cualquier persona con el vínculo puede ver**.
6. Copia el enlace (no es necesario enviarlo; este paso simula el flujo de compartir materiales con un cliente).
7. Cierra el cuadro de compartir.

---

## Solución de Problemas

### Problema 1: El panel de Copilot no aparece en PowerPoint o está deshabilitado

**Síntoma:** Al abrir PowerPoint y hacer clic en la pestaña **Inicio**, el botón **Copilot** no está visible, aparece en gris, o al hacer clic no responde.

**Causa probable:** El archivo de PowerPoint está guardado localmente (en el disco duro del equipo) en lugar de en OneDrive o SharePoint. Copilot en aplicaciones de Microsoft 365 requiere que el archivo esté en la nube para funcionar. Una causa secundaria es que la licencia Microsoft 365 Copilot no esté activa para el usuario.

**Solución:**

1. Verifica la ubicación del archivo: en la barra de título de PowerPoint, debe aparecer el nombre de tu organización o `OneDrive` junto al nombre del archivo. Si dice `Este PC` o muestra una ruta local (ej.: `C:\Users\...`), el archivo no está en la nube.
2. Guarda el archivo en OneDrive: haz clic en **Archivo** → **Guardar como** → selecciona **OneDrive — [nombre de tu organización]** → elige la carpeta `Modulo2` → **Guardar**.
3. Cierra y vuelve a abrir el archivo desde OneDrive.
4. Si el problema persiste después de guardar en OneDrive, verifica la licencia: ve a `https://microsoft365.com`, inicia sesión y comprueba si el ícono de Copilot aparece en la barra lateral. Si no aparece, contacta al administrador del tenant para verificar la asignación de la licencia Copilot.

---

### Problema 2: Copilot genera correos en inglés o con un tono inadecuado

**Síntoma:** Al usar Copilot en Outlook o Word para generar correos, el borrador aparece en inglés, o el tono generado no corresponde al solicitado en el prompt (por ejemplo, genera un correo muy informal cuando se pidió tono ejecutivo).

**Causa probable:** Copilot responde en el idioma del prompt, pero si el prompt contiene mezcla de idiomas o términos técnicos en inglés, puede alternar entre idiomas. El tono incorrecto generalmente ocurre cuando el prompt no especifica explícitamente el tono o cuando la descripción del destinatario es ambigua.

**Solución:**

1. **Para el problema de idioma:** Asegúrate de que todo el prompt esté escrito en español. Si necesitas incluir nombres de productos o términos técnicos en inglés (como "ERP" o "SAP"), especifica en el prompt: *"Redacta el correo completamente en español, incluyendo el asunto."*

   Ejemplo de corrección al prompt:
   ```
   [Contenido del prompt anterior]...
   IMPORTANTE: Redacta TODO el correo en español (México), 
   incluyendo el asunto. No uses anglicismos innecesarios.
   ```

2. **Para el problema de tono:** Agrega ejemplos concretos de lo que significa el tono deseado. En lugar de solo decir "tono ejecutivo", especifica: *"Tono ejecutivo: frases cortas, sin adjetivos superfluos, enfocado en cifras y resultados, sin frases de cortesía excesiva."*

3. Si el borrador generado sigue siendo inadecuado, usa la función **Refinar** (disponible en Outlook) o escribe en el chat de Copilot: *"Reescribe el correo con un tono más [formal/conciso/persuasivo]. Elimina las frases de cortesía excesiva y mantén el foco en el beneficio para el cliente."*

---

## Limpieza del Entorno

Al finalizar el laboratorio, realiza las siguientes acciones para mantener el entorno de trabajo ordenado:

1. **Cerrar borradores en Outlook:**
   - Abre Outlook y navega a la carpeta **Borradores**.
   - Elimina los correos de práctica que guardaste como borrador (los que tienen como destinatario `gerente.logistica@retailmx-demo.com` y similares).
   - Vacía la **Papelera** de Outlook si es necesario.

2. **Verificar sincronización de OneDrive:**
   - Abre el explorador de archivos y navega a la carpeta sincronizada de OneDrive.
   - Confirma que los 5 archivos de entregables muestran el ícono de nube verde (✓) indicando sincronización completa.

3. **Cerrar aplicaciones:**
   - Guarda y cierra Word, PowerPoint y Outlook.
   - No es necesario eliminar los archivos de OneDrive; son los entregables del curso y serán revisados por el instructor.

4. **Opcional — Revocar enlace compartido:**
   - Si generaste un enlace compartido del catálogo en el paso de validación, ve a OneDrive en el navegador.
   - Haz clic derecho en `Catalogo_InventariaPro.pptx` → **Administrar acceso** → elimina el enlace de acceso público.

---

## Resumen

En esta práctica aplicaste las capacidades generativas de Microsoft 365 Copilot en tres escenarios de comunicación comercial del mundo real:

**Bloque 1 — Correos comerciales:** Aprendiste a construir prompts estructurados con los cinco componentes clave (rol, perfil, objetivo, tono, contexto) para generar correos adaptados a perfiles distintos. Verificaste en la práctica cómo el mismo producto (InventaríaPro) requiere un ángulo logístico para la Gerente de Logística, consultivo para el Gerente de Operaciones, y financiero/ROI para el CFO.

**Bloque 2 — Catálogo en PowerPoint:** Creaste una presentación comercial completa desde un prompt descriptivo, refinaste diapositivas individuales con instrucciones específicas y agregaste una diapositiva de comparativa de planes. Comprobaste la importancia de guardar en OneDrive para que Copilot funcione plenamente.

**Bloque 3 — Adaptación de mensajes:** Transformaste un mensaje base en tres variantes para etapas distintas del ciclo de ventas (prospección, seguimiento y reactivación), y generaste un análisis comparativo que consolida el concepto de adaptación estratégica del mensaje.

### Conceptos Clave Aplicados

| Concepto | Aplicación en el laboratorio |
|---|---|
| Prompt engineering para correos | Cinco componentes: rol, perfil, objetivo, tono, contexto |
| Adaptación estratégica del mensaje | Tres correos con el mismo producto, tres enfoques distintos |
| Iteración y refinamiento | Uso de la función Refinar para ajustar borradores |
| Generación de contenido visual | Catálogo de 8+ diapositivas desde un prompt en PowerPoint |
| Flujo de trabajo en la nube | Todos los entregables en OneDrive, listos para compartir |

### Recursos Adicionales

- [Documentación oficial: Copilot en Outlook](https://support.microsoft.com/es-es/topic/copilot-en-outlook-31777a4e-1816-4a1f-8892-cddb2e0f2e8c)
- [Documentación oficial: Copilot en PowerPoint](https://support.microsoft.com/es-es/topic/copilot-en-powerpoint-57133c75-24c0-4519-8096-d0dadf25fb8d)
- [Guía de prompts efectivos para Microsoft 365 Copilot — Microsoft Adoption](https://adoption.microsoft.com/es-es/copilot/)
- [Principios de redacción persuasiva para ventas B2B — HubSpot Blog en español](https://blog.hubspot.es/sales/correo-electronico-de-ventas)
- [Mejores prácticas de comunicación comercial — Salesforce Resources](https://www.salesforce.com/es/resources/articles/sales-email/)

> 📌 **Próxima práctica:** En la **Práctica 3**, utilizarás Copilot Studio para configurar un agente especializado que automatice la generación de cotizaciones y el flujo de costos, integrando los materiales comerciales que creaste en esta práctica.

---
