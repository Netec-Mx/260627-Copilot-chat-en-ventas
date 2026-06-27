# Automatización de cotizaciones

## Metadatos

| Campo            | Detalle                                                                 |
|------------------|-------------------------------------------------------------------------|
| **Duración**     | 100 minutos                                                             |
| **Complejidad**  | Alta                                                                    |
| **Nivel Bloom**  | Aplicar                                                                 |
| **Módulo**       | Módulo 3 — Automatización de cotizaciones con Microsoft 365 Copilot    |
| **Prerequisitos**| Prácticas 1 y 2 completadas; licencia Microsoft 365 Copilot activa     |

---

## Descripción General

En esta práctica configurarás un agente Copilot especializado en cotizaciones utilizando Copilot Studio integrado en Microsoft 365, y construirás una plantilla de flujo de costos automatizada en Excel con asistencia de Copilot. A lo largo de tres fases complementarias, pasarás de la configuración conceptual del agente a la prueba operativa de extremo a extremo: el agente generará borradores de cotización a partir de fuentes de datos reales almacenadas en OneDrive, y el resultado se transferirá a una plantilla Excel para el cálculo final de márgenes y totales. La práctica simula un escenario B2B realista con productos y precios ficticios proporcionados en los archivos del módulo.

---

## Objetivos de Aprendizaje

Al finalizar esta práctica, serás capaz de:

- [ ] Configurar un agente Copilot especializado en Copilot Studio, definiendo instrucciones del sistema, fuentes de conocimiento y comportamiento de respuesta orientados al proceso de cotización.
- [ ] Construir una plantilla de cotización automatizada en Excel con Copilot, incluyendo fórmulas dinámicas, tabla de precios base, descuentos por volumen y cálculo automático de totales.
- [ ] Integrar el agente Copilot con documentos de referencia almacenados en OneDrive para generar borradores de cotización personalizados mediante conversación.
- [ ] Ejecutar y verificar el flujo completo de cotización de extremo a extremo: solicitud al agente → borrador generado → transferencia a plantilla Excel → validación de resultados.

---

## Prerequisitos

### Conocimientos Requeridos

| Área                        | Nivel mínimo requerido                                                        |
|-----------------------------|-------------------------------------------------------------------------------|
| Microsoft 365 general       | Uso básico de Word, Excel, Teams y OneDrive                                   |
| Microsoft Excel             | Fórmulas básicas: `SUMA`, `SI`, `BUSCARV` / `XLOOKUP`, formato condicional   |
| Microsoft Copilot Chat      | Haber completado las Prácticas 1 y 2 del curso                               |
| Copilot Studio              | No se requiere experiencia previa; se guía paso a paso                        |

### Accesos y Recursos Requeridos

| Recurso                                          | Estado requerido                                                                 |
|--------------------------------------------------|---------------------------------------------------------------------------------|
| Licencia Microsoft 365 Copilot activa            | ✅ Obligatorio — verificar con el administrador antes de iniciar                |
| Acceso a Copilot Studio / "Crear un agente"      | ✅ Habilitado por el administrador del tenant                                   |
| Archivos del módulo 3 en OneDrive                | ✅ `M3_ListaPrecios.xlsx` y `M3_CatalogoProductos.docx` cargados en OneDrive   |
| Carpeta de trabajo en OneDrive                   | ✅ `Curso_Copilot/Modulo3/` creada y accesible                                  |
| Microsoft Teams (aplicación de escritorio)       | ✅ Sesión iniciada con cuenta corporativa                                       |
| Navegador Microsoft Edge (versión 120+)          | ✅ Recomendado para acceder a Copilot Studio                                    |

> ⚠️ **Advertencia crítica:** Si no tienes acceso a "Crear un agente" en Copilot Studio, notifica al instructor **antes de comenzar**. El instructor puede proporcionar un agente de demostración pre-configurado para que puedas completar las Fases 2 y 3.

---

## Entorno de Laboratorio

### Hardware Mínimo

| Componente       | Especificación mínima                                    |
|------------------|----------------------------------------------------------|
| Procesador       | Intel Core i5 8ª gen. / AMD equivalente (64 bits)       |
| Memoria RAM      | 8 GB (recomendado 16 GB)                                |
| Almacenamiento   | 10 GB disponibles en disco                              |
| Monitor          | Resolución 1366×768 (recomendado 1920×1080)             |
| Conectividad     | Internet estable ≥ 10 Mbps                              |

### Software Requerido

| Aplicación                        | Versión / Configuración                                         |
|-----------------------------------|-----------------------------------------------------------------|
| Microsoft 365 Apps                | Canal actual 2024 (Word, Excel, PowerPoint, Outlook)           |
| Microsoft Copilot Chat            | Licencia M365 Copilot activa                                   |
| Microsoft Teams (escritorio)      | Versión 2024 incluida en M365                                  |
| Microsoft Copilot Studio          | Acceso vía `copilotstudio.microsoft.com` o Teams               |
| OneDrive for Business             | Sincronización activa con cuenta corporativa                   |
| Microsoft Edge                    | Versión 120+                                                   |

### Configuración Inicial del Entorno

Antes de comenzar los pasos del laboratorio, realiza las siguientes verificaciones:

**1. Verificar archivos del módulo en OneDrive**

Abre el navegador Edge y navega a:
```
https://onedrive.live.com  (o tu OneDrive corporativo)
```
Confirma que en la ruta `Curso_Copilot/Modulo3/` existan los siguientes archivos:

```
Curso_Copilot/
└── Modulo3/
    ├── M3_ListaPrecios.xlsx       ← Lista de precios base (proporcionada por instructor)
    ├── M3_CatalogoProductos.docx  ← Catálogo de productos ficticios
    └── M3_PlantillaCotizacion.xlsx ← Plantilla base (la crearás en la Fase 2)
```

> 📝 **Nota:** Si los archivos `M3_ListaPrecios.xlsx` y `M3_CatalogoProductos.docx` no están disponibles, solicítalos al instructor. Los datos ficticios de estos archivos se detallan en el **Apéndice A** al final de esta guía para que puedas crearlos manualmente si es necesario.

**2. Verificar acceso a Copilot Studio**

Abre Edge y navega a:
```
https://copilotstudio.microsoft.com
```
Si la página carga y muestra el panel principal de Copilot Studio, el acceso está habilitado. Si recibes un error de permisos, notifica al instructor inmediatamente.

**3. Verificar que Excel esté guardando en OneDrive**

