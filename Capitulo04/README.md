# Simulación de Precios y Reportes

## Metadatos

| Campo            | Detalle                                                                 |
|------------------|-------------------------------------------------------------------------|
| **Duración**     | 100 minutos                                                             |
| **Complejidad**  | Alta                                                                    |
| **Nivel Bloom**  | Aplicar                                                                 |
| **Módulo**       | Módulo 4 — Simulación de Precios y Automatización de Reportes          |
| **Prácticas previas requeridas** | Prácticas 1, 2 y 3 completadas (o archivos de entregables disponibles) |

---

## Descripción General

Esta práctica de cierre integra las capacidades analíticas avanzadas de Microsoft 365 Copilot para construir escenarios de simulación de precios en Excel, automatizar la generación de reportes ejecutivos de ventas en Word y PowerPoint, y consolidar un portafolio de ventas completo. Los participantes aplicarán el flujo de trabajo completo del curso —investigación → comunicación → cotización → reporte— utilizando Copilot como asistente analítico en cada etapa. Al finalizar, cada participante contará con un conjunto de entregables profesionales que demuestran el uso estratégico de Copilot en un ciclo de ventas real.

---

## Objetivos de Aprendizaje

Al completar este laboratorio, el participante será capaz de:

- [ ] Construir y analizar escenarios de simulación de precios (análisis what-if) en Excel utilizando Copilot, evaluando el impacto de variaciones de precio, descuentos y costos en el margen de utilidad.
- [ ] Formular prompts analíticos efectivos en lenguaje natural para obtener tablas comparativas, gráficas de sensibilidad y recomendaciones de estrategia de precios desde Copilot Chat y Copilot en Excel.
- [ ] Automatizar la generación de reportes de ventas periódicos utilizando Copilot en Excel, Word y PowerPoint, transformando datos en resúmenes ejecutivos, gráficas interpretadas y recomendaciones accionables.
- [ ] Aplicar el flujo completo de trabajo aprendido en el curso para consolidar un caso de ventas integral con soporte de Copilot en cada etapa.

---

## Requisitos Previos

### Conocimiento y Experiencia

- Haber completado las Prácticas 1, 2 y 3 del curso, o contar con los archivos de entregables de módulos anteriores disponibles en OneDrive.
- Conocimiento intermedio de Excel: uso de tablas, gráficas básicas y formato condicional.
- Familiaridad con Copilot Chat y Copilot integrado en aplicaciones de Microsoft 365 (Word, Excel, PowerPoint).
- Comprensión de los conceptos de margen de utilidad, precio de lista, descuentos y costos base (cubiertos en lecciones anteriores del curso).

### Acceso y Licencias

- Cuenta de Microsoft 365 activa con licencia **Microsoft 365 Copilot** habilitada.
- Acceso a OneDrive for Business con al menos 10 GB de espacio disponible.
- Archivos del Módulo 4 descargados y guardados en OneDrive (ver sección de Entorno de Laboratorio).
- Acceso a: Excel, Word, PowerPoint, Copilot Chat y Microsoft Edge o Chrome (versión 120+).

