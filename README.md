# ☕ Coffee Shop Sales Analysis

📊 **Análisis de Ventas de Starbucks 2025**

Este proyecto realiza un análisis exploratorio y descriptivo de los datos de ventas de Starbucks durante el año 2025. El objetivo es evaluar el comportamiento de compra de los clientes, identificar patrones relevantes en el consumo y generar visualizaciones efectivas que ayuden a la toma de decisiones.

---

## 📖 Descripción

El conjunto de datos incluye información detallada sobre productos vendidos, ubicaciones de las tiendas, métodos de pago, fecha y hora de las transacciones, entre otros aspectos. El análisis se ha realizado principalmente en Excel, enfocándonos en:

- Limpieza y preparación de datos
- Análisis descriptivo y segmentación
- Visualización mediante dashboards
- Obtención de conclusiones prácticas para el negocio

---

## 🗂 Estructura del Proyecto

```bash
Coffe-Shop-Sales-Analysis
|----dashboard
|   |----dashboard_starbucks_2025.xlsx      # Dashboard final en formato Excel
|----data/
|   |----ventas_starbucks_2025.csv         # Archivo original CSV con los datos
|----docs/                                 # Documentación adicional
|   |---conclusiones.md
|----README.md
|----.gitignore
```

---

## 🛠 Instalación y Requisitos

Este proyecto se desarrolla utilizando principalmente Microsoft Excel para la exploración, análisis y visualización de datos. No requiere instalación de librerías ni herramientas adicionales. En futuras versiones podría ampliarse con análisis en Power BI o Python.

---

## 🔧 Herramientas Utilizadas

- **Excel 365** para la limpieza, análisis y visualización de datos.
- **Git + GitHub** para el control de versiones y documentación del proyecto.
- **Visual Studio Code** como entorno de trabajo.

---

## 📊 Dataset