Abre Microsoft Excel → Archivo → Cuenta → confirma que la cuenta conectada es tu cuenta corporativa de Microsoft 365.

---

## Pasos del Laboratorio

---

### FASE 1: Configuración del Agente Copilot Especializado en Cotizaciones
**Tiempo estimado: 40 minutos**

---

#### Paso 1.1: Crear el Agente en Copilot Studio

**Objetivo:** Crear un nuevo agente en Copilot Studio con nombre, descripción e instrucciones del sistema orientadas al proceso de cotización B2B.

**Instrucciones:**

1. Abre Microsoft Edge y navega a:
   ```
   https://copilotstudio.microsoft.com
   ```

2. Inicia sesión con tu cuenta corporativa de Microsoft 365 cuando se te solicite.

3. En el panel principal de Copilot Studio, haz clic en el botón **"+ Crear"** (o **"New agent"** si la interfaz está en inglés) ubicado en la esquina superior izquierda o en el centro de la pantalla de bienvenida.

4. Selecciona la opción **"Crear un agente en blanco"** (o *"Start from blank"*) para comenzar con una configuración personalizada.

5. En el campo **"Nombre del agente"**, escribe exactamente:
   ```
   CotiBot - Distribuidora Andina
   ```

6. En el campo **"Descripción"**, escribe:
   ```
   Agente especializado en la generación de borradores de cotización para el
   equipo comercial de Distribuidora Andina S.A. Consulta el catálogo oficial
   de productos y la lista de precios vigente para generar propuestas precisas.
   ```

7. Haz clic en **"Crear"** o **"Siguiente"** para continuar.

**Resultado esperado:** El agente "CotiBot - Distribuidora Andina" aparece creado en el panel de Copilot Studio y se abre el editor del agente con las secciones: Descripción general, Instrucciones, Conocimiento, Acciones y Canales.

**Verificación:** Confirma que el nombre del agente aparece correctamente en la barra superior del editor y que el estado muestra "Borrador" o "Draft".

---

#### Paso 1.2: Redactar las Instrucciones del Sistema (System Prompt)

**Objetivo:** Definir el comportamiento, rol, tono y restricciones del agente mediante instrucciones del sistema precisas y alineadas con las políticas comerciales de la empresa ficticia.

**Instrucciones:**

1. Dentro del editor del agente, localiza la sección **"Instrucciones"** (puede aparecer como *"Instructions"* o *"System prompt"*). Haz clic en ella para expandirla.

2. Borra cualquier texto de ejemplo que aparezca por defecto.

3. Copia y pega el siguiente bloque de instrucciones del sistema en el campo de texto:

```text
Eres CotiBot, el asistente oficial de cotizaciones de Distribuidora Andina S.A.
Tu función principal es ayudar al equipo comercial a generar borradores de
cotización precisos, profesionales y alineados con las políticas de la empresa.

== ROL Y COMPORTAMIENTO ==
- Actúa como un especialista en ventas B2B con amplio conocimiento del catálogo
  de productos de la empresa.
- Responde siempre en español formal y con tono profesional y amigable.
- Sé conciso pero completo: incluye toda la información necesaria para que el
  vendedor pueda revisar y enviar la cotización sin modificaciones adicionales.

== REGLAS DE NEGOCIO ==
- Solo cotiza productos que aparezcan en el catálogo oficial cargado como fuente
  de conocimiento. Si el producto no existe, informa claramente y sugiere el
  artículo más similar disponible.
- Los precios deben tomarse exclusivamente de la lista de precios vigente
  (archivo M3_ListaPrecios.xlsx). No inventes precios ni uses estimados propios.
- Los descuentos máximos permitidos son:
    * 1–10 unidades: hasta 5 % de descuento
    * 11–50 unidades: hasta 10 % de descuento
    * 51 o más unidades: hasta 15 % de descuento
- Nunca ofrezcas descuentos superiores al 15 % sin indicar que requieren
  aprobación del Gerente Comercial.
- Incluye siempre: fecha de vigencia de la cotización (30 días desde hoy),
  condiciones de pago estándar (30 días neto) y tiempo de entrega estimado
  (5–7 días hábiles).

== FORMATO DE RESPUESTA ==
Cuando generes un borrador de cotización, usa siempre esta estructura:

---
COTIZACIÓN N.° [NÚMERO CONSECUTIVO]
Fecha: [FECHA ACTUAL]
Válida hasta: [FECHA + 30 DÍAS]
Cliente: [NOMBRE DEL CLIENTE]
Contacto: [NOMBRE DEL CONTACTO]

DETALLE DE PRODUCTOS:
| Código | Descripción | Cant. | P. Unitario | Descuento | Subtotal |
|--------|-------------|-------|-------------|-----------|----------|
| [...]  | [...]       | [...] | [...]       | [...]     | [...]    |

SUBTOTAL:     $ [VALOR]
IVA (19 %):   $ [VALOR]
TOTAL:        $ [VALOR]

Condiciones de pago: 30 días neto
Tiempo de entrega: 5–7 días hábiles
Vigencia: 30 días desde la fecha de emisión
---

== RESTRICCIONES ==
- No proporciones información financiera interna de la empresa.
- No accedas a sistemas externos no autorizados.
- Si el usuario solicita algo fuera de tu alcance, redirige amablemente hacia
  el proceso correcto o sugiere contactar al área correspondiente.
```

4. Haz clic en **"Guardar"** o en el ícono de guardar (💾) para conservar las instrucciones.

**Resultado esperado:** Las instrucciones del sistema quedan guardadas en el agente. El panel muestra el texto completo sin errores de formato.

**Verificación:** Haz clic fuera del campo de instrucciones y vuelve a hacer clic en la sección "Instrucciones" para confirmar que el texto se guardó correctamente y no se truncó.

---

#### Paso 1.3: Agregar Fuentes de Conocimiento desde OneDrive

**Objetivo:** Conectar el agente con los archivos de referencia (`M3_ListaPrecios.xlsx` y `M3_CatalogoProductos.docx`) almacenados en OneDrive para que el agente pueda consultar datos reales al generar cotizaciones.

**Instrucciones:**

1. Dentro del editor del agente, localiza la sección **"Conocimiento"** (puede aparecer como *"Knowledge"*) en el menú lateral o en las pestañas del editor.

2. Haz clic en **"+ Agregar conocimiento"** o **"+ Add knowledge"**.

