🚀 Data Cleaning & ETL Pipeline: HR Insights (SQL)

📌 Descripción del Proyecto
Este repositorio contiene un flujo integral de ETL (Extract, Transform, Load) desarrollado en MySQL para procesar un dataset crudo de Recursos Humanos. El proyecto se enfoca en la transformación de datos inconsistentes en un set de datos estructurado y optimizado, listo para ser consumido por herramientas de visualización como Power BI o Python.

🛠️ Tecnologías y Técnicas Aplicadas
Motor de Base de Datos: MySQL Workbench.

Limpieza Avanzada: Expresiones Regulares (RegEx) para normalización de strings.

Automatización: Stored Procedures para optimizar tareas repetitivas de consulta.

Integridad de Datos: Manejo de duplicados mediante tablas temporales y validación de tipos técnicos (DECIMAL, DATE, DATETIME).


⚙️ El Proceso de Limpieza (Paso a Paso)
1. Ingesta y Corrección de Metadatos
Identificación y corrección de errores de codificación BOM (Byte Order Mark) en las cabeceras del CSV.

Estandarización de nombres de columnas a un formato descriptivo y profesional (CamelCase/Snake_case).

2. Sanitización y Calidad (Data Quality)
Deduplicación: Eliminación de registros repetidos utilizando tablas temporales para garantizar la unicidad de cada ID de empleado.

Normalización de Texto: Limpieza de espacios en blanco mediante TRIM y eliminación de espacios múltiples internos con RegEx.

Mapping de Categorías: Transformación de valores ambiguos en categorías estandarizadas (Male/Female/Other) mediante lógica CASE.

3. Transformación Técnica
Formateo de Moneda: Conversión de strings (ej. "$1,200.50") a valores de tipo DECIMAL(15,2) para habilitar cálculos matemáticos.

Normalización de Fechas: Procesamiento de múltiples formatos de fecha (ISO, MM/DD/YYYY, DD-MM-YYYY) a un formato estándar de base de datos.

4. Feature Engineering (Generación de Valor)
Cálculo de Edad: Implementación de la función TIMESTAMPDIFF para obtener la edad actual de los empleados dinámicamente.

Generación de Emails: Creación automatizada de correos corporativos basados en la combinación de nombres y áreas.

📈 Resultado Final
El script culmina en la creación de una Vista (View) optimizada que filtra registros inválidos y presenta la información lista para el análisis de indicadores clave (KPIs) de RRHH.


👤 Autor

Arturo Geldres Valderrama
🎯 Aspirante a Data Analyst.

💡 Instrucciones de Uso
Clona este repositorio.

Importa el archivo .csv proporcionado en la carpeta data/.

Ejecuta el script SQL en orden secuencial para transformar los datos.