> ⚠️ **Aviso crítico de licenciamiento:** Sin una licencia Microsoft 365 Copilot activa y asignada a tu cuenta, ningún paso de esta práctica puede realizarse. Verifica tu acceso antes de comenzar ejecutando Copilot Chat en [microsoft365.com/copilot](https://microsoft365.com/copilot).

---

## Entorno de Laboratorio

### Requisitos de Hardware

| Componente        | Mínimo requerido                                      | Recomendado                     |
|-------------------|-------------------------------------------------------|---------------------------------|
| Procesador        | Intel Core i5 8ª gen / AMD equivalente (64 bits)     | Intel Core i7 10ª gen o superior |
| Memoria RAM       | 8 GB                                                  | 16 GB                           |
| Almacenamiento    | 10 GB disponibles                                     | SSD con 20 GB disponibles       |
| Monitor           | 1366 × 768 px                                         | 1920 × 1080 px                  |
| Conectividad      | 10 Mbps estables                                      | 25 Mbps o superior              |
| Periféricos       | Teclado y ratón funcionales                           | Micrófono para entrada de voz   |

### Requisitos de Software

| Aplicación                    | Versión requerida                                          |
|-------------------------------|------------------------------------------------------------|
| Microsoft Excel               | Microsoft 365 Apps (canal actual 2024)                     |
| Microsoft Word                | Microsoft 365 Apps (canal actual 2024)                     |
| Microsoft PowerPoint          | Microsoft 365 Apps (canal actual 2024)                     |
| Microsoft 365 Copilot Chat    | Licencia Copilot activa (add-on M365 E3/E5 o Business Premium) |
| OneDrive for Business         | Incluido en Microsoft 365 (sincronización activa)          |
| Navegador web                 | Microsoft Edge 120+ o Google Chrome 120+                   |

### Preparación del Entorno — Archivos de Trabajo

Antes de iniciar los pasos del laboratorio, crea la estructura de carpetas en OneDrive y carga los archivos necesarios:

**Paso A — Crear carpeta de trabajo en OneDrive:**

1. Abre el navegador y ve a [onedrive.live.com](https://onedrive.live.com) o accede desde [microsoft365.com](https://microsoft365.com) → OneDrive.
2. Crea la siguiente estructura de carpetas:

```
OneDrive/
└── Curso_Copilot_Ventas/
    ├── Practica_1/   (entregables previos)
    ├── Practica_2/   (entregables previos)
    ├── Practica_3/   (entregables previos)
    └── Practica_4/   ← carpeta activa para este laboratorio
```

**Paso B — Crear el archivo base de Excel (si no se proporcionó por el instructor):**

Si el instructor no ha proporcionado el archivo de datos, crea manualmente el libro de Excel con los siguientes datos ficticios. Abre Excel desde Microsoft 365, crea un nuevo libro y guárdalo en `OneDrive/Curso_Copilot_Ventas/Practica_4/` con el nombre:

```
Lab04_Base_Ventas_Productos.xlsx
```

Ingresa los siguientes datos en la **Hoja 1** (renómbrala como `Productos`):

| ID_Producto | Nombre_Producto          | Categoría     | Costo_Unitario | Precio_Lista | Unidades_Vendidas_Mes | Descuento_Aplicado |
|-------------|--------------------------|---------------|----------------|--------------|-----------------------|--------------------|
| P001        | Válvula Industrial V-200 | Mecánica      | 95             | 140          | 320                   | 0%                 |
| P002        | Sensor de Presión SP-50  | Electrónica   | 210            | 315          | 185                   | 5%                 |
| P003        | Bomba Centrífuga BC-10   | Hidráulica    | 450            | 630          | 75                    | 10%                |
| P004        | Filtro Industrial FI-300 | Mecánica      | 60             | 90           | 540                   | 0%                 |
| P005        | Compresor Compacto CC-5  | Neumática     | 780            | 1100         | 42                    | 8%                 |
| P006        | Rodamiento de Precisión RP-22 | Mecánica | 35             | 55           | 890                   | 0%                 |
| P007        | Actuador Eléctrico AE-15 | Electrónica   | 320            | 480          | 130                   | 12%                |
| P008        | Manguera Hidráulica MH-8 | Hidráulica    | 28             | 45           | 1200                  | 5%                 |
| P009        | Variador de Frecuencia VF-3 | Electrónica | 560           | 840          | 68                    | 7%                 |
| P010        | Reductor de Velocidad RV-7 | Mecánica   | 195            | 290          | 215                   | 0%                 |

Agrega una **Hoja 2** (renómbrala como `Ventas_Mensuales`) con los siguientes datos de ventas del mes:

| Mes       | Vendedor          | Región    | Producto                   | Unidades | Precio_Venta | Ingreso_Total | Costo_Total | Utilidad   |
|-----------|-------------------|-----------|----------------------------|----------|--------------|---------------|-------------|------------|
| Octubre   | Ana Martínez      | Norte     | Válvula Industrial V-200   | 80       | 140          | 11200         | 7600        | 3600       |
| Octubre   | Carlos Ruiz       | Sur       | Sensor de Presión SP-50    | 45       | 299.25       | 13466.25      | 9450        | 4016.25    |
| Octubre   | Ana Martínez      | Norte     | Filtro Industrial FI-300   | 150      | 90           | 13500         | 9000        | 4500       |
| Octubre   | Laura Gómez       | Centro    | Bomba Centrífuga BC-10     | 20       | 567          | 11340         | 9000        | 2340       |
| Octubre   | Carlos Ruiz       | Sur       | Rodamiento de Precisión RP-22 | 300   | 55           | 16500         | 10500       | 6000       |
| Octubre   | Pedro Sánchez     | Este      | Compresor Compacto CC-5    | 12       | 1012         | 12144         | 9360        | 2784       |
| Octubre   | Laura Gómez       | Centro    | Actuador Eléctrico AE-15   | 35       | 422.4        | 14784         | 11200       | 3584       |
| Octubre   | Pedro Sánchez     | Este      | Manguera Hidráulica MH-8   | 400      | 42.75        | 17100         | 11200       | 5900       |
| Octubre   | Ana Martínez      | Norte     | Variador de Frecuencia VF-3 | 18      | 781.2        | 14061.6       | 10080       | 3981.6     |
| Octubre   | Carlos Ruiz       | Sur       | Reductor de Velocidad RV-7 | 60       | 290          | 17400         | 11700       | 5700       |
| Noviembre | Ana Martínez      | Norte     | Válvula Industrial V-200   | 95       | 140          | 13300         | 9025        | 4275       |
| Noviembre | Carlos Ruiz       | Sur       | Sensor de Presión SP-50    | 52       | 299.25       | 15561         | 10920       | 4641       |
| Noviembre | Laura Gómez       | Centro    | Filtro Industrial FI-300   | 180      | 90           | 16200         | 10800       | 5400       |
| Noviembre | Pedro Sánchez     | Este      | Bomba Centrífuga BC-10     | 25       | 567          | 14175         | 11250       | 2925       |
| Noviembre | Ana Martínez      | Norte     | Rodamiento de Precisión RP-22 | 420   | 55           | 23100         | 14700       | 8400       |
| Noviembre | Carlos Ruiz       | Sur       | Compresor Compacto CC-5    | 15       | 1012         | 15180         | 11700       | 3480       |
| Noviembre | Laura Gómez       | Centro    | Actuador Eléctrico AE-15   | 40       | 422.4        | 16896         | 12800       | 4096       |
| Noviembre | Pedro Sánchez     | Este      | Manguera Hidráulica MH-8   | 500      | 42.75        | 21375         | 14000       | 7375       |
| Noviembre | Ana Martínez      | Norte     | Variador de Frecuencia VF-3 | 22      | 781.2        | 17186.4       | 12320       | 4866.4     |
| Noviembre | Carlos Ruiz       | Sur       | Reductor de Velocidad RV-7 | 75       | 290          | 21750         | 14625       | 7125       |

> 💾 **Importante:** Guarda el archivo inmediatamente en OneDrive (`Ctrl + S`). Verifica que la barra de título muestre el ícono de OneDrive (nube) y no una ruta local.

---

## Pasos del Laboratorio

### Bloque 1: Simulación de Escenarios de Precios en Excel (35 minutos)

---

#### Paso 1 — Preparar la Hoja de Simulación de Escenarios

**Objetivo:** Crear una hoja dedicada en Excel para la simulación de precios y agregar columnas de cálculo base que Copilot pueda analizar.

**Instrucciones:**

1. Abre el archivo `Lab04_Base_Ventas_Productos.xlsx` desde OneDrive.
2. Haz clic derecho en la pestaña de la hoja `Productos` y selecciona **Insertar hoja**. Nómbrala `Simulacion_Precios`.
3. En la hoja `Simulacion_Precios`, crea la siguiente tabla de encabezados comenzando en la celda `A1`:

```
A1: Producto
B1: Costo_Unitario
C1: Precio_Lista
D1: Margen_Base_%
E1: Precio_Desc_10%
F1: Margen_Desc_10%
G1: Precio_Desc_15%
H1: Margen_Desc_15%
I1: Precio_Desc_20%
J1: Margen_Desc_20%
K1: Ganancia_Total_SinDesc (100 uds)
L1: Ganancia_Total_Desc15% (100 uds)
```

4. Copia los datos de Nombre_Producto, Costo_Unitario y Precio_Lista desde la hoja `Productos` a las columnas A, B y C de `Simulacion_Precios` (10 filas de datos, comenzando en fila 2).

5. Ingresa las siguientes fórmulas para los primeros cálculos base (fila 2, luego extiende hasta fila 11):

```excel
D2: =((C2-B2)/C2)*100          → Margen base porcentual
E2: =C2*(1-0.10)               → Precio con descuento 10%
F2: =((E2-B2)/E2)*100          → Margen con descuento 10%
G2: =C2*(1-0.15)               → Precio con descuento 15%
H2: =((G2-B2)/G2)*100          → Margen con descuento 15%
I2: =C2*(1-0.20)               → Precio con descuento 20%
J2: =((I2-B2)/I2)*100          → Margen con descuento 20%
K2: =(C2-B2)*100               → Ganancia total sin descuento (100 unidades)
L2: =(G2-B2)*100               → Ganancia total con 15% descuento (100 unidades)
```

6. Selecciona el rango `A1:L11` y convierte los datos en una tabla de Excel: ve a **Insertar → Tabla** → marca "La tabla tiene encabezados" → **Aceptar**. Nombra la tabla `TSimulacion` desde el campo **Nombre de tabla** en la cinta de opciones.

7. Guarda el archivo (`Ctrl + S`).

**Resultado esperado:** Una tabla estructurada con 10 productos y 12 columnas de datos que incluye precios base, precios con descuento del 10%, 15% y 20%, márgenes resultantes y ganancias totales estimadas para 100 unidades.

**Verificación:** Confirma que la celda `D2` muestre aproximadamente `32.14%` para el producto P001 (Válvula Industrial V-200 con costo $95 y precio $140). Si el valor es diferente, revisa la fórmula en D2.

---

#### Paso 2 — Activar Copilot en Excel y Realizar Análisis de Escenarios

**Objetivo:** Utilizar Copilot en Excel para analizar la tabla de simulación mediante preguntas en lenguaje natural e identificar los escenarios de precio más favorables.

**Instrucciones:**

1. Con el archivo `Lab04_Base_Ventas_Productos.xlsx` abierto en la hoja `Simulacion_Precios`, activa el panel de Copilot haciendo clic en el botón **Copilot** en la cinta de opciones (pestaña **Inicio** → grupo **Copilot**), o presiona el ícono de Copilot en la barra de herramientas.

   > 💡 **Nota:** Si el botón Copilot no aparece, verifica que el archivo esté guardado en OneDrive (no localmente) y que tu licencia Copilot esté activa.

2. En el panel de Copilot que aparece a la derecha, escribe el siguiente prompt:

```text
Analiza la tabla TSimulacion. ¿Qué producto tiene el mejor margen 
base porcentual? ¿Y cuál tiene el margen más bajo? Muestra los 
resultados ordenados de mayor a menor margen base.
```

3. Revisa la respuesta de Copilot. Toma nota de los productos con mayor y menor margen base.

4. Escribe el siguiente prompt para analizar el impacto de descuentos:

```text
¿Cómo afecta un descuento del 15% al margen total de todos los productos 
en la tabla? Identifica qué productos mantienen un margen saludable 
(superior al 20%) después del descuento del 15% y cuáles caen por 
debajo de ese umbral.
```

5. Revisa la respuesta. Copilot identificará los productos que pueden soportar el descuento del 15% sin comprometer la rentabilidad mínima.

6. Escribe el siguiente prompt para obtener una recomendación estratégica:

```text
Basándote en los datos de la tabla TSimulacion, recomienda una 
estrategia de descuentos diferenciada por producto. Considera que 
el margen mínimo aceptable es del 18%. ¿Para cuáles productos 
es viable ofrecer un 20% de descuento? ¿Para cuáles solo es 
viable el 10%? Presenta la recomendación en formato de tabla.
```

7. Solicita a Copilot que genere una gráfica de comparación:

```text
Crea un gráfico de barras agrupadas que compare el margen base, 
el margen con descuento del 10%, del 15% y del 20% para todos 
los productos de la tabla. Usa los nombres de producto en el eje X.
```

8. Acepta la gráfica generada por Copilot y reubícala debajo de la tabla de datos.

9. Guarda el archivo (`Ctrl + S`).

**Resultado esperado:** El panel de Copilot habrá respondido a las cuatro preguntas con análisis claros. La hoja `Simulacion_Precios` ahora incluye la tabla de datos más un gráfico de barras agrupadas que visualiza la sensibilidad de margen por producto y nivel de descuento.

**Verificación:** Confirma que el gráfico muestre 4 series de datos (margen base, margen 10%, margen 15%, margen 20%) con los 10 productos en el eje X. Verifica que Copilot haya identificado correctamente al menos 2 productos donde el descuento del 20% lleva el margen por debajo del 18%.

---

#### Paso 3 — Simulación de Escenarios con Producto Específico (Análisis de Cliente)

**Objetivo:** Aplicar el proceso de simulación de precios aprendido en la Lección 4.1 para preparar una propuesta comercial con tres escenarios diferenciados para un cliente específico.

**Instrucciones:**

1. Agrega una nueva hoja al libro y nómbrala `Propuesta_Cliente`.

2. En la hoja `Propuesta_Cliente`, crea el encabezado del caso de negocio:

```
A1: SIMULACIÓN DE PRECIO - PROPUESTA COMERCIAL
A2: Cliente: Industrias Metálicas del Norte S.A.
A3: Producto: Bomba Centrífuga BC-10
A4: Volúmenes evaluados: 50, 100 y 200 unidades
A5: Fecha: [fecha actual]
```

3. Crea la siguiente tabla de escenarios comenzando en `A7`:

```
A7: Escenario
B7: Descripción
C7: Volumen (uds)
D7: Descuento
E7: Precio_Unitario_Final
F7: Margen_%
G7: Ingreso_Total
H7: Ganancia_Total
I7: Recomendación_Uso
```

4. Ingresa los datos base de los tres escenarios (filas 8, 9 y 10):

```
A8: Escenario A | B8: Precio estándar | C8: 50  | D8: 0%
A9: Escenario B | B9: Descuento volumen | C9: 100 | D9: 12%
A10: Escenario C | B10: Desc. + pago 30d | C10: 200 | D10: 18%
```

5. Ingresa las fórmulas de cálculo (el costo base de la Bomba BC-10 es $450, precio de lista $630):

```excel
E8: =630*(1-D8)       → Para Escenario A: =630*(1-0)    = 630
E9: =630*(1-0.12)                                        = 554.4
E10: =630*(1-0.18)                                       = 516.6

F8: =((E8-450)/E8)*100
F9: =((E9-450)/E9)*100
F10: =((E10-450)/E10)*100

G8: =E8*C8
G9: =E9*C9
G10: =E10*C10

H8: =(E8-450)*C8
H9: =(E9-450)*C9
H10: =(E10-450)*C10
```

6. Selecciona el rango `A7:I10` y conviértelo en tabla. Nómbrala `TPropuesta`.

7. En el panel de Copilot, escribe el siguiente prompt (basado en el ejemplo de la Lección 4.1):

```text
Analiza la tabla TPropuesta con los tres escenarios de precio para 
la Bomba Centrífuga BC-10. Para cada escenario indica:
- ¿Es el margen resultante aceptable (mínimo 18%)?
- ¿Cuál es la ganancia total generada?
- ¿Cuál escenario recomendarías presentar primero al cliente y por qué?
Incluye una recomendación de estrategia de negociación: cuál escenario 
usar como oferta inicial, cuál como concesión y cuál como referencia.
```

8. Copia la respuesta de Copilot y pégala como texto en las celdas de la columna `I` (columna Recomendación_Uso) o en un cuadro de texto debajo de la tabla.

9. Solicita a Copilot que genere un gráfico de columnas comparando la ganancia total por escenario:

```text
Crea un gráfico de columnas que compare la Ganancia_Total de los 
tres escenarios en la tabla TPropuesta. Etiqueta cada columna con 
el nombre del escenario y el valor de ganancia total.
```

10. Guarda el archivo (`Ctrl + S`).

**Resultado esperado:** La hoja `Propuesta_Cliente` contiene una tabla de tres escenarios con todos los cálculos completados, la recomendación de estrategia generada por Copilot y un gráfico de columnas comparativo. Los márgenes calculados deben ser aproximadamente: Escenario A = 28.57%, Escenario B = 18.85%, Escenario C = 12.93%.

**Verificación:** Confirma que el Escenario C (18% de descuento) muestre un margen inferior al 18% mínimo aceptable (~12.93%). Copilot debería haber señalado esto en su recomendación y sugerido el Escenario B como oferta principal.

---

### Bloque 2: Automatización de Reportes de Ventas (40 minutos)

---

#### Paso 4 — Analizar Datos de Ventas con Copilot en Excel

**Objetivo:** Utilizar Copilot en Excel para analizar los datos de ventas mensuales y extraer tendencias, métricas clave y áreas de mejora que servirán como base para el reporte ejecutivo.

**Instrucciones:**

1. En el mismo archivo Excel, navega a la hoja `Ventas_Mensuales`.

2. Convierte el rango de datos en una tabla de Excel: selecciona `A1:I21` → **Insertar → Tabla** → confirma encabezados → **Aceptar**. Nombra la tabla `TVentas`.

3. Activa el panel de Copilot (si no está abierto) y escribe el siguiente prompt:

```text
Analiza la tabla TVentas que contiene datos de ventas de octubre 
y noviembre. Calcula y muestra:
1. Ingreso total y utilidad total por mes (octubre vs noviembre)
2. Vendedor con mayor ingreso total acumulado en ambos meses
3. Producto más vendido por ingreso total
4. Región con mejor desempeño
5. Variación porcentual del ingreso total entre octubre y noviembre
Presenta los resultados en formato de tabla resumen.
```

4. Revisa la respuesta de Copilot. Verifica que los cálculos sean coherentes con los datos.

5. Escribe el siguiente prompt para análisis de tendencias:

```text
¿Qué tendencias observas en los datos de ventas entre octubre y 
noviembre? Identifica:
- Productos con crecimiento en unidades vendidas
- Vendedores que mejoraron su desempeño
- Áreas de oportunidad o productos con caída en ventas
- Una recomendación accionable para el equipo de ventas basada en estos datos
```

6. Solicita a Copilot que cree una visualización de desempeño por vendedor:

```text
Crea un gráfico de barras apiladas que muestre el Ingreso_Total 
por Vendedor, separando octubre y noviembre como dos series. 
Incluye el título "Desempeño de Ventas por Vendedor - Oct/Nov".
```

7. Acepta el gráfico y reubícalo en la hoja `Ventas_Mensuales`.

8. Escribe un prompt adicional para análisis de rentabilidad:

```text
Calcula el margen de utilidad porcentual promedio por vendedor 
(Utilidad/Ingreso_Total × 100) para el período completo. 
¿Hay diferencias significativas entre vendedores en términos 
de rentabilidad? Muestra los resultados ordenados de mayor a menor.
```

9. Guarda el archivo (`Ctrl + S`).

10. **Captura o copia** las respuestas clave de Copilot (resumen de métricas, tendencias y recomendaciones) en un documento de texto temporal o en el bloc de notas; las usarás en el siguiente paso para el reporte en Word.

**Resultado esperado:** La hoja `Ventas_Mensuales` incluye la tabla de datos estructurada, un gráfico de barras apiladas por vendedor, y el panel de Copilot ha generado análisis de tendencias, métricas comparativas y recomendaciones accionables. El ingreso total de noviembre debe ser superior al de octubre (tendencia de crecimiento en los datos de ejemplo).

**Verificación:** Confirma que Copilot identifique a Ana Martínez como la vendedora con mayor volumen acumulado (aparece en 6 registros de los 20 totales). El ingreso total del período completo debe ser aproximadamente $371,018.25.

---

#### Paso 5 — Crear el Reporte Ejecutivo de Ventas en Word con Copilot

**Objetivo:** Generar un reporte formal de ventas en Word utilizando Copilot para estructurar el contenido, redactar secciones ejecutivas y formatear el documento de manera profesional.

**Instrucciones:**

1. Abre **Microsoft Word** desde Microsoft 365. Crea un nuevo documento en blanco.

2. Guarda el documento inmediatamente en OneDrive con el nombre:

```
Lab04_Reporte_Ventas_OctNov.docx
```

   Ruta: `OneDrive/Curso_Copilot_Ventas/Practica_4/`

3. Activa Copilot en Word haciendo clic en el ícono de Copilot en la cinta de opciones (**Inicio → Copilot**) o usando el botón **Borrador con Copilot** que aparece al inicio del documento en blanco.

4. En el panel de Copilot o en el área de borrador, escribe el siguiente prompt:

```text
Crea un reporte ejecutivo de ventas con la siguiente estructura 
y contenido:

TÍTULO: Reporte de Desempeño Comercial — Octubre y Noviembre 2024
EMPRESA: Suministros Industriales Avanzados S.A. de C.V.

Secciones requeridas:
1. Resumen Ejecutivo (3-4 párrafos): El equipo de ventas registró 
   un ingreso total de $141,811 en octubre y $185,348 en noviembre, 
   representando un crecimiento del 30.7%. La utilidad total pasó 
   de $42,405 en octubre a $58,659 en noviembre. Ana Martínez fue 
   la vendedora de mayor desempeño con $79,648 en ingresos totales.

2. Análisis por Vendedor: Incluir tabla con los 4 vendedores 
   (Ana Martínez, Carlos Ruiz, Laura Gómez, Pedro Sánchez), 
   sus ingresos totales acumulados y margen de utilidad promedio.

3. Productos Destacados: Mencionar los 3 productos con mayor 
   ingreso total: Manguera Hidráulica MH-8 ($38,475), 
   Rodamiento de Precisión RP-22 ($39,600) y 
   Reductor de Velocidad RV-7 ($39,150).

4. Tendencias y Hallazgos Clave: Crecimiento consistente en 
   todos los vendedores entre octubre y noviembre. La región Norte 
   lidera en ingresos. Los productos de la categoría Mecánica 
   representan el mayor volumen de ventas.

5. Recomendaciones Estratégicas: Al menos 3 recomendaciones 
   accionables para el equipo de ventas basadas en los datos.

6. Próximos Pasos: Acciones concretas para diciembre.

Usa un tono ejecutivo y profesional. Incluye viñetas donde sea 
apropiado. El reporte debe ser claro y directo para una audiencia 
de gerencia media y alta dirección.
```

5. Revisa el borrador generado por Copilot. Realiza ajustes de contenido si es necesario (corrección de datos, ajuste de tono).

6. Solicita a Copilot que mejore el resumen ejecutivo:

```text
Reescribe el Resumen Ejecutivo para que sea más impactante. 
Comienza con el dato de crecimiento más relevante y usa 
lenguaje orientado a resultados. Máximo 150 palabras.
```

7. Aplica formato profesional al documento:
   - Título principal: Estilo **Título** (Heading 1)
   - Secciones: Estilo **Título 2** (Heading 2)
   - Tabla de vendedores: Estilo de tabla **Cuadrícula de tabla 4**
   - Márgenes: Normal (2.54 cm todos los lados)
   - Fuente del cuerpo: Calibri 11pt

8. Inserta un pie de página con el texto:

```
Confidencial — Suministros Industriales Avanzados S.A. de C.V. | Uso interno
```

9. Guarda el documento (`Ctrl + S`) y verifica que se guarde en OneDrive.

**Resultado esperado:** Un documento Word de 3-5 páginas con estructura ejecutiva profesional, que incluye resumen ejecutivo, análisis por vendedor con tabla, sección de productos destacados, tendencias y al menos 3 recomendaciones estratégicas. El documento debe estar formateado con estilos de título coherentes y pie de página corporativo.

**Verificación:** Confirma que el documento tiene al menos las 6 secciones indicadas, que la tabla de vendedores está presente y formateada, y que el pie de página aparece en todas las páginas. El conteo de palabras debe ser de al menos 400 palabras.

---

#### Paso 6 — Crear la Presentación Ejecutiva en PowerPoint con Copilot

**Objetivo:** Transformar el reporte de ventas en una presentación ejecutiva de PowerPoint utilizando Copilot para generar diapositivas estructuradas y visuales.

**Instrucciones:**

1. Abre **Microsoft PowerPoint** desde Microsoft 365. Crea una nueva presentación en blanco.

2. Guarda la presentación inmediatamente en OneDrive:

```
Lab04_Presentacion_Ventas_OctNov.pptx
```

   Ruta: `OneDrive/Curso_Copilot_Ventas/Practica_4/`

3. Activa Copilot en PowerPoint: haz clic en el ícono **Copilot** en la cinta de opciones (**Inicio → Copilot**).

4. En el panel de Copilot, escribe el siguiente prompt:

```text
Crea una presentación ejecutiva de ventas con las siguientes 
diapositivas:

Diapositiva 1 — Portada:
Título: "Resultados Comerciales Q4 2024"
Subtítulo: "Octubre – Noviembre | Suministros Industriales Avanzados"

Diapositiva 2 — Resumen de Resultados:
Métricas clave en formato de tarjetas:
• Ingreso Total: $327,159
• Crecimiento MoM: +30.7%
• Utilidad Total: $101,064
• Vendedores activos: 4

Diapositiva 3 — Desempeño por Vendedor:
Tabla comparativa con: Ana Martínez, Carlos Ruiz, Laura Gómez, 
Pedro Sánchez y sus ingresos acumulados.

Diapositiva 4 — Productos Más Rentables:
Top 3 productos por ingreso total con íconos o gráfico.

Diapositiva 5 — Tendencias Clave:
3-4 puntos de tendencia identificados en el período.

Diapositiva 6 — Recomendaciones Estratégicas:
3 recomendaciones accionables para diciembre.

Diapositiva 7 — Próximos Pasos:
Lista de acciones concretas con responsables sugeridos.

Usa un diseño profesional, moderno y consistente. 
Tema de color: azul corporativo.
```

5. Revisa las diapositivas generadas. Ajusta el contenido de texto si es necesario.

6. Solicita a Copilot que mejore una diapositiva específica:

```text
Mejora la diapositiva de Recomendaciones Estratégicas. 
Agrega una justificación breve (1 oración) para cada recomendación 
basada en los datos de ventas de octubre y noviembre. 
Usa formato de lista con viñetas y sub-viñetas.
```

7. Aplica un tema de diseño profesional: ve a **Diseño → Temas** y selecciona un tema corporativo (por ejemplo, "Faceta" o "Integral").

8. Verifica que todas las diapositivas tengan:
   - Título visible y legible
   - Contenido alineado y sin desbordamiento de texto
   - Numeración de diapositivas en el pie

9. Guarda la presentación (`Ctrl + S`).

**Resultado esperado:** Una presentación de 7 diapositivas con diseño profesional y consistente, que cubre portada, métricas clave, desempeño por vendedor, productos destacados, tendencias, recomendaciones y próximos pasos. La presentación debe ser coherente con el reporte Word generado en el paso anterior.

**Verificación:** Confirma que las 7 diapositivas están presentes y que la diapositiva de Resumen de Resultados muestra las 4 métricas clave en formato destacado. Verifica que el tema de color aplicado sea consistente en todas las diapositivas.

---

### Bloque 3: Ejercicio Integrador Final — Portafolio de Ventas (25 minutos)

---

#### Paso 7 — Consolidar el Portafolio de Ventas con Copilot Chat

**Objetivo:** Utilizar Copilot Chat para generar un resumen integrador del ciclo de ventas completo, conectando los entregables de las 4 prácticas del curso en un mensaje ejecutivo coherente.

**Instrucciones:**

1. Abre **Copilot Chat** desde el navegador: ve a [microsoft365.com/copilot](https://microsoft365.com/copilot) o accede desde Microsoft Teams → **Copilot**.

2. Verifica que estás en la interfaz de Copilot Chat con acceso a los archivos de Microsoft 365 (modo "Trabajo" si está disponible).

3. Escribe el siguiente prompt de investigación y síntesis:

```text
Actúa como un consultor de ventas senior. Necesito un resumen 
ejecutivo de 300-400 palabras que describa el ciclo completo 
de una oportunidad de ventas para una empresa de suministros 
industriales. El ciclo debe cubrir estas 4 etapas:

1. INVESTIGACIÓN: Análisis de competidores e identificación 
   del cliente potencial (Industrias Metálicas del Norte S.A.)
   
2. COMUNICACIÓN COMERCIAL: Propuesta de valor y catálogo 
   de productos enviado al cliente (Bombas, Válvulas, Sensores)
   
3. COTIZACIÓN: Propuesta con 3 escenarios de precio para 
   la Bomba Centrífuga BC-10 (sin descuento, 12% y 18%)
   
4. REPORTE Y SEGUIMIENTO: Resultados de ventas de octubre 
   y noviembre con crecimiento del 30.7%

El resumen debe estar redactado como un caso de éxito comercial 
que podría presentarse a la dirección general. Incluye métricas 
clave, lecciones aprendidas y el valor que Copilot aportó 
en cada etapa del proceso.
```

4. Revisa la respuesta de Copilot Chat. Solicita ajustes si el tono o el contenido no son adecuados:

```text
Ajusta el tono para que sea más orientado a resultados y menos 
descriptivo. Agrega al inicio una frase de impacto que resuma 
el valor total del ciclo de ventas en términos de ingreso generado 
o eficiencia lograda. Mantén el formato de 4 secciones.
```

5. Copia el texto generado por Copilot Chat.

6. Abre el archivo Word `Lab04_Reporte_Ventas_OctNov.docx` desde OneDrive.

7. Agrega una nueva sección al final del documento titulada **"Caso de Éxito: Ciclo Completo de Ventas con Microsoft 365 Copilot"** y pega el texto generado por Copilot Chat.

8. Aplica el estilo **Título 2** al encabezado de la nueva sección y ajusta el formato del texto pegado para que sea consistente con el resto del documento (fuente Calibri 11pt, interlineado 1.15).

9. Guarda el documento Word actualizado (`Ctrl + S`).

**Resultado esperado:** El documento Word ahora incluye una sección final de caso de éxito que integra las 4 etapas del ciclo de ventas con métricas clave, redactada en tono ejecutivo y generada con apoyo de Copilot Chat.

**Verificación:** Confirma que la nueva sección tiene el encabezado correcto con estilo Título 2, que el texto tiene al menos 300 palabras y que menciona explícitamente las 4 etapas del ciclo de ventas.

---

#### Paso 8 — Revisión Final y Verificación del Portafolio

**Objetivo:** Verificar que todos los entregables de la práctica están completos, correctamente guardados en OneDrive y listos para presentación.

**Instrucciones:**

1. Abre OneDrive desde el navegador y navega a la carpeta `Curso_Copilot_Ventas/Practica_4/`.

2. Verifica que los siguientes archivos estén presentes y accesibles:

```
Practica_4/
├── Lab04_Base_Ventas_Productos.xlsx
│   ├── Hoja: Productos
│   ├── Hoja: Ventas_Mensuales
│   ├── Hoja: Simulacion_Precios (con tabla TSimulacion y gráfico)
│   └── Hoja: Propuesta_Cliente (con tabla TPropuesta y gráfico)
├── Lab04_Reporte_Ventas_OctNov.docx
│   ├── 6 secciones del reporte ejecutivo
│   └── Sección: Caso de Éxito (Paso 7)
└── Lab04_Presentacion_Ventas_OctNov.pptx
    └── 7 diapositivas con diseño profesional
```

3. Abre cada archivo y realiza una revisión rápida de calidad:

   **Para el archivo Excel:**
   - Verifica que la hoja `Simulacion_Precios` tenga el gráfico de barras agrupadas generado por Copilot.
   - Confirma que la hoja `Propuesta_Cliente` muestre los 3 escenarios con todos los cálculos y el gráfico de columnas.

   **Para el documento Word:**
   - Confirma que tiene al menos 7 secciones (6 originales + caso de éxito).
   - Verifica que el pie de página "Confidencial" aparece en todas las páginas.
   - Revisa que la tabla de vendedores esté presente y formateada.

   **Para la presentación PowerPoint:**
   - Confirma que tiene exactamente 7 diapositivas.
   - Verifica que el tema de diseño sea consistente en todas las diapositivas.
   - Comprueba que la diapositiva de portada muestra el título y subtítulo correctos.

4. Si algún archivo tiene deficiencias, regresa al paso correspondiente y completa el trabajo faltante.

5. Como paso final, abre Copilot Chat y escribe el siguiente prompt de reflexión:

```text
He completado un ciclo de ventas completo utilizando Microsoft 365 
Copilot en 4 etapas: investigación, comunicación, cotización y reportes. 
Dame 5 recomendaciones específicas para maximizar el uso de Copilot 
en mi trabajo diario de ventas, basadas en las capacidades que 
hemos utilizado en este ejercicio. Sé concreto y práctico.
```

6. Lee las recomendaciones y reflexiona sobre cuáles aplicarás en tu trabajo real.

**Resultado esperado:** Los tres archivos del portafolio están completos, correctamente guardados en OneDrive y verificados. El participante cuenta con un portafolio integrado que demuestra el uso de Copilot en todo el ciclo de ventas.

**Verificación:** Confirma que puedes abrir cada archivo directamente desde OneDrive en el navegador (sin necesidad de descargarlo). Verifica que los archivos muestren el ícono de sincronización completada (✓ verde) en OneDrive.

---

## Validación y Pruebas

Al finalizar el laboratorio, ejecuta la siguiente lista de verificación completa para confirmar que todos los objetivos han sido alcanzados:

### Lista de Verificación de Entregables

| # | Entregable / Criterio de Validación | Archivo | ✓ |
|---|--------------------------------------|---------|---|
| 1 | Hoja `Simulacion_Precios` con tabla TSimulacion (10 productos, 12 columnas) | Excel | ☐ |
| 2 | Gráfico de barras agrupadas de márgenes por nivel de descuento | Excel | ☐ |
| 3 | Hoja `Propuesta_Cliente` con 3 escenarios de precio para Bomba BC-10 | Excel | ☐ |
| 4 | Gráfico de columnas comparando ganancia total por escenario | Excel | ☐ |
| 5 | Análisis de Copilot indicando que Escenario C cae por debajo del margen mínimo | Excel | ☐ |
| 6 | Hoja `Ventas_Mensuales` con tabla TVentas y gráfico de barras apiladas por vendedor | Excel | ☐ |
| 7 | Reporte Word con 6+ secciones ejecutivas y tabla de vendedores | Word | ☐ |
| 8 | Sección de Caso de Éxito integrador en el reporte Word | Word | ☐ |
| 9 | Presentación PowerPoint con 7 diapositivas y diseño profesional consistente | PowerPoint | ☐ |
| 10 | Todos los archivos guardados en `OneDrive/Curso_Copilot_Ventas/Practica_4/` | OneDrive | ☐ |

### Prueba de Funcionalidad de Copilot

Para confirmar que Copilot funcionó correctamente durante la práctica, verifica que:

1. **En Excel:** Las respuestas de Copilot al prompt del Paso 2 (análisis de margen) identificaron correctamente los productos con margen superior e inferior.
2. **En Excel:** Copilot generó al menos 2 gráficos (uno en `Simulacion_Precios` y uno en `Propuesta_Cliente`) sin errores.
3. **En Word:** El borrador generado por Copilot en el Paso 5 tiene estructura de 6 secciones coherentes con los datos de ventas proporcionados.
4. **En PowerPoint:** Las 7 diapositivas generadas en el Paso 6 tienen contenido relevante y no están vacías.
5. **En Copilot Chat:** El resumen del ciclo de ventas del Paso 7 menciona las 4 etapas y al menos 2 métricas numéricas específicas.

---

## Solución de Problemas

### Problema 1: Copilot en Excel no responde o el botón no está disponible

**Síntoma:** El botón de Copilot en la cinta de opciones de Excel aparece deshabilitado (en gris), o al hacer clic no se abre el panel lateral. Puede aparecer el mensaje: "Copilot no está disponible para este archivo."

**Causa:** Este problema ocurre cuando el archivo de Excel está guardado localmente en el disco duro del equipo en lugar de en OneDrive for Business o SharePoint. Copilot en las aplicaciones de Microsoft 365 requiere que el archivo esté almacenado en la nube para funcionar. También puede ocurrir si la tabla de datos no está formateada como tabla de Excel (objeto Table), ya que Copilot en Excel requiere datos estructurados en formato de tabla para realizar análisis.

**Solución:**
1. Verifica la ubicación del archivo: revisa la barra de título. Si muestra una ruta local como `C:\Users\...`, el archivo no está en OneDrive.
2. Guarda el archivo en OneDrive: ve a **Archivo → Guardar una copia → OneDrive** y selecciona la carpeta `Curso_Copilot_Ventas/Practica_4/`. Cierra el archivo local y abre la versión de OneDrive.
3. Si el archivo ya está en OneDrive pero Copilot sigue deshabilitado, verifica que los datos estén en formato de tabla: selecciona el rango de datos → **Insertar → Tabla**. Copilot requiere al menos una tabla de Excel para activarse.
4. Si el problema persiste, cierra y vuelve a abrir Excel, o intenta desde el navegador en [microsoft365.com](https://microsoft365.com) → Excel Online, donde Copilot también está disponible.

---

### Problema 2: Copilot genera una tabla de escenarios con cálculos incorrectos o datos inconsistentes con los ingresados en el prompt

**Síntoma:** Al solicitar a Copilot Chat (en el Paso 3 o en el Bloque 1) que calcule precios finales, márgenes o ganancias totales, los valores en la tabla de respuesta no coinciden con los cálculos manuales esperados. Por ejemplo, el margen del Escenario B aparece como 25% en lugar del ~18.85% correcto.

**Causa:** Copilot Chat es un modelo de lenguaje y puede cometer errores aritméticos, especialmente cuando el prompt incluye múltiples variables numéricas simultáneas o cuando la instrucción de la fórmula es ambigua. Un error frecuente es la confusión entre "margen sobre precio" (fórmula: (Precio-Costo)/Precio) y "margen sobre costo" (fórmula: (Precio-Costo)/Costo), que producen valores diferentes. También puede ocurrir si el prompt no especifica claramente la base de cálculo del margen.

**Solución:**
1. Verifica los cálculos manualmente usando las fórmulas de Excel ingresadas en el Paso 1 y el Paso 3. Los valores de Excel son la fuente de verdad; Copilot Chat es una herramienta de análisis e interpretación, no de cálculo primario.
2. Si detectas un error, refina el prompt especificando explícitamente la fórmula: `"El margen porcentual se calcula como: ((Precio_Final - Costo_Unitario) / Precio_Final) × 100"`.
3. Ejemplo de prompt corregido: `"Usando la fórmula de margen = ((Precio_Final - Costo) / Precio_Final) × 100, donde el costo es $450 y el precio de lista es $630, calcula el margen para un descuento del 12%."` Esto reduce la ambigüedad y mejora la precisión del resultado.
4. Para cálculos críticos de negocio, siempre valida los números de Copilot Chat contra las fórmulas de Excel antes de presentarlos a un cliente o directivo.

---

## Limpieza del Entorno

Al finalizar el laboratorio, realiza las siguientes acciones para mantener el entorno ordenado:

1. **Cierra todos los archivos abiertos** (Excel, Word, PowerPoint) guardando los cambios finales con `Ctrl + S` en cada uno.

2. **Verifica la sincronización de OneDrive:** Asegúrate de que el ícono de OneDrive en la barra de tareas muestre el estado "Sincronizado" (ícono de nube con paloma ✓). Si hay archivos pendientes de sincronizar, espera a que el proceso termine antes de cerrar sesión.

3. **Organiza la carpeta de entregables en OneDrive:** Confirma que los tres archivos del portafolio están en `OneDrive/Curso_Copilot_Ventas/Practica_4/` y que no hay archivos duplicados o versiones temporales.

4. **Cierra Copilot Chat:** Cierra la pestaña del navegador con Copilot Chat o el panel de Copilot en Teams.

5. **No elimines ningún archivo:** Los entregables de esta práctica forman parte del portafolio final del curso y pueden ser revisados por el instructor. Mantén todos los archivos en OneDrive hasta recibir indicación de lo contrario.

6. **Opcional — Compartir entregables con el instructor:** Si el instructor lo solicita, comparte la carpeta `Practica_4` desde OneDrive: clic derecho en la carpeta → **Compartir** → ingresa el correo del instructor → **Enviar**. Asegúrate de otorgar permisos de "Solo visualización".

---

## Resumen

### Lo que Aprendiste en Este Laboratorio

En esta práctica de cierre aplicaste un conjunto completo de capacidades de Microsoft 365 Copilot para resolver un caso de ventas integral. Los logros principales fueron:

- **Simulación de escenarios de precios:** Construiste una tabla de análisis what-if en Excel con 10 productos y 3 niveles de descuento, identificando mediante Copilot qué productos pueden soportar descuentos agresivos sin comprometer la rentabilidad mínima del 18%.

- **Propuesta comercial con escenarios diferenciados:** Aplicaste la metodología de la Lección 4.1 para preparar una propuesta de 3 escenarios (Escenario A: sin descuento / Escenario B: 12% / Escenario C: 18%) para la Bomba Centrífuga BC-10, con recomendación de estrategia de negociación generada por Copilot.

- **Análisis de datos de ventas con lenguaje natural:** Utilizaste Copilot en Excel para extraer tendencias, métricas comparativas y recomendaciones accionables de un conjunto de 20 registros de ventas de dos meses, sin necesidad de fórmulas complejas ni tablas dinámicas manuales.

- **Automatización de reportes ejecutivos:** Generaste un reporte formal de ventas en Word y una presentación ejecutiva de 7 diapositivas en PowerPoint, ambos estructurados y redactados con apoyo de Copilot, en una fracción del tiempo que tomaría hacerlo manualmente.

- **Portafolio integrado de ventas:** Consolidaste los entregables de las 4 prácticas del curso en un caso de éxito coherente, demostrando el valor de Copilot en cada etapa del ciclo comercial.

### Conexión con el Ciclo de Ventas Completo

| Práctica | Etapa del Ciclo | Herramienta Principal |
|----------|-----------------|-----------------------|
| Práctica 1 | Investigación de mercado y competidores | Copilot Chat |
| Práctica 2 | Comunicación comercial y catálogo | Word + PowerPoint con Copilot |
| Práctica 3 | Cotización automatizada con agente | Copilot Studio / Agentes |
| **Práctica 4** | **Simulación de precios y reportes** | **Excel + Word + PowerPoint + Copilot Chat** |

### Recursos Adicionales

- [Documentación oficial: Copilot en Excel](https://support.microsoft.com/es-es/office/copilot-en-excel-d7110502-0334-4b4f-a175-a73abdfc118a)
- [Documentación oficial: Copilot en Word](https://support.microsoft.com/es-es/office/copilot-en-word-b3a5d9f0-3e7a-4e8e-a8e6-2d7e7a7a7a7a)
- [Documentación oficial: Copilot en PowerPoint](https://support.microsoft.com/es-es/office/copilot-en-powerpoint)
- [Guía de prompts efectivos para Microsoft 365 Copilot](https://adoption.microsoft.com/es-es/copilot/)
- [Fundamentos de estrategia de precios — Harvard Business Review](https://hbr.org/2018/09/the-good-better-best-approach-to-pricing)
- [Recursos de capacitación Microsoft 365 Copilot para profesionales de ventas](https://learn.microsoft.com/es-es/training/paths/get-started-with-microsoft-365-copilot/)
- [Microsoft AI Blog — Análisis de escenarios financieros con IA](https://blogs.microsoft.com/ai/)

---

> 🎓 **¡Felicitaciones!** Has completado la Práctica 4 y el ciclo completo del curso. Tu portafolio en OneDrive contiene evidencia concreta del uso estratégico de Microsoft 365 Copilot en un proceso de ventas real, desde la investigación inicial hasta el reporte ejecutivo final.