3. En el menú de opciones que aparece, selecciona **"Archivos"** o **"Files"** (para cargar documentos desde OneDrive/SharePoint).

4. Se abrirá el selector de archivos de Microsoft 365. Navega a la carpeta:
   ```
   Curso_Copilot/Modulo3/
   ```

5. Selecciona el archivo **`M3_ListaPrecios.xlsx`** y haz clic en **"Agregar"** o **"Add"**.

6. Repite el proceso (pasos 2–5) para agregar también el archivo **`M3_CatalogoProductos.docx`**.

7. Espera a que ambos archivos aparezcan en la lista de fuentes de conocimiento con el estado **"Listo"** o **"Ready"** (el procesamiento puede tardar entre 1 y 3 minutos por archivo).

8. Una vez procesados, verifica que ambos archivos aparezcan así en la sección de Conocimiento:

   ```
   ✅ M3_ListaPrecios.xlsx        — Estado: Listo
   ✅ M3_CatalogoProductos.docx   — Estado: Listo
   ```

9. Haz clic en **"Guardar"** para conservar la configuración.

> 📝 **Nota técnica:** Copilot Studio indexa el contenido de los archivos para permitir búsqueda semántica. El agente no "lee" el archivo completo en cada consulta; en su lugar, recupera los fragmentos más relevantes según la pregunta del usuario. Por esta razón, es importante que los archivos estén bien estructurados (tablas con encabezados claros, nombres de productos consistentes).

**Resultado esperado:** Ambos archivos aparecen listados como fuentes de conocimiento activas con estado "Listo". El agente ahora puede consultar precios y descripciones de productos al responder preguntas.

**Verificación:** Haz clic en el nombre de uno de los archivos en la lista de conocimiento para confirmar que muestra una vista previa del contenido indexado o al menos el nombre y tamaño del archivo correctamente.

---

#### Paso 1.4: Probar el Agente en el Panel de Pruebas

**Objetivo:** Verificar que el agente responde correctamente a solicitudes de cotización, consultando las fuentes de conocimiento configuradas y respetando las instrucciones del sistema.

**Instrucciones:**

1. En el editor del agente, localiza el panel de pruebas en el lado derecho de la pantalla (generalmente llamado **"Probar el agente"** o **"Test your agent"**). Si no es visible, haz clic en el botón **"Probar"** en la barra superior.

2. En el campo de chat del panel de pruebas, escribe el siguiente mensaje y presiona **Enter**:
   ```
   Hola, necesito una cotización para el cliente Empresa Tecnológica S.A.
   Quiero 25 unidades de la Impresora Láser Modelo X-200 con un descuento del 8%.
   El contacto es Juan Ramírez.
   ```

3. Espera la respuesta del agente (puede tardar entre 5 y 15 segundos).

4. Verifica que la respuesta incluya:
   - El formato de cotización definido en las instrucciones (tabla con columnas: Código, Descripción, Cant., P. Unitario, Descuento, Subtotal)
   - El precio tomado del archivo `M3_ListaPrecios.xlsx`
   - El descuento del 8 % aplicado (válido para 11–50 unidades según las reglas)
   - Cálculo de IVA al 19 %
   - Condiciones de pago: 30 días neto
   - Vigencia: 30 días

5. Realiza una segunda prueba para verificar el manejo de restricciones. Escribe:
   ```
   Necesito cotizar 5 unidades del producto X-200 con un descuento del 20%.
   ```

6. Verifica que el agente:
   - Indique que el descuento del 20 % supera el límite permitido para esa cantidad (máx. 5 % para 1–10 unidades)
   - Sugiera el descuento máximo aplicable o indique que requiere aprobación del Gerente Comercial

7. Realiza una tercera prueba para verificar el manejo de productos inexistentes:
   ```
   ¿Puedes cotizarme una Fotocopiadora Industrial Modelo Z-9000?
   ```

8. Verifica que el agente indique que el producto no está en el catálogo y sugiera una alternativa disponible.

**Resultado esperado:** El agente responde correctamente a los tres escenarios de prueba: genera el borrador con formato correcto, rechaza descuentos fuera de política y maneja productos inexistentes de forma apropiada.

**Verificación:** Toma una captura de pantalla de la respuesta al primer mensaje de prueba. Guárdala como `Captura_CotiBot_Prueba1.png` en la carpeta `Curso_Copilot/Modulo3/` de OneDrive. Esta captura será solicitada durante la validación final.

---

### FASE 2: Construcción de la Plantilla de Cotización Automatizada en Excel
**Tiempo estimado: 35 minutos**

---

#### Paso 2.1: Crear y Configurar la Plantilla Base en Excel

**Objetivo:** Crear la estructura de la plantilla de cotización en Excel con las secciones necesarias para el ingreso de datos y los cálculos automáticos.

**Instrucciones:**

1. Abre Microsoft Excel desde el menú de aplicaciones de Microsoft 365 o desde `https://office.com`.

2. Crea un nuevo libro en blanco y guárdalo **inmediatamente** en OneDrive:
   - Haz clic en **Archivo → Guardar como → OneDrive - [Tu organización]**
   - Navega a la carpeta `Curso_Copilot/Modulo3/`
   - Nombre del archivo: `M3_PlantillaCotizacion.xlsx`
   - Haz clic en **Guardar**

   > ⚠️ **Importante:** Copilot en Excel solo funciona completamente cuando el archivo está guardado en OneDrive. No trabajes con archivos locales.

3. Renombra la hoja activa (Sheet1) como `Cotización`. Para ello, haz doble clic sobre la pestaña de la hoja y escribe `Cotización`.

4. Crea una segunda hoja y nómbrala `Precios_Base`. Esta hoja contendrá la tabla de referencia de precios.

5. En la hoja **`Precios_Base`**, crea la siguiente tabla de datos ficticios (escríbelos manualmente o cópialos):

   | A | B | C | D |
   |---|---|---|---|
   | **Código** | **Producto** | **Precio_Base** | **Categoría** |
   | IMP-X200 | Impresora Láser Modelo X-200 | 450000 | Impresión |
   | IMP-X300 | Impresora Multifunción X-300 | 680000 | Impresión |
   | MON-27HD | Monitor 27" HD Pro | 520000 | Pantallas |
   | MON-24FHD | Monitor 24" Full HD | 380000 | Pantallas |
   | TEC-MK100 | Teclado Mecánico MK-100 | 95000 | Periféricos |
   | MOU-ER200 | Mouse Ergonómico ER-200 | 75000 | Periféricos |
   | CAM-WB4K | Cámara Web 4K Business | 210000 | Video |
   | AUD-HS300 | Auriculares con Micrófono HS-300 | 145000 | Audio |
   | SRV-NAS4T | Servidor NAS 4TB | 1850000 | Almacenamiento |
   | UPS-1500 | UPS 1500VA Torre | 320000 | Energía |

