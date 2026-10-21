# EverPeak Retail Analysis

**Análisis exploratorio de datos | Calidad de datos | Detección de valores atípicos | Segmentación de transacciones**

## 1. Descripción del proyecto

EverPeak Retail Analysis es un proyecto de análisis de datos enfocado en estudiar el comportamiento de las transacciones comerciales, evaluar la calidad de la información e identificar patrones que puedan contribuir a la toma de decisiones de negocio.

El análisis utiliza Python para explorar datos transaccionales, detectar posibles anomalías y desarrollar segmentaciones que permitan comprender las diferencias entre grupos de compras.

## 2. Objetivo del análisis

Analizar la información transaccional de EverPeak para identificar patrones de compra, evaluar la confiabilidad de los datos y generar hallazgos útiles para la planificación comercial.

**Objetivos específicos:**

- Examinar la estructura, integridad y consistencia de los datos.
- Analizar las distribuciones de precio, cantidad, valor de pedido y edad.
- Identificar valores atípicos mediante IQR y Z-Score.
- Evaluar el impacto de posibles tratamientos estadísticos.
- Segmentar transacciones según volumen de compra, edad y método de pago.
- Formular recomendaciones basadas en los resultados observados.

## 3. Tecnologías utilizadas

| Tecnología | Aplicación |
|---|---|
| Python | Procesamiento y análisis |
| pandas | Manipulación y exploración de datos |
| NumPy | Operaciones numéricas y segmentación |
| Matplotlib | Visualización de distribuciones |
| Seaborn | Histogramas y diagramas de caja |
| Google Colab | Ejecución y documentación del notebook |
| GitHub | Control de versiones y publicación |

## 4. Conjunto de datos

El análisis principal utiliza un dataset limpio de **5,000 transacciones y 14 columnas**.

Los archivos de trabajo son:

- `everpeak_clean.csv`: conjunto de datos preparado para el análisis exploratorio.
- `everpeak_retail.csv`: conjunto de datos de origen utilizado para análisis complementarios de calidad y segmentación.

Las variables principales incluyen `price`, `quantity`, `order_value`, `customer_age` y `payment_method`.

Los datasets no se distribuyen públicamente mientras no se confirme que sus condiciones de uso permiten compartirlos.

## 5. Metodología

### 5.1 Exploración y calidad de datos

Se revisaron dimensiones, tipos de datos, valores faltantes y duplicados. También se contempló la identificación de valores inválidos y posibles anomalías presentes en los datos de origen.

### 5.2 Análisis estadístico descriptivo

Se calcularon medidas de tendencia central y dispersión, incluyendo media, mediana, desviación estándar, cuartiles y valores extremos.

Las distribuciones se examinaron mediante histogramas y diagramas de caja.

### 5.3 Detección de valores atípicos

Se implementaron métodos IQR y Z-Score para identificar observaciones extremas.

Adicionalmente, se realizó una simulación de winsorización al percentil 99 para evaluar posibles cambios en los indicadores estadísticos, conservando los valores originales.

### 5.4 Segmentación de transacciones

Se desarrollaron clasificaciones basadas en volumen de compra, edad y método de pago mediante operaciones condicionales y funciones de Python.

### 5.5 Interpretación comercial

Los resultados se interpretaron considerando su relevancia para el negocio y las limitaciones de los métodos utilizados.

## 6. Principales hallazgos

**Calidad de datos**

El conjunto de datos limpio analizado contiene 5,000 registros, sin valores nulos ni filas completamente duplicadas.

**Distribuciones**

Las variables `price` y `quantity` presentan medias superiores a sus medianas, lo que sugiere la influencia de observaciones de valores elevados.

**Valores atípicos identificados mediante IQR**

| Variable | Observaciones atípicas | Porcentaje |
|---|---:|---:|
| `price` | 446 | 8.92% |
| `quantity` | 642 | 12.84% |
| `order_value` | 165 | 3.30% |
| `customer_age` | 0 | 0.00% |

La presencia de valores extremos no demuestra por sí sola errores de registro. Su tratamiento debe considerar la plausibilidad comercial de cada observación.

**Segmentación por volumen**

| Segmento | Transacciones | Porcentaje |
|---|---:|---:|
| Low Volume | 3,739 | 74.78% |
| High Volume | 1,261 | 25.22% |
| **Total** | **5,000** | **100%** |

La mayoría de las transacciones pertenece al segmento de bajo volumen, mientras que aproximadamente una cuarta parte corresponde a compras de alto volumen.

## 7. Recomendaciones de negocio

- Analizar la contribución económica de las transacciones de alto volumen.
- Investigar los valores extremos antes de aplicar exclusiones o transformaciones.
- Comparar el comportamiento de compra entre segmentos para identificar oportunidades comerciales.
- Validar los umbrales de segmentación con indicadores adicionales, como ingresos y recurrencia de compra.

## 8. Estructura del repositorio

La estructura prevista es:

```text
everpeak-analysis/
├── README.md
└── notebooks/
    └── everpeak_analysis.ipynb
```

## 9. Reproducibilidad

Para reproducir el análisis:

1. Abrir `notebooks/everpeak_analysis.ipynb` en Google Colab o Jupyter Notebook.
2. Obtener los archivos CSV desde una fuente autorizada.
3. Cargar los archivos mediante la celda de importación del notebook.
4. Ejecutar las celdas en orden.
5. Revisar las estadísticas, visualizaciones, segmentaciones y conclusiones.

El notebook requiere Python y las bibliotecas pandas, NumPy, Matplotlib y Seaborn.

## 10. Limitaciones

Los resultados representan las transacciones incluidas en los datos disponibles y no necesariamente describen el comportamiento de toda la población de clientes.

Los criterios de segmentación se definieron previamente y requieren validación adicional para determinar su capacidad de diferenciar patrones comerciales.

La identificación estadística de valores atípicos no constituye evidencia suficiente para eliminar registros. Cualquier tratamiento definitivo debe justificarse según la calidad de los datos y su impacto sobre el análisis.

## 11. Control de versiones

El proyecto utiliza GitHub para mantener un historial de modificaciones del notebook y su documentación.

Los cambios relevantes se registran mediante commits descriptivos que facilitan la trazabilidad del análisis y la revisión de versiones anteriores.
