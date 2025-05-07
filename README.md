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

## 📊 Dataset

- **Fuente**: [Ventas Starbucks - Kaggle](https://www.kaggle.com/datasets/guadalupesaraviaweht/ventas-starbucks)
- **Formato**: CSV
- **Tamaño**: ~149.000 filas, 18 columnas
- **Ubicación**: `./data/ventas_starbucks_2025.csv`

---

## 🗂 Estructura del Proyecto

```
📁 data/           # Archivo original CSV con los datos
📁 docs/           # Documentación adicional, capturas o notas
📁 dashboard/      # Dashboard final en formato Excel
📄 README.md       # Este archivo
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


## Pasos seguidos durante el proyecto




### Comprension general datos
- Dataset con 5001 filas y 21 columnas iniciales
- Se comprueba que no hay filas duplicadas
-  Se inicia el editor de Power Query para revisar y comprender las columnas:
     - Se cambian los nombres de columnas para que no haya mayusculas y sean mas adecuados
-contenido de columnas:
     - id_venta: 
          - Identificador único de la transacción de venta
          - Sin errores, sin nulos
          - Se cambia tipo de dato a texto
     - fecha: fecha de las ventas, 
          - comprende fechas entre el 01-01-2025 y 18-04-2025, 108 distintos, sin nulos
          - Se cambia tipo de dato a fecha
     - hora:
          - hora de la venta
          - entre las 7:00 y las 21:00
          - Se cambia tipo de dato a hora
     - sucursal:
          - tienda que realiza la venta parecen ser de Cordoba, Argentina
          - 4 valores únicos, posible estandarizacion de nombres
               - Sucursal Nueva Córdoba ,Sucursal Shopping ,Sucursal Av. Colón ,Sucursal San Lorenzo 47
          - sin nulos, tipo de dato texto
     - producto:
          - nombre del producto vendido
          -  36 valores distintos
          - sin nulos, tipo de dato texto
     - categoría:
          - categoria del producto
          -  11 distintas
          -  sin nulos, formato texto
     -tamaño:
          - Tamaño del producto vendido
          - 5 distintos (Tall, Pequeño, Grande, Venti)
               - nombres de tamaños en ingles y español, estandarizar datos
          - 73% de celdas vacías
               - hacer tratamiento de nulos
     - cantidad:
          - unidades vendidas en la transacion de compra
          - 5 valores distintos entre 1 y 5
          - sin nulos, se cambia tipo de dato a numero entero
     - precio_ud:
          - precio unitario del producto
          - formato decimales con .
     - total_vemta:
          - precio unitario del producto
          - formato decimales con .
     - canal_compra:
          - canal por el que se ha realizado la compra
          -  3 valores distintos (En tienda, Take Away, Delivery)
          - en ingles y español, estandarizar datos
     - metodo_pago:
          - 3 distintos (App, tarjeta y efectivo)
          - estandarizar datos, cambiar App por palabra completa
     - cliente_miembro:
          - 2 distintos, si y no
     - descuento_miembro:
          - 3 distintos (0, 10, 15)
     - promoción_aplicada:
          - 4 distintos (combo, ninguna, 2x1, happy Hour)
          -  estandarización de datos
     - vendedor:
          - 6 únicos(Julián, Luis, Sofía, Marcos, Florencia, Camila)
     - turno:
          - 3 únicos(Tarde, Mañana, Noche)
     -tiempo_preparacion:
          - valor decimal, supongo en minutos
     - satisfacción cliente:
          - entre 1 y 5
     - stock antes:
     - stock despues:

- Se cambia el tipo de datos mas adecuado en cada columna
- se sustituyen los (.) por (,) para adecuar los números decimales a la zona
- Elegir las columnas que se van a quedar, posibles descartes:
     - descuento miembro, no parece una columna relevante ni veo consistencia en los datos
     - las dos columnas de stock, no parecen relevantes  puesto que nunca llegan a tener roturas de stock que podria afectar a las ventas
- posibles agrupaciones que pudieran ser interesantes
     - por rangos de importe de gasto
     - por rangos de tiempo de preparacion
- creacion de columnas con fechas disgregadas dia, dia de la semana, mes, etc
- estadistica descriptiva
     - datos>analisis de datos>estadistica descriptiva