6. Convierte este rango en una tabla de Excel:
   - Selecciona el rango `A1:D11`
   - Presiona `Ctrl + T`
   - Confirma que "La tabla tiene encabezados" está marcado
   - Haz clic en **Aceptar**
   - En la pestaña "Diseño de tabla", asigna el nombre: `TBL_Precios`

7. Guarda el archivo con `Ctrl + S`.

**Resultado esperado:** La hoja `Precios_Base` contiene una tabla estructurada con 10 productos ficticios, sus códigos, precios base y categorías, formateada como tabla de Excel con el nombre `TBL_Precios`.

**Verificación:** Haz clic en cualquier celda de la tabla y confirma que en el cuadro de nombres (esquina superior izquierda de Excel) aparece `TBL_Precios` al seleccionar la tabla completa.

---

#### Paso 2.2: Diseñar el Formulario de Cotización con Copilot

**Objetivo:** Usar Copilot en Excel para generar y estructurar el formulario principal de cotización en la hoja `Cotización`, incluyendo las fórmulas de cálculo automático.

**Instrucciones:**

1. Haz clic en la pestaña de la hoja **`Cotización`**.

2. Construye manualmente el encabezado de la cotización en las siguientes celdas:

   ```
   A1: DISTRIBUIDORA ANDINA S.A.
   A2: Cotización Comercial
   A3: (dejar en blanco)
   A4: N.° Cotización:        B4: [fórmula dinámica — se agregará en el paso 5]
   A5: Fecha:                 B5: =HOY()
   A6: Válida hasta:          B6: =B5+30
   A7: Cliente:               B7: [campo de ingreso manual]
   A8: Contacto:              B8: [campo de ingreso manual]
   A9: RUT/NIT Cliente:       B9: [campo de ingreso manual]
   ```

3. Formatea la celda `B5` con formato de fecha corta (`dd/mm/aaaa`): selecciona `B5`, presiona `Ctrl + 1`, elige "Fecha" y el formato `14/03/2024`.

4. Repite el formato de fecha para la celda `B6`.

5. En la celda `B4`, ingresa la siguiente fórmula para generar un número de cotización automático basado en la fecha:
   ```excel
   ="COT-"&TEXT(HOY(),"YYYYMMDD")&"-001"
   ```

6. Ahora crea la tabla de detalle de productos a partir de la fila 12. Escribe los encabezados en la fila 11:

   ```
   A11: Código
   B11: Descripción del Producto
   C11: Cantidad
   D11: Precio Unitario
   E11: % Descuento
   F11: Precio con Descuento
   G11: Subtotal
   ```

7. Selecciona el rango `A11:G11` y aplica formato de encabezado: fondo azul oscuro, texto blanco, negrita.

8. En las filas 12 a 21 (10 filas para productos), agrega las siguientes fórmulas para las columnas calculadas. Para la fila 12:

   - **Columna D (Precio Unitario)** — busca el precio en la tabla de referencia:
     ```excel
     =IFERROR(XLOOKUP(A12,TBL_Precios[Código],TBL_Precios[Precio_Base],"Código no encontrado"),0)
     ```
     > Si tu versión de Excel no tiene XLOOKUP, usa:
     ```excel
     =IFERROR(BUSCARV(A12,TBL_Precios,3,FALSO),0)
     ```

   - **Columna F (Precio con Descuento)**:
     ```excel
     =D12*(1-E12)
     ```

   - **Columna G (Subtotal)**:
     ```excel
     =C12*F12
     ```

   - **Columna B (Descripción)** — busca automáticamente el nombre del producto:
     ```excel
     =IFERROR(XLOOKUP(A12,TBL_Precios[Código],TBL_Precios[Producto],""),0)
     ```

9. Copia las fórmulas de la fila 12 hacia las filas 13 a 21 (selecciona `B12:G12` y arrastra el controlador de relleno hacia abajo hasta la fila 21).

10. Selecciona el rango `A11:G21` y conviértelo en tabla:
    - `Ctrl + T` → confirmar encabezados → **Aceptar**
    - Nombre de la tabla: `TBL_Cotizacion`

**Resultado esperado:** La hoja `Cotización` tiene un encabezado con datos del cliente y una tabla de 10 filas para productos con fórmulas automáticas de búsqueda de precio, cálculo de descuento y subtotal.

**Verificación:** En la celda `A12`, escribe `IMP-X200` y en `C12` escribe `5`. Confirma que la celda `D12` muestra automáticamente `450000` (precio de la Impresora X-200 desde la tabla de referencia) y que `G12` calcula el subtotal correctamente.

---

#### Paso 2.3: Agregar Cálculos de Totales, IVA y Descuentos por Volumen con Copilot

**Objetivo:** Usar Copilot en Excel para generar las fórmulas de totales, IVA, descuentos por volumen y formato condicional para visualizar márgenes.

**Instrucciones:**

1. Debajo de la tabla de productos (fila 23 en adelante), crea la sección de totales:

   ```
   A23: Subtotal antes de IVA:
   A24: IVA (19 %):
   A25: TOTAL A PAGAR:
   A27: Condiciones de pago:     B27: 30 días neto
   A28: Tiempo de entrega:       B28: 5–7 días hábiles
   A29: Vigencia:                B29: 30 días desde la fecha de emisión
   ```

2. Ahora usa **Copilot en Excel** para generar las fórmulas de totales. Abre el panel de Copilot:
   - Haz clic en la pestaña **"Inicio"** de la cinta de opciones
   - Haz clic en el botón **"Copilot"** (ícono de Copilot en la barra de herramientas)
   - Se abrirá el panel de Copilot en el lado derecho

3. En el panel de Copilot, escribe el siguiente prompt:
   ```
   En la celda G23, crea una fórmula que sume todos los subtotales de la columna G
   de la tabla TBL_Cotizacion, ignorando las filas vacías. En G24, calcula el IVA
   del 19% sobre el subtotal de G23. En G25, calcula el total sumando G23 + G24.
   Formatea G25 con negrita y borde doble.
   ```