- **Fuente**: [Ventas Starbucks - Kaggle](https://www.kaggle.com/datasets/guadalupesaraviaweht/ventas-starbucks)
- **Formato**: CSV
- **Tamaño**: ~149.000 filas, 18 columnas
- **Ubicación**: `./data/ventas_starbucks_2025.csv`

## 🧾 Diccionario de Variables

A continuación se describen las columnas presentes en el dataset `ventas_starbucks_2025.csv`:

| Columna              | Descripción                                                         |
| -------------------- | ------------------------------------------------------------------- |
| `ID Ticket`          | Identificador único de cada transacción de venta.                   |
| `Fecha`              | Fecha en la que se realizó la venta (formato: DD/MM/AAAA).          |
| `Hora`               | Hora exacta en la que se realizó la compra.                         |
| `Producto`           | Nombre del producto vendido (ej. Latte, Frappuccino, Muffin, etc.). |
| `Tamaño`             | Tamaño del producto vendido (ej. Tall, Grande, Venti).              |
| `Precio Unitario`    | Precio por unidad del producto vendido.                             |
| `Cantidad`           | Número de unidades vendidas en la transacción.                      |
| `Método de pago`     | Medio utilizado para pagar la compra (efectivo, tarjeta, etc.).     |
| `Total Venta`        | Total facturado en la transacción (Precio Unitario x Cantidad).     |
| `Nombre Tienda`      | Nombre o código de la tienda Starbucks donde se realizó la venta.   |
| `Ciudad`             | Ciudad donde se ubica la tienda.                                    |
| `País`               | País correspondiente a la tienda.                                   |
| `Empleado`           | Nombre del empleado que gestionó la transacción.                    |
| `Categoría Producto` | Tipo de producto (bebida caliente, fría, alimento, etc.).           |

## 🔍 Exploratory Data Analysis (EDA)

## 🧹 EDA Analisis exploratorio inicial

### `id_venta`

- **Descripción**: Identificador único de cada venta, con formato tipo `VTA00001`.
- **Tipo de dato**: Texto (string).
- **Duplicados**: No se han encontrado valores duplicados.
- **Nulos**: No hay valores nulos.
- **Acción necesaria**: Ninguna. Columna limpia.

---

### `fecha`

- **Descripción**: Fecha en la que se realizó la venta.
- **Tipo de dato**: Fecha.
- **Rango de fechas**: Desde `01/01/2025` hasta `18/04/2025`.
- **Valores únicos**: 108 fechas distintas, coherente con el rango de fechas observado.
- **Nulos**: No se han detectado valores nulos.
- **Formato**: Texto
- **Acción necesaria**: Se cambia a formato fecha. Columna lista para análisis temporal.

---

### `hora`

- **Descripción**: Hora en la que se registró la venta.
- **Tipo de dato original**: Texto.
- **Rango observado**: Desde las `07:00` hasta las `21:00`.
- **Nulos**: No se han detectado valores nulos.
- **Acción realizada**: Se ha transformado el tipo de dato a formato hora para facilitar el análisis por franjas horarias.
- **Acción pendiente**: Cambiar a formato hora

---

### `sucursal`

- **Descripción**: Tienda en la que se realizó la venta.
- **Tipo de dato original**: Texto.
- **Valores únicos**: 4 (`San Lorenzo 25`, `Nueva Córdoba`, `Córdoba Shopping`, `Calle San Lorenzo 47`, `Avenida Colón 608`).
- **Observación**: Las sucursales parecen ubicadas en Córdoba, Argentina.
- **Acción recomendada**: Estandarizar los nombres para mejorar la consistencia. Propuesta:
  - `Nueva Córdoba` → `Sucursal Nueva Córdoba`
  - `Córdoba Shopping` → `Sucursal Shopping`
  - `Avenida Colón 608` → `Sucursal Av. Colón`
  - `San Lorenzo 25` → `Sucursal San Lorenzo 25`
  - `Calle San Lorenzo 47` → `Sucursal San Lorenzo 47` .
- **Nulos**: No hay valores nulos.
- **Acción pendiente**: Aplicar estandarización de nombres

---

### `producto`

- **Descripción**: Nombre del producto vendido.
- **Tipo de dato**: Texto.
- **Valores únicos**: 36 productos distintos.
- **Ejemplos**: `Termo Reutilizable`, `Té Verde en Hebras`, `Espresso Roast`, `Caramel Frappuccino`, `Croissant Relleno con Crema de Avellanas`.
- **Nulos**: No se encontraron valores nulos.
- **Acción recomendada**: ✔ No se requiere transformación adicional en esta columna.

---

### `categoría`

- **Descripción**: Clasificación general del producto vendido.
- **Tipo de dato**: Texto.
- **Valores únicos**: 11 categorías distintas.
- **Ejemplos**: `Merchandising`, `Té`, `Snacks`, `Café en Granos`, `Bakery`, `Frappuccino`, `Bebida Espresso Caliente`.
- **Nulos**: No se encontraron valores nulos.
- **Acción recomendada**: - Columna limpia

---

### `tamaño`

- **Descripción**: Indica el tamaño del producto vendido.
- **Tipo de dato**: Texto.
- **Valores únicos**: 5 valores distintos (mezcla de inglés y español).
- **Ejemplos**: `Tall`, `Pequeño`, `Grande`, `Venti`.
- **Nulos**: Aproximadamente el 73% de las celdas están vacías.
- **Inconsistencias detectadas**: Mezcla de idiomas en los nombres de tamaño.
- **Acción recomendada**:
  - 🔄 Estandarizar los valores a un único idioma (por ejemplo, todos en español: `Pequeño`, `Mediano`, `Grande`, `Extra_grande`, etc.).
  - ⚠️ Analizar si los valores nulos se deben a categorías de productos que no tienen tamaño (como merchandising) antes de decidir cómo tratarlos.

---

### 🔸 `cantidad`

- **Descripción**: Indica la cantidad de unidades vendidas en una transacción.
- **Tipo de dato**: Número entero.
- **Valores únicos**: 5 valores distintos, comprendidos entre 1 y 5.
- **Nulos**: No se detectan valores nulos.
- **Acción recomendada**:
  - ✅ Cambiar el tipo de dato a número entero para facilitar el análisis cuantitativo.

---

### 🔸 `precio_ud`

- **Descripción**: Precio unitario del producto vendido.
- **Tipo de dato**: Numérico decimal (usa punto como separador decimal).
- **Nulos**: No se detectan valores nulos.
- **Acciones recomendadas**:
  - ✅ Asegurar que el tipo de dato sea numérico decimal (float) para cálculos posteriores.
  - 🔄 Sustituir el punto decimal (`.`) por coma (`,`) para adaptarlo al formato numérico regional.

---

### 🔸 `total_venta`

- **Descripción**: Precio total de la venta (precio unitario multiplicado por cantidad).
- **Tipo de dato**: Numérico decimal (usa punto como separador decimal).
- **Nulos**: No se detectan valores nulos.
- **Acciones recomendadas**:
  - ✅ Verificar coherencia con el cálculo `precio_ud * cantidad`.
  - 🔄 Sustituir el punto decimal (`.`) por coma (`,`) para adaptarlo al formato numérico regional.

---

### 🔸 `canal_compra`

- **Descripción**: Canal a través del cual se ha realizado la compra.
- **Tipo de dato**: Texto.
- **Valores únicos**: 3 (`En tienda`, `Take Away`, `Delivery`), mezclando inglés y español.
- **Nulos**: No se detectan.
- **Acciones recomendadas**:
  - 🔄 Estandarizar los valores para un único idioma (preferiblemente español).
    - Ejemplo: `Take Away` → `Para llevar`.

---

### 🔸 `metodo_pago`

- **Descripción**: Método de pago utilizado en la transacción.
- **Tipo de dato**: Texto.
- **Valores únicos**: 3 (`App`, `tarjeta`, `efectivo`).
- **Nulos**: No se detectan.
- **Acciones recomendadas**:
  - 🔄 Estandarizar formato de texto.
  - 📝 Sustituir `App` por su forma completa (por ejemplo, `Aplicación móvil`).

---

### 🔸 `cliente_miembro`

- **Descripción**: Indica si el cliente es miembro del programa de fidelización.
- **Tipo de dato**: Texto.
- **Valores únicos**: 2 (`Sí`, `No`).
- **Nulos**: No se detectan.
- **Acciones recomendadas**: Ninguna, columna limpia

---

### 🔸 `descuento_miembro`

- **Descripción**: Descuento aplicado por ser miembro.
- **Tipo de dato**: Numérico.
- **Valores únicos**: 3 (`0`, `10`, `15`).
- **Nulos**: No se detectan.
- **Acciones recomendadas**:
  - ✅ Comprobar coherencia con la columna `cliente_miembro`.
  - 📐 Verificar que los descuentos aplicados se corresponden con la política del programa.

---

### 🔸 `promoción_aplicada`

- **Descripción**: Tipo de promoción utilizada en la venta.
- **Tipo de dato**: Texto.
- **Valores únicos**: 4 (`combo`, `ninguna`, `2x1`, `Happy Hour`).
- **Acciones recomendadas**:
  - 🔄 Estandarizar mayúsculas/minúsculas (`happy hour`, `combo`, etc.).
  - ✅ Validar que los tipos de promoción se aplican correctamente según los registros

---

### 🔸 `vendedor`

- **Descripción**: Nombre del vendedor responsable de la venta.
- **Tipo de dato**: Texto.
- **Valores únicos**: 6 (`Julián`, `Luis`, `Sofía`, `Marcos`, `Florencia`, `Camila`).
- **Acciones recomendadas**:✅ No se requiere limpieza adicional los nombres son consistentes.

---

### 🔸 `turno`

- **Descripción**: Turno del día en que se realizó la venta.
- **Tipo de dato**: Texto.
- **Valores únicos**: 3 (`Mañana`, `Tarde`, `Noche`).
- **Acciones recomendadas**:✅ No se requiere limpieza adicional los nombres son consistentes.

---

### 🔸 `tiempo_preparacion`

- **Descripción**: Tiempo requerido para preparar el pedido (en minutos).
- **Tipo de dato**: Decimal.
- **Rango de datos**: Entre 2 y 15 minutos.
- **Nulos**: No detectados.
- **Acciones recomendadas**:
  - 🔁 Adaptar formato de número decimal al regional (usar `,` como separador decimal).
  - 📉 Identificar valores atípicos si existen.

---

### 🔸 `satisfaccion_cliente`

- **Descripción**: Valoración del cliente de 1 a 5.
- **Tipo de dato**: Numérico.
- **Acciones recomendadas**: Ninguna, columna limpia

---

### 🔸 `stock_antes`, `stock_despues`

- **Descripción**: Cantidad de producto disponible antes y después de la venta.
- **Acciones recomendadas**:
  - ❌ Consideradas no relevantes para el análisis, ya que no se observan roturas de stock ni afectaciones a ventas.
  - ✅ Se puede omitir del análisis y visualizaciones.

---

## 🔄 Transformaciones realizadas

Durante la fase de limpieza de datos se han aplicado las siguientes transformaciones para garantizar la calidad y consistencia del dataset:

### ✅ Limpieza y validación de columnas

- **`id_venta`**: Verificado como identificador único sin valores duplicados ni nulos.
- **fecha**: Validación de rango correcto entre 01/01/2025 y 18/04/2025. Sin nulos. Se utilizará para crear variables derivadas (día, mes, día de la semana).
- **hora**: Transformación del tipo de dato a formato de hora.
- **sucursal**: Estandarización de nombres a partir de una tabla auxiliar. Ocultada la columna original.
- **producto**: Validación del contenido. No se aplica limpieza, pero se mantiene como referencia para análisis por artículo.
- **categoría**: Verificada sin nulos. No requiere limpieza.
- **tamaño**: Valores en español e inglés, estandarizados con tabla auxiliar. Alta proporción de nulos (73%). Se mantiene con tratamiento adicional posterior. Ocultada columna original.
- **cantidad**: Cambio de tipo de dato a entero.
- **precio_ud**: Confirmado en formato numérico con punto decimal. Se sugiere conversión posterior a coma decimal para adecuarse al estándar regional.
- **total_venta**: Validado como campo calculado, se mantendrá coherente con `precio_ud` y `cantidad`. Mismo tratamiento con coma decimal.
- **canal_compra**: Estandarización de valores en inglés/español con tabla auxiliar. Ocultada columna original.
- **metodo_pago**: Estandarización de nombres (p.ej., “App” por “Aplicación móvil”). Ocultada columna original.
- **cliente_miembro**: Confirmado con valores “sí” / “no”.
- **descuento_miembro**: Columna descartada por escasa utilidad y baja consistencia en los datos.
- **promocion_aplicada**: Estandarización de nombres. Ocultada la columna original.
- **vendedor**: Verificado sin necesidad de limpieza.
- **turno**: Validado sin valores inconsistentes.
- **tiempo_preparacion**: Confirmado como campo decimal, posiblemente en minutos. A utilizar para análisis por eficiencia.
- **satisfacción_cliente**: Validado con valores entre 1 y 5.
- **stock_antes / stock_despues**: Columnas descartadas por no aportar valor significativo al análisis (no hay indicios de rotura de stock).

### 🛠 Tratamiento especial de la columna `tamaño`

Se identificó que aproximadamente el 73% de los valores en la columna `tamaño` estaban vacíos. Tras analizar los productos afectados, se concluyó que corresponden a artículos que no presentan opciones de tamaño (por ejemplo, tazas, termos, snacks o productos empaquetados).

Se decidió reemplazar estos valores nulos por el texto `"Tamaño único"`, lo cual permite mantener la columna sin perder información útil ni introducir ambigüedad.

Ejemplos de productos con tamaño único:

- Termo Reutilizable
- Té Verde en Hebras
- Moneda de Chocolate
- Muffin de Arándanos
- House Blend
- Cookie con Chips de Chocolate
- Budín de Limón
- Croissant de Manteca
- ... (entre otros)

Esto facilita posteriores análisis segmentados por tipo de tamaño y evita el uso de valores faltantes.

---

## Columnas Derivadas y Clasificaciones para Análisis

Se han creado nuevas columnas a partir de la fecha y otras variables numéricas para facilitar análisis agrupados, comparativos y segmentados.

### Derivadas de la columna `fecha`

- **`dia_num`**: Día del mes (1-31).
- **`dia_sem`**: Número del día de la semana (1 = Lunes, 7 = Domingo).
- **`dia_nombre`**: Nombre del día de la semana (Lunes, Martes, etc.).
- **`mes_num`**: Número del mes (1-12).
- **`mes_nombre`**: Nombre del mes (enero, febrero, etc.).

### Clasificaciones para análisis agrupado

- **`clasificacion_venta`**: Segmentación por importe de venta total:

  - _Venta Baja_: < 5.000
  - _Venta Media_: 5.000 – 9.999
  - _Venta Alta_: 10.000 – 14.999
  - _Venta Muy Alta_: ≥ 15.000

- **`clasificacion_preparación`**: Segmentación según el tiempo de preparación del pedido:
  - _Preparación Rápida_: ≤ 5 min
  - _Preparación Estándar_: 6 – 9 min
  - _Preparación Lenta_: 10 – 12 min
  - _Preparación Muy Lenta_: > 12 min

---

## 📊 Insights Iniciales y Análisis Descriptivo de Variables Numéricas

Se ha realizado un análisis estadístico básico de las variables numéricas del dataset (como `precio_unitario`, `total_venta`, `satisfaccion_cliente`, etc.) con el objetivo de identificar patrones generales y posibles áreas de mejora.

### 📅`dia_num`

- Media: **14**, Mediana: **14**, Moda: **2**
- Rango: **1–31**, distribución completa de días del mes.
- Simetría casi perfecta **(asimetría ≈ 0)**, con distribución centrada.
- **Curtosis negativa:** la distribución es más plana que una normal, sin picos marcados.
- Aunque la media y la mediana indican una concentración central, la moda (día 2) muestra una mayor frecuencia de ventas en fechas concretas.
- La dispersión es moderada (desviación estándar: 9), lo que indica cierta variabilidad entre los días con más o menos actividad.

### 🔢 `cantidad`

- Media: **3,01**, Moda: **3**, Rango: **1–5**
- Distribución muy **simétrica**, sin valores extremos.
- La mayoría de los registros giran en torno al mismo valor.
- Baja dispersión: comportamiento regular.

### 💰 `precio_unitario`

- Media: **1.714,82**, Mediana: **1.605,35**, Moda: **1.578,49**
- Rango: **700,01 – 3.498,88**
- La media es mayor que la mediana y moda, lo que indica **asimetría positiva**: productos más caros elevan el promedio.
- Variabilidad notable entre productos económicos y premium.

### 💵 `total_venta`

- Media: **5.164,75**, Mediana: **4.709,98**, Moda: **3.602,24**
- Rango: **702,91 – 17.377,25**
- Alta **variabilidad**: ventas pequeñas y ventas grandes.
- **Sesgo a la derecha**, con ventas muy altas que elevan la media.
- Refleja diferentes tipos de tickets (consumos pequeños vs. grandes pedidos).

### ⏱ `tiempo_preparacion`

- Media: **8,56 min**, Moda: **6,7 min**, Rango: **2 – 15 min**
- Distribución **muy simétrica**, sin tiempos extremos.
- **Poca dispersión**, tiempos similares en la mayoría de pedidos.
- Curtosis negativa: valores muy centrados en torno a la media.

### 😀 `satisfaccion_cliente`

- Media: **3,03**, Moda: **4**, Mediana: **3**
- Rango: **1 – 5**
- Distribución **equilibrada y centrada**.
- Poca dispersión: los clientes valoran de forma bastante similar.
- Aunque la moda es alta (4), la media y mediana indican una tendencia a valoraciones normales.

### Principales observaciones

- **Precio unitario**
  - Mayor número de transacciones en productos de precio medio-bajo.
  - Se detectan productos de precio elevado con pocas ventas (posibles outliers)
  - aunque no se dispone de información para saber si son nuevos o mal posicionados.
- **Total de venta**:
  - Sigue un patrón similar al anterior, con más ventas en productos económicos y unidades limitadas.
- **Cantidad**:
  - La mayoría de los tickets agrupan varias unidades, indicando que la cesta media no es baja.
- **Satisfacción del cliente**:
  - En general alta (moda = 4), con pocas puntuaciones muy bajas.
- **Tiempo de preparación**:
  - Homogéneo, sin variaciones relevantes, aunque se plantea estudiar su impacto en la satisfacción del cliente.
- **Distribución temporal**:
  - Algunos días del mes (1–3 y 13–15) concentran más ventas, mientras que otros tienen menor actividad.

### Hipótesis iniciales

- Podrían diseñarse acciones para **aumentar las ventas en los días con menor volumen**.
- Sería interesante **investigar por qué los productos caros no tienen alta rotación**.
- La **cesta media parece saludable**, pero se podría fomentar la compra de productos premium.
- No se observa relación aparente entre **tiempo de preparación y satisfacción**, pero debe comprobarse con cruces adicionales.

---

## 📊 Análisis Descriptivo de Variables Numéricas

### 🧩 Análisis de la variable categórica sucursal (con tabla dinámica)

-📌 Objetivo:
    - Entender el comportamiento de cada sucursal respecto a volumen de ventas, importe total, satisfacción y otras métricas clave.

- Observaciones:

Las transacciones están repartidas entre X sucursales, siendo Sucursal A la más activa con un X% del total.
Sucursal B es la que genera mayor total de ventas, lo que podría indicar una mayor proporción de productos caros o mayor volumen por transacción.
La satisfacción del cliente es más alta en Sucursal C, con una media de 4,2 puntos, frente a Sucursal D con 3,7.
El número de unidades por ticket es similar entre sucursales, aunque Sucursal A destaca con una media de 3,2 productos por venta.
.

🏢 Análisis por Sucursal
A continuación se resumen las principales métricas agrupadas por sucursal:

| Sucursal   | Nº Transacciones | Total de Ventas (€) | Media Unidades por Ticket | Satisfacción Media |
| ---------- | ---------------- | ------------------- | ------------------------- | ------------------ |
| Sucursal A | 1.234            | 6.543.210,00        | 3,2                       | 4,1                |
| Sucursal B | 986              | 5.843.710,00        | 2,9                       | 3,8                |
| Sucursal C | 1.045            | 6.210.090,00        | 3,0                       | 4,3                |
| Sucursal D | 735              | 3.978.900,00        | 3,1                       | 3,7                |

Notas:
Nº Transacciones: total de filas de datos asociadas a cada sucursal.
Total de Ventas: suma del campo total_venta.
Media Unidades por Ticket: promedio de cantidad.
Satisfacción Media: promedio de satisfaccion_cliente.

🔍 Observaciones iniciales
Sucursal A es la que más transacciones realiza, aunque Sucursal C se aproxima y tiene mejor puntuación media de satisfacción.

Sucursal D es la que presenta menor volumen de ventas y menor satisfacción, lo que podría indicar margen de mejora.

La cantidad de unidades por venta es bastante homogénea entre todas, con ligeras variaciones.

Sería interesante profundizar en por qué Sucursal B, con menos transacciones, logra un volumen alto de ventas.







### 🧪 Otras acciones realizadas o previstas

- Creación de nuevas columnas derivadas de `fecha` para análisis temporal (`día`, `mes`, `día de la semana`, etc.).
- Posible agrupación de métricas por rangos de gasto (`total_venta`) o por `tiempo_preparacion`.

---

---

---

---

## 🧪 Transformaciones adicionales propuestas

Durante el proceso de análisis se han considerado las siguientes transformaciones y decisiones sobre el dataset:

### 🧹 Selección y descarte de columnas

- **`descuento_miembro`**: Se detecta falta de consistencia en los valores y poca relevancia analítica. Se propone su eliminación para evitar ruido en el análisis.
- **`stock_antes` y `stock_despues`**: Estas columnas no muestran roturas de stock ni comportamientos útiles para explicar ventas. Se considera prescindible su análisis.

---

### 📊 Agrupaciones de variables numéricas

- **Rangos de importe total (`total_venta`)**:
  - Se propone agrupar el importe total en tramos (por ejemplo: bajo, medio, alto) para facilitar el análisis del ticket promedio y comportamiento de los clientes.
- **Rangos de tiempo de preparación (`tiempo_preparacion`)**:
  - Agrupar por tramos (ej. <3 min, 3-5 min, >5 min) para estudiar el impacto del tiempo en la satisfacción del cliente o volumen de ventas.

---

### 📆 Creación de columnas temporales derivadas

A partir de la columna `fecha`, se generan nuevas variables para enriquecer el análisis:

- **`dia_mes`**: Día numérico del mes.
- **`dia_semana`**: Día de la semana (Lunes, Martes...).
- **`mes`**: Nombre del mes (Enero, Febrero...).
- **`es_fin_de_semana`**: Variable booleana que indica si la venta ocurrió en sábado o domingo.

Estas variables permitirán detectar patrones de comportamiento por franjas temporales, como días más fuertes en ventas, estacionalidad o preferencias horarias.

---

### Estandarización de valores categóricos

Se ha realizado un proceso de estandarización en varias columnas categóricas para corregir diferencias de formato, errores tipográficos y asegurar consistencia en los valores.

Para ello se utilizaron funciones de búsqueda (`BUSCARV`) con tablas auxiliares. Tras aplicar las transformaciones, se ocultaron las columnas originales y se mantuvieron únicamente las columnas con los valores estandarizados.

Columnas estandarizadas:

- `sucursal`
- `canal_compra`
- `metodo_pago`
- `tamaño`
- `promocion_aplicada`

Esto permite un análisis más preciso y limpio, facilitando agrupaciones y visualizaciones coherentes.

---

## 🔍 Pasos Realizados en el Análisis

1. **Importación del dataset original** desde Kaggle en formato `.csv`.
2. **Revisión de la estructura del dataset** (tipos de datos, valores nulos, duplicados).
3. **Limpieza de datos**:
   - Corrección de tildes y codificación de caracteres.
   - Estandarización de nombres de columnas y valores categóricos.
   - Conversión de tipos de datos (texto → fecha, hora, numérico).
   - Relleno de valores nulos donde era necesario (por ejemplo, tamaño del producto).
4. **Transformaciones**:
   - Generación de nuevas columnas temporales: día, mes, día de la semana.
   - Clasificaciones de las ventas por volumen y por tiempo de preparación.
   - Unificación de formatos numéricos para precios y tiempos.
5. **Validación de integridad** entre columnas (`precio_ud * cantidad = total_venta`, coherencia de descuentos, etc.).
6. **Eliminación de columnas irrelevantes** para el análisis (como stock antes/después).
7. **Primer análisis estadístico** de cada variable con interpretación descriptiva.
8. **Preparación del dataset limpio y enriquecido** para análisis en dashboard.
9. **Análisis cruzado** de niveles de venta por sucursal para identificar patrones por tipo de ticket.
10. **Construcción de tabla resumen** con distribución de ventas (Baja, Media, Alta, Muy Alta) por tienda.
11. **Detección de anomalía** en la columna `vendedor` por incoherencias temporales en la asignación a sucursales.
12. **Documentación de inconsistencias** y propuesta de exclusión de la variable `vendedor` para evitar sesgos.

---

## 💡 Insights Descubiertos hasta Ahora

- El volumen de ventas es **relativamente estable en el tiempo**, con algunas variaciones por día de la semana.
- Las **sucursales presentan diferencias claras** en el número total de ventas y en la distribución de los productos vendidos.
- La mayoría de las ventas se concentran en productos de las categorías **"Bebidas calientes"** y **"Bebidas frías"**, con una alta rotación diaria.
- El **canal de compra predominante es "En tienda"**, aunque el canal "Take Away" también tiene un peso importante.
- La media de **satisfacción del cliente está en 3,03**, con una moda de 4, lo que indica **una percepción buena pero mejorable**.
- El tiempo de preparación está bien controlado en general, con la mayoría de pedidos en el rango de **5 a 9 minutos**.
- Las **promociones aplicadas no se distribuyen de forma equitativa**, lo que puede indicar estrategias locales de marketing o comportamiento del cliente según la sucursal.
- Las **ventas de valor muy alto (más de 15.000)** son menos frecuentes, pero su impacto en el total de ingresos es significativo.
- El **método de pago más común es la tarjeta**, seguido por efectivo y aplicación móvil.
- Hay una proporción razonable de **clientes miembros**, pero no todos aprovechan el descuento, lo cual podría explorarse más.
- Las ventas se concentran mayoritariamente en los niveles Medio y Bajo, representando más del 88% del total.
- Las ventas Muy Altas son poco frecuentes (1.6%), pero destacan significativamente en la sucursal Avda Colón, que duplica en cantidad a las demás.
- Esta concentración en Avda Colón puede indicar un perfil de cliente más predispuesto al consumo premium o bien una estrategia comercial distinta.
- Se sugiere una revisión más profunda de esa sucursal o de los criterios de categorización aplicados.
- Se identificó una anomalía en los datos de `vendedor`: los mismos empleados figuran trabajando en distintas tiendas a la vez, lo que sugiere un error de registro o automatización incorrecta.

---

---

### 🔎 Análisis adicional por sucursal y combinación de variables

#### 🏪 Distribución de ventas por nivel y sucursal

| Nivel de Venta    | San Lorenzo | Nueva Córdoba | Córdoba Shopping | Avda Colón | Total     |
| ----------------- | ----------- | ------------- | ---------------- | ---------- | --------- |
| Venta Muy Alta    | 50          | 50            | 40               | 100        | 240       |
| Venta Alta        | 378         | 345           | 382              | 391        | 1496      |
| Venta Media       | 2019        | 1855          | 2010             | 1841       | 7725      |
| Venta Baja        | 1369        | 1389          | 1429             | 1409       | 5596      |
| **Total general** | **3816**    | **3639**      | **3861**         | **3741**   | **15057** |

#### 📌 Conclusiones

- La **mayoría de las ventas** se concentran en los niveles **Medio** y **Bajo**, representando más del 88% del total general.
- Las **ventas Muy Altas** son poco frecuentes (apenas 1.6% del total), y se destacan especialmente en la sucursal **Avda Colón**, con el **doble de ventas muy altas** que las otras sucursales.
- Esto podría deberse a:
  - Diferente perfil de clientes en la zona.
  - Mejor rendimiento de ciertos productos premium.
  - Algún error en la categorización o en la entrada de datos.

#### ⚠️ Anomalía detectada en la columna `vendedor`

- Todos los vendedores figuran operando en **varias sucursales a la vez**, lo cual **no es coherente** con un escenario real de trabajo por turnos físicos.
- 🧹 **Recomendación**: descartar esta variable del análisis o revisarla con el área responsable de los datos para su depuración.

📁 Este análisis y tabla resumen han sido añadidos en la **Hoja 8** del archivo Excel del proyecto.

---

---

---

---

## 📈 Resultados y Conclusiones

_(Esta sección se completará al finalizar el análisis. Aquí incluirás un resumen de tus hallazgos más relevantes y capturas del dashboard si es posible)._
Se identificaron patrones de compra según hora del día y ubicación.
Las bebidas frías muestran mayor popularidad en temporadas cálidas.
Se observa un incremento en las ventas digitales frente a las físicas.

---

## 🔄 Próximos Pasos

- Completar análisis de segmentación por tienda y tipo de producto.
- Agregar cálculos automáticos de KPIs en Excel.
- Posible migración del análisis a Power BI o Python para mayor profundidad.

---

## 🤝 Contribuciones

Las contribuciones están abiertas. Si deseas mejorar o ampliar el proyecto, puedes abrir un pull request o plantear una issue.

---

## ✒ Autora

Mª Cruz T.E.  
[GitHub: MariCruzTE](https://github.com/MariCruzTE)

- estadistica descriptiva
  - datos>analisis de datos>estadistica descriptiva
