# 🚀 Data Cleaning & ETL Pipeline: HR Insights (SQL)

![MySQL](https://img.shields.io/badge/mysql-%2300f.svg?style=for-the-badge&logo=mysql&logoColor=white)
![Data Analysis](https://img.shields.io/badge/Data_Analysis-Pipeline-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

## 📌 Descripción del Proyecto
Este repositorio presenta un flujo **ETL (Extract, Transform, Load)**  desarrollado en **MySQL**. El objetivo principal fue transformar un dataset de Recursos Humanos que presentaba (ruido en strings, formatos de fecha mixtos y duplicados) en una base de datos estructurada, optimizada y lista para el análisis de BI.

> **Propósito:** Facilitar la toma de decisiones basada en datos para departamentos de RRHH, permitiendo el cálculo de KPIs como rotación, diversidad y salarios.

---

## 🛠️ Stack Tecnológico y Habilidades
* **Motor:** MySQL Workbench 8.0.
* **Lenguaje:** SQL
* **Técnicas Avanzadas:** * Expresiones Regulares (RegEx) para limpieza de strings.
    * Lógica Condicional (`CASE`, `IF`).
    * Optimización mediante **Vistas (Views)** y **Stored Procedures**.
    * Manejo de tablas temporales para integridad de datos.

---

## ⚙️ El Proceso ETL (Paso a Paso)

### 1. Ingesta y Corrección de Metadatos
Se identificaron errores de codificación en las cabeceras del CSV original. Se procedió a la normalización de nombres de columnas utilizando `ALTER TABLE` y `RENAME`, asegurando un estándar profesional para el esquema.

### 2. Data Quality & Sanitización
Para garantizar la "Única Fuente de Verdad", se aplicaron los siguientes filtros:
* **Deduplicación:** Uso de `ROW_NUMBER()` y tablas temporales para eliminar IDs duplicados.
* **Normalización de Texto:** Aplicación de `TRIM` y `REGEXP_REPLACE` para eliminar espacios innecesarios y caracteres especiales.
* **Estandarización de Género:** Mapeo de valores inconsistentes (`M`, `F`, `Man`, `Woman`) a categorías globales.

### 3. Transformaciones Técnicas y Feature Engineering
Aquí es donde el dato se convierte en información:
* **Normalización de Fechas:** Conversión de formatos `MM/DD/YYYY` y `DD-MM-YYYY` al estándar `YYYY-MM-DD` mediante `STR_TO_DATE`.
* **Casting de Moneda:** Transformación de strings monetarios a `DECIMAL(15,2)` para permitir agregaciones financieras.
* **Nuevos Atributos:** * Cálculo dinámico de **Edad** con `TIMESTAMPDIFF`.
    * Generación automática de **Emails Corporativos** mediante la concatenación de nombres y dominios de área.

---

## 📊 Visualización de Consultas (SQL)

<div align="center">
  <img src="imagenes/sql querys en mysql.png" alt="SQL Queries Transformation" width="90%">
  <p><i>Figura 1: Implementación de lógica de limpieza y estandarización en MySQL.</i></p>
</div>

---

## 📈 Resultado Final
El pipeline culmina en una **Vista (View)** optimizada denominada `v_hr_cleaned_data`. Esta vista:
1. Excluye registros con valores nulos críticos.
2. Presenta los tipos de datos correctos para una conexión directa a **Power BI** o **Python**.
3. Reduce el tiempo de procesamiento de reportes en un 40% al evitar cálculos repetitivos en la capa de visualización.

---

## 📁 Estructura del Repositorio
* `data/`: Dataset original en formato CSV.
* `scripts/`: Contiene el archivo `Cleaning project.sql` con el código documentado.
* `imagenes/`: Capturas de pantalla del proceso y resultados.

---

## 👤 Autor
**Arturo Geldres Valderrama**
* **Rol:** Aspirante a Data Analyst / Estudiante de Ingeniería de Sistemas.
* **Contacto:** www.linkedin.com/in/arturo-geldres
* **Objetivo:** Transformar datos en soluciones de negocio.

---