4. Revisa la sugerencia de Copilot y haz clic en **"Insertar"** o **"Aplicar"** para aceptar las fórmulas propuestas. Las fórmulas deberían ser similares a:
   ```excel
   G23: =SUMA(TBL_Cotizacion[Subtotal])
   G24: =G23*0.19
   G25: =G23+G24
   ```

5. Si Copilot no genera exactamente estas fórmulas, ingrésalas manualmente en las celdas correspondientes.

6. Ahora pide a Copilot que agregue formato condicional para identificar visualmente los productos con descuento alto. En el panel de Copilot, escribe:
   ```
   Agrega formato condicional a la columna E (% Descuento) de la tabla TBL_Cotizacion:
   - Si el descuento es mayor al 10%, resalta la celda en color rojo claro.
   - Si el descuento está entre 5% y 10%, resalta en color amarillo claro.
   - Si el descuento es menor al 5%, no apliques formato especial.
   ```

7. Acepta la sugerencia de Copilot o aplica el formato condicional manualmente:
   - Selecciona el rango `E12:E21`
   - **Inicio → Formato condicional → Nueva regla**
   - Regla 1: "El valor de la celda es mayor que 0.10" → Relleno rojo claro (`#FFB3B3`)
   - Regla 2: "El valor de la celda está entre 0.05 y 0.10" → Relleno amarillo claro (`#FFFF99`)

8. Agrega también una columna de **Margen de Contribución** en la columna H para análisis interno:

   - `H11`: `Margen %` (encabezado)
   - `H12` (y copiar hasta H21):
     ```excel
     =IFERROR((F12-TBL_Precios[Precio_Base])/F12,0)
     ```
     > Esta fórmula es simplificada para el ejercicio; en un escenario real incluiría costos de adquisición.

9. Formatea la columna H como porcentaje con 1 decimal: selecciona `H12:H21` → `Ctrl + 1` → Porcentaje → 1 decimal.

10. Guarda el archivo con `Ctrl + S`.

**Resultado esperado:** La hoja `Cotización` tiene todas las fórmulas de cálculo funcionando: subtotal automático, IVA al 19 %, total final, formato condicional en la columna de descuentos y columna de margen de contribución.

**Verificación:** Con los datos de prueba del Paso 2.2 (`IMP-X200`, cantidad 5), verifica que:
- `G23` muestre `2,250,000` (5 × 450,000)
- `G24` muestre `427,500` (19 % de 2,250,000)
- `G25` muestre `2,677,500` (total con IVA)

---

#### Paso 2.4: Agregar Validación de Datos para Descuentos

**Objetivo:** Implementar validación de datos en la columna de descuentos para que Excel alerte automáticamente cuando se ingrese un descuento fuera de los límites permitidos por política.

**Instrucciones:**

1. Selecciona el rango `E12:E21` (columna de % Descuento en la tabla de productos).

2. Ve a **Datos → Validación de datos**.

3. En la pestaña **"Configuración"**:
   - **Permitir:** Decimal
   - **Datos:** entre
   - **Mínimo:** `0`
   - **Máximo:** `0.15`

4. En la pestaña **"Mensaje de entrada"**:
   - Título: `Descuento permitido`
   - Mensaje: `Ingresa el descuento en formato decimal. Máximo permitido: 15% (0.15). Descuentos superiores requieren aprobación del Gerente Comercial.`

5. En la pestaña **"Mensaje de error"**:
   - Estilo: **Advertencia**
   - Título: `Descuento fuera de política`
   - Mensaje: `El descuento ingresado supera el 15% máximo permitido. Para aplicar este descuento, se requiere autorización del Gerente Comercial. ¿Deseas continuar de todas formas?`

6. Haz clic en **Aceptar**.

7. Formatea el rango `E12:E21` como porcentaje: `Ctrl + 1` → Porcentaje → 1 decimal.

8. Guarda el archivo con `Ctrl + S`.

**Resultado esperado:** Al intentar ingresar un valor mayor a 0.15 (15 %) en cualquier celda de la columna de descuentos, Excel muestra una advertencia con el mensaje de política configurado.

**Verificación:** En la celda `E12`, escribe `0.20` y presiona Enter. Confirma que aparece el cuadro de advertencia con el mensaje de política. Haz clic en **"No"** para rechazar el valor y escribe `0.08` (8 %) en su lugar.

---

### FASE 3: Prueba de Extremo a Extremo del Flujo de Cotización
**Tiempo estimado: 25 minutos**

---

#### Paso 3.1: Publicar el Agente en Microsoft Teams

**Objetivo:** Publicar el agente CotiBot en el canal de Microsoft Teams para que pueda ser utilizado en el flujo de trabajo del equipo comercial.

**Instrucciones:**

1. Regresa al editor del agente en Copilot Studio (`https://copilotstudio.microsoft.com`).

2. En la barra superior del editor, haz clic en el botón **"Publicar"** o **"Publish"**.

3. Confirma la publicación en el cuadro de diálogo que aparece. Espera a que el proceso de publicación se complete (puede tardar entre 1 y 3 minutos).

4. Una vez publicado, localiza la sección **"Canales"** (o *"Channels"*) en el menú del editor.

5. Haz clic en **"Microsoft Teams"** en la lista de canales disponibles.

6. Sigue las instrucciones en pantalla para agregar el agente a Teams:
   - Haz clic en **"Abrir el bot en Teams"** o **"Open bot in Teams"**
   - Se abrirá Microsoft Teams con una ventana de conversación con el agente
   - Haz clic en **"Agregar"** o **"Add"** si se te solicita confirmar la instalación

7. Si el proceso de publicación en Teams no está disponible por restricciones del tenant, utiliza el **panel de pruebas integrado** de Copilot Studio para completar el Paso 3.2.

**Resultado esperado:** El agente CotiBot aparece como un contacto de chat en Microsoft Teams, listo para recibir solicitudes de cotización.

**Verificación:** Abre Microsoft Teams y busca "CotiBot" en la barra de búsqueda. Confirma que aparece en los resultados como un bot disponible.

---

#### Paso 3.2: Ejecutar el Flujo Completo de Cotización

**Objetivo:** Simular un escenario real de ventas B2B completo: solicitar una cotización al agente, recibir el borrador y transferir los datos a la plantilla Excel para el cálculo final.

**Instrucciones:**

**Parte A — Solicitar cotización al agente:**

1. Abre la conversación con CotiBot en Teams (o en el panel de pruebas de Copilot Studio).

