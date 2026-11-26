# ConnectaTel | Análisis y Segmentación de Clientes

## Descripción del proyecto

Este proyecto se enfoca en un análisis sobre el comportamiento de los clientes de **ConnectaTel**, una empresa de telecomunicaciones en Latinoamérica, utilizando información disponible hasta 2024.

Se realizó la exploración, limpieza, integración y análisis estadístico de los datos, con el propósito de identificar patrones de consumo, detectar valores atípicos y construir segmentos de clientes que permitan orientar decisiones comerciales.

## Objetivo

Analizar el comportamiento de los clientes de ConnectaTel según sus características demográficas, planes contratados y consumo de servicios, con el fin de:

- Identificar patrones de uso de llamadas y mensajes.
- Detectar inconsistencias y valores atípicos en los datos.
- Segmentar clientes según su edad y nivel de consumo.
- Identificar oportunidades de optimización de planes y retención.

## Datasets utilizados

El proyecto utiliza tres archivos CSV:

| Dataset | Descripción |
| `plans.csv` | Información de los planes Básico y Premium, incluyendo precios y beneficios. |
| `users_latam.csv` | Información de clientes: identificador, edad, ciudad, fecha de registro, plan y fecha de abandono. |
| `usage.csv` | Registros de llamadas y mensajes, incluyendo usuario, tipo de servicio, fecha, duración y longitud. |

## Etapas del análisis

### 1. Exploración inicial

Carga de los tres datasets y revisión de su estructura, dimensiones, tipos de datos, valores nulos y estadísticas descriptivas.

### 2. Identificación y análisis de la calidad de los datos.

Detección de valores inválidos, sentinels y fechas fuera del periodo de análisis.
Entre los problemas identificados se encuentran:
- Edades registradas con el valor inválido `-999`.
- 565 clientes sin ciudad válida (14%).
- 40 fechas de registro correspondientes a 2026, fuera del periodo analizado.

### 3. Limpieza y preparación

Se realizaron las siguientes transformaciones:

- Sustitución de valores de edades incorrrectar por la mediana de las edades.
- Reemplazo del sentinel `?` en la columna `city` por valores nulos.
- Conversión de fechas.
- Sustitución de fechas de registros del año 2026 por valores nulos.

### 4. Análisis estadístico por cliente

Se agruparon los registros de consumo por `user_id` para calcular:

- Cantidad total de mensajes.
- Cantidad total de llamadas.
- Total de minutos de llamadas.
 Adicional se realizó una segmentación de los clientes a nivel de edad y consumo.

### El notebook se puede ejecutar en Google Colab

1. Ingresa a [Google Colab](https://colab.research.google.com/).
2. Selecciona **Archivo → Subir notebook**.
3. Carga el archivo `.ipynb` del proyecto.
4. Carga los tres datasets CSV en el entorno de ejecución.
5. Ajusta las rutas de los archivos en las celdas de carga.
6. Ejecuta las celdas en orden para reproducir el análisis.

## Conclusiones

El análisis permitió construir un perfil de los clientes de ConnectaTel, identificar problemas a nivel de data y reconocer distintos patrones de comportamiento.

Los resultados sugieren oportunidades para mejorar la segmentación comercial y evaluar ofertas más alineadas con las necesidades de consumo.