2. Escribe el siguiente mensaje de solicitud de cotización completa:
   ```
   Buenos días CotiBot. Necesito preparar una cotización urgente para el cliente
   Constructora del Pacífico Ltda., contacto: María Fernanda Torres.

   Los productos requeridos son:
   - 30 unidades de Monitor 27" HD Pro
   - 30 unidades de Teclado Mecánico MK-100
   - 30 unidades de Mouse Ergonómico ER-200

   El cliente solicita el mejor descuento posible dentro de la política.
   Por favor genera el borrador de cotización completo.
   ```

3. Espera la respuesta del agente. Verifica que el borrador incluya:
   - Encabezado con nombre del cliente y contacto
   - Los tres productos con sus precios tomados del catálogo
   - Descuento del 10 % aplicado (máximo para 11–50 unidades)
   - Cálculo de IVA al 19 %
   - Condiciones de pago y vigencia

4. Copia el contenido del borrador generado por el agente (selecciona el texto y usa `Ctrl + C`).

**Parte B — Transferir datos a la plantilla Excel:**

5. Abre el archivo `M3_PlantillaCotizacion.xlsx` en Excel (debe estar guardado en OneDrive).

6. En la hoja `Cotización`, completa los campos del encabezado:
   - `B7` (Cliente): `Constructora del Pacífico Ltda.`
   - `B8` (Contacto): `María Fernanda Torres`
   - `B9` (RUT/NIT): `76.543.210-9` (ficticio)

7. En la tabla de productos, ingresa los datos del borrador generado por el agente:

   | Celda | Valor |
   |-------|-------|
   | A12   | MON-27HD |
   | C12   | 30 |
   | E12   | 0.10 |
   | A13   | TEC-MK100 |
   | C13   | 30 |
   | E13   | 0.10 |
   | A14   | MOU-ER200 |
   | C14   | 30 |
   | E14   | 0.10 |

8. Verifica que las fórmulas calculen automáticamente:
   - Precios unitarios (columna D) — deben cargarse automáticamente desde `TBL_Precios`
   - Precios con descuento (columna F)
   - Subtotales por línea (columna G)
   - Subtotal general (G23), IVA (G24) y Total (G25)

9. Usa Copilot en Excel para verificar los cálculos. Abre el panel de Copilot y escribe:
   ```
   Revisa los cálculos de la tabla TBL_Cotizacion. Verifica que el descuento del
   10% esté aplicado correctamente a todos los productos y que el total con IVA
   sea correcto. Muéstrame un resumen de los valores calculados.
   ```

10. Revisa el resumen generado por Copilot y confirma que los valores son correctos.

11. Guarda el archivo con `Ctrl + S`.

**Resultado esperado:** La plantilla Excel muestra la cotización completa con los tres productos, descuentos aplicados automáticamente, IVA calculado y total final. Los valores deben ser:

| Producto           | Cant. | P. Unit.  | Desc. | Subtotal    |
|--------------------|-------|-----------|-------|-------------|
| Monitor 27" HD Pro | 30    | $520,000  | 10%   | $14,040,000 |
| Teclado MK-100     | 30    | $95,000   | 10%   | $2,565,000  |
| Mouse ER-200       | 30    | $75,000   | 10%   | $2,025,000  |
| **Subtotal**       |       |           |       | **$18,630,000** |
| **IVA 19%**        |       |           |       | **$3,539,700** |
| **TOTAL**          |       |           |       | **$22,169,700** |

**Verificación:** Confirma que los valores en `G23`, `G24` y `G25` coinciden con los totales esperados en la tabla anterior. Toma una captura de pantalla de la hoja `Cotización` con los datos completos y guárdala como `Captura_Excel_Cotizacion_Final.png` en `Curso_Copilot/Modulo3/`.

---

## Validación y Verificación Final

Al finalizar la práctica, verifica que hayas completado todos los elementos siguientes:

### Lista de Verificación de Entregables

| # | Elemento a verificar | Criterio de éxito |
|---|----------------------|-------------------|
| 1 | Agente CotiBot creado en Copilot Studio | Aparece en el panel de agentes con estado "Publicado" |
| 2 | Instrucciones del sistema configuradas | El agente respeta las reglas de descuento y formato en las pruebas |
| 3 | Fuentes de conocimiento agregadas | `M3_ListaPrecios.xlsx` y `M3_CatalogoProductos.docx` con estado "Listo" |
| 4 | Prueba de restricción de descuento | El agente rechaza descuentos > 15 % y explica la política |
| 5 | Prueba de producto inexistente | El agente indica que el producto no está en catálogo y sugiere alternativa |
| 6 | Plantilla Excel en OneDrive | `M3_PlantillaCotizacion.xlsx` guardado en `Curso_Copilot/Modulo3/` |
| 7 | Tabla `TBL_Precios` configurada | 10 productos con precios en hoja `Precios_Base` |
| 8 | Fórmulas XLOOKUP/BUSCARV funcionando | Precio se carga automáticamente al ingresar código de producto |
| 9 | Formato condicional en descuentos | Celdas se colorean según el rango de descuento aplicado |
| 10 | Validación de datos en columna E | Alerta al ingresar descuento > 15 % |
| 11 | Flujo E2E completado | Cotización de Constructora del Pacífico con totales correctos |
| 12 | Capturas de pantalla guardadas | `Captura_CotiBot_Prueba1.png` y `Captura_Excel_Cotizacion_Final.png` en OneDrive |

### Prueba de Regresión Rápida

Para confirmar que el flujo completo funciona correctamente, realiza esta prueba final de 5 minutos:

1. Abre una nueva conversación con CotiBot (Teams o panel de pruebas).
2. Escribe: `¿Cuál es el precio de la Cámara Web 4K Business para 60 unidades con el máximo descuento?`
3. Confirma que el agente responde con: precio unitario de $210,000, descuento del 15 % (máximo para ≥51 unidades), y calcula el subtotal de $10,710,000 (60 × $210,000 × 0.85).
4. En Excel, ingresa `CAM-WB4K` en `A15`, `60` en `C15` y `0.15` en `E15`. Confirma que `G15` muestra `$10,710,000`.

Si ambos resultados coinciden, el flujo de extremo a extremo está funcionando correctamente.

---

## Solución de Problemas

### Problema 1: Las fuentes de conocimiento en Copilot Studio muestran estado "Error" o no se procesan

**Síntomas:**
- Al agregar `M3_ListaPrecios.xlsx` o `M3_CatalogoProductos.docx` como fuentes de conocimiento, el estado se queda en "Procesando" por más de 10 minutos, o cambia a "Error" con un mensaje de fallo.
- El agente responde que no encuentra información sobre los productos al ser consultado en el panel de pruebas.

**Causa probable:**
El archivo no está accesible para Copilot Studio debido a permisos de OneDrive/SharePoint insuficientes, el archivo está en formato no compatible (versión antigua de Excel `.xls` en lugar de `.xlsx`), o el archivo contiene protección con contraseña que impide la indexación.

**Solución:**
1. Verifica que el archivo esté guardado en **OneDrive for Business** (cuenta corporativa), no en OneDrive personal.
2. Confirma que el archivo tiene formato `.xlsx` (no `.xls`). Si es necesario, ábrelo en Excel y guárdalo como "Libro de Excel (.xlsx)".
3. Verifica que el archivo **no tiene contraseña**: en Excel, ve a **Revisar → Proteger libro** y confirma que no hay protección activa.
4. Confirma que los permisos del archivo permiten acceso a "Todos en la organización" o al menos al usuario que configuró el agente: en OneDrive, haz clic derecho sobre el archivo → **Compartir** → verifica los permisos.
5. Elimina la fuente de conocimiento fallida en Copilot Studio y agrégala nuevamente seleccionando el archivo desde el selector de SharePoint/OneDrive.
6. Si el problema persiste, crea una copia del archivo con un nombre más simple (sin caracteres especiales) y vuelve a intentarlo.

---

### Problema 2: Las fórmulas XLOOKUP en Excel devuelven error `#N/A` o `0` al ingresar códigos de producto

**Síntomas:**
- Al escribir un código de producto (por ejemplo, `IMP-X200`) en la columna A de la tabla `TBL_Cotizacion`, la columna D (Precio Unitario) muestra `#N/A`, `0` o `Código no encontrado` en lugar del precio correcto.
- La fórmula `=XLOOKUP(A12,TBL_Precios[Código],TBL_Precios[Precio_Base],"Código no encontrado")` no encuentra el valor aunque el código existe en la hoja `Precios_Base`.

**Causa probable:**
Las causas más frecuentes son: (1) el código ingresado tiene espacios adicionales al inicio o al final que no son visibles; (2) el código en la tabla `TBL_Precios` y el código ingresado tienen diferente capitalización o caracteres especiales; (3) la tabla `TBL_Precios` no fue nombrada correctamente y la referencia estructurada no resuelve; (4) la versión de Excel no soporta XLOOKUP (requiere Microsoft 365 o Excel 2019+).

**Solución:**
1. **Verificar espacios ocultos:** En la celda con el código, usa la fórmula temporal `=LARGO(A12)` para contar caracteres. Si el resultado es mayor que el número esperado de caracteres del código, hay espacios ocultos. Usa `=ESPACIOS(A12)` para limpiarlos, o aplica la función `TRIM()` en la fórmula: `=XLOOKUP(ESPACIOS(A12),TBL_Precios[Código],TBL_Precios[Precio_Base],"Código no encontrado")`.
2. **Verificar nombre de la tabla:** Haz clic en cualquier celda de la tabla de precios en la hoja `Precios_Base`. En el cuadro de nombres (esquina superior izquierda), confirma que aparece `TBL_Precios`. Si no, selecciona toda la tabla, ve a **Diseño de tabla** y verifica/corrige el nombre.
3. **Versión sin XLOOKUP:** Si tu versión de Excel no tiene XLOOKUP, reemplaza la fórmula con BUSCARV: `=IFERROR(BUSCARV(A12,Precios_Base!$A:$D,3,FALSO),"Código no encontrado")`. Asegúrate de que la columna del precio (Precio_Base) sea la tercera columna del rango de búsqueda.
4. **Verificar que las hojas estén en el mismo libro:** Confirma que las hojas `Cotización` y `Precios_Base` están en el mismo archivo `M3_PlantillaCotizacion.xlsx` y no en libros separados.

---

## Limpieza del Entorno

Al finalizar la práctica, realiza las siguientes acciones de limpieza para mantener el entorno ordenado:

### Archivos a Conservar (No Eliminar)

Los siguientes archivos deben permanecer en OneDrive para prácticas futuras:

```
Curso_Copilot/Modulo3/
├── M3_ListaPrecios.xlsx          ✅ Conservar
├── M3_CatalogoProductos.docx     ✅ Conservar
├── M3_PlantillaCotizacion.xlsx   ✅ Conservar (entregable principal)
├── Captura_CotiBot_Prueba1.png   ✅ Conservar (evidencia)
└── Captura_Excel_Cotizacion_Final.png  ✅ Conservar (evidencia)
```

### Acciones de Limpieza Recomendadas

1. **Cerrar sesiones activas en Copilot Studio:**
   - En el navegador Edge, cierra la pestaña de `copilotstudio.microsoft.com`
   - No es necesario eliminar el agente; permanecerá disponible para la Práctica 4

2. **Limpiar datos de prueba en la plantilla Excel:**
   - Abre `M3_PlantillaCotizacion.xlsx`
   - En la hoja `Cotización`, borra los datos ingresados en las celdas `A12:A21`, `C12:C21` y `E12:E21` (los campos de ingreso manual)
   - **No borres las fórmulas** en las columnas B, D, F, G y H
   - Borra también los campos del cliente (`B7`, `B8`, `B9`)
   - Guarda el archivo con `Ctrl + S`

3. **Cerrar Excel:**
   - Confirma que el archivo se guardó correctamente en OneDrive (el ícono de la nube en la barra de título debe mostrar "Guardado en OneDrive")
   - Cierra Excel

4. **Verificar sincronización de OneDrive:**
   - En la bandeja del sistema (esquina inferior derecha del escritorio), haz clic en el ícono de OneDrive (nube azul)
   - Confirma que el estado muestra "Actualizado" o "Up to date"

> 📝 **Nota:** El agente CotiBot permanecerá publicado en Copilot Studio y disponible en Teams. En la Práctica 4 se utilizará este mismo agente para generar reportes de ventas automatizados, por lo que es importante no eliminarlo.

---

## Resumen

### Logros de la Práctica

En esta práctica de 100 minutos completaste tres componentes fundamentales de la automatización de cotizaciones con Microsoft 365 Copilot:

**Fase 1 — Agente Copilot especializado:** Configuraste CotiBot en Copilot Studio con instrucciones del sistema que definen su rol, restricciones de descuento y formato de respuesta; conectaste el agente con archivos de referencia reales en OneDrive como fuentes de conocimiento; y verificaste su comportamiento ante solicitudes válidas, descuentos fuera de política y productos inexistentes.

**Fase 2 — Plantilla Excel automatizada:** Construiste una plantilla de cotización profesional con búsqueda automática de precios (XLOOKUP/BUSCARV), cálculo dinámico de descuentos y subtotales, IVA automático, formato condicional para alertas visuales de descuento y validación de datos que protege las políticas comerciales.

**Fase 3 — Flujo de extremo a extremo:** Ejecutaste el flujo completo: solicitud al agente en lenguaje natural → borrador de cotización generado en segundos → transferencia a la plantilla Excel → verificación de cálculos con Copilot. Este flujo demuestra cómo un equipo comercial puede reducir el tiempo de preparación de cotizaciones de 20–45 minutos a menos de 5 minutos.

### Conceptos Clave Aplicados

| Concepto | Aplicación en la práctica |
|----------|--------------------------|
| Instrucciones del sistema (system prompt) | Definieron el comportamiento, restricciones y formato de respuesta de CotiBot |
| Fuentes de conocimiento | `M3_ListaPrecios.xlsx` y `M3_CatalogoProductos.docx` como base de datos del agente |
| Dominio delimitado | El agente solo cotiza productos del catálogo oficial, evitando respuestas fuera de contexto |
| XLOOKUP / BUSCARV | Búsqueda automática de precios al ingresar el código del producto |
| Copilot en Excel | Generación asistida de fórmulas y verificación de cálculos mediante lenguaje natural |
| Validación de datos | Protección automática de políticas de descuento máximo (15 %) |
| Formato condicional | Visualización inmediata de alertas de margen por nivel de descuento |

### Recursos Adicionales

- [Documentación oficial: Crear y configurar agentes en Copilot Studio](https://learn.microsoft.com/es-es/microsoft-copilot-studio/authoring-create-edit-topics)
- [Configuración de fuentes de conocimiento en Copilot Studio](https://learn.microsoft.com/es-es/microsoft-copilot-studio/knowledge-add-existing-copilot)
- [Instrucciones del sistema y personalización del comportamiento del agente](https://learn.microsoft.com/es-es/microsoft-copilot-studio/agent-system-prompt)
- [Uso de Copilot en Microsoft Excel](https://support.microsoft.com/es-es/office/copilot-en-excel-d7110502-0334-4b4f-a175-a73abdfc118a)
- [Referencia de la función XLOOKUP en Excel](https://support.microsoft.com/es-es/office/función-buscarx-b7fd680e-6d10-43e6-84f9-88eae8bf5929)
- [Integración de Copilot Studio con Microsoft Teams](https://learn.microsoft.com/es-es/microsoft-copilot-studio/publication-add-bot-to-microsoft-teams)

---

## Apéndice A: Datos Ficticios para Creación Manual de Archivos del Módulo

Si los archivos del módulo no están disponibles, utiliza los siguientes datos para crearlos manualmente antes de comenzar la práctica.

### Contenido de `M3_ListaPrecios.xlsx`

Crea un libro Excel con una hoja llamada `Lista_Vigente` y los siguientes datos:

| Código | Producto | Precio_Base | Categoría | Stock_Disponible | Tiempo_Entrega |
|--------|----------|-------------|-----------|-----------------|----------------|
| IMP-X200 | Impresora Láser Modelo X-200 | 450000 | Impresión | 150 | 3 días |
| IMP-X300 | Impresora Multifunción X-300 | 680000 | Impresión | 80 | 5 días |
| MON-27HD | Monitor 27" HD Pro | 520000 | Pantallas | 200 | 3 días |
| MON-24FHD | Monitor 24" Full HD | 380000 | Pantallas | 250 | 3 días |
| TEC-MK100 | Teclado Mecánico MK-100 | 95000 | Periféricos | 500 | 2 días |
| MOU-ER200 | Mouse Ergonómico ER-200 | 75000 | Periféricos | 600 | 2 días |
| CAM-WB4K | Cámara Web 4K Business | 210000 | Video | 120 | 5 días |
| AUD-HS300 | Auriculares con Micrófono HS-300 | 145000 | Audio | 300 | 3 días |
| SRV-NAS4T | Servidor NAS 4TB | 1850000 | Almacenamiento | 30 | 7 días |
| UPS-1500 | UPS 1500VA Torre | 320000 | Energía | 90 | 5 días |

### Contenido de `M3_CatalogoProductos.docx`

Crea un documento Word con el siguiente contenido mínimo:

```
CATÁLOGO DE PRODUCTOS — DISTRIBUIDORA ANDINA S.A.
Versión vigente: 2024

CATEGORÍA: IMPRESIÓN
- IMP-X200: Impresora Láser Modelo X-200
  Velocidad: 30 ppm. Resolución: 1200 dpi. Conectividad: USB, WiFi, Ethernet.
  Garantía: 1 año. Ideal para oficinas medianas.

- IMP-X300: Impresora Multifunción X-300
  Funciones: Impresión, copia, escaneo, fax. Velocidad: 25 ppm.
  Conectividad: USB, WiFi, Ethernet, Bluetooth. Garantía: 2 años.

CATEGORÍA: PANTALLAS
- MON-27HD: Monitor 27" HD Pro
  Panel: IPS. Resolución: 2560x1440. Tiempo de respuesta: 5ms.
  Puertos: HDMI x2, DisplayPort, USB-C. Garantía: 3 años.

- MON-24FHD: Monitor 24" Full HD
  Panel: VA. Resolución: 1920x1080. Tiempo de respuesta: 4ms.
  Puertos: HDMI, VGA, DisplayPort. Garantía: 2 años.

[Continuar con las demás categorías siguiendo el mismo formato]

POLÍTICA COMERCIAL:
- Descuentos por volumen: 1-10 uds: hasta 5%; 11-50 uds: hasta 10%; 51+ uds: hasta 15%
- Descuentos mayores al 15% requieren aprobación del Gerente Comercial
- Condiciones de pago estándar: 30 días neto
- Tiempo de entrega estándar: 5-7 días hábiles
- Vigencia de cotizaciones: 30 días desde la fecha de emisión
```

Guarda ambos archivos en la carpeta `Curso_Copilot/Modulo3/` de OneDrive antes de comenzar la práctica.

---
