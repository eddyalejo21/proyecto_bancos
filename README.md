# Sistema de Inteligencia Financiera para el Análisis del Sector Bancario Ecuatoriano

![Python](https://img.shields.io/badge/Python-3.12+-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-green)
![FastAPI](https://img.shields.io/badge/FastAPI-API-009688)
![Streamlit](https://img.shields.io/badge/Streamlit-Dashboard-ff4b4b)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-orange)
![Status](https://img.shields.io/badge/Status-En%20desarrollo-yellow)
![License](https://img.shields.io/badge/License-Uso%20académico-lightgrey)

Proyecto de tesis orientado a transformar los boletines estadísticos oficiales de la Superintendencia de Bancos del Ecuador en un sistema analítico que permita comparar, rankear y evaluar el desempeño financiero de las instituciones bancarias privadas del país.

---

## Descripción del proyecto

La Superintendencia de Bancos del Ecuador publica mensualmente boletines estadísticos en archivos Excel con información financiera de las instituciones bancarias. Sin embargo, estos archivos presentan una estructura institucional compleja: encabezados multinivel, celdas fusionadas, bancos ubicados como columnas, variaciones en los nombres de las instituciones y cambios en la presencia de bancos a lo largo del tiempo.

Este proyecto busca convertir dichos archivos en un dataset analítico consolidado, limpio y estandarizado, que pueda ser utilizado para análisis exploratorio de datos, rankings financieros, visualizaciones interactivas y futuros modelos de evaluación del desempeño bancario.

---

## Objetivo general

Transformar el boletín estadístico oficial de la Superintendencia de Bancos en un sistema de inteligencia financiera que permita comparar, rankear y analizar el desempeño de las instituciones bancarias privadas del Ecuador mediante indicadores financieros clave.

---
## Resumen rápido de la solución

Este proyecto convierte archivos Excel oficiales del sistema bancario ecuatoriano en un dataset limpio que permite:

- Procesar boletines estadísticos en formato `.xls`, `.xlsx` y `.xlsm`.
- Extraer automáticamente el período desde la cabecera del archivo.
- Limpiar encabezados, celdas fusionadas y filas no analíticas.
- Estandarizar nombres de bancos.
- Transformar bancos de columnas a filas.
- Consolidar indicadores financieros en formato analítico.
- Generar rankings por banco, período e indicador.
- Preparar datos para un dashboard en Streamlit.
- Exponer información mediante una API local con FastAPI.

---
## Anáñisis de la estrucutra de los archivos

- Encabezados multinivel.
- Celdas fusionadas.
- Bancos ubicados como columnas.
- Variaciones en los nombres de las instituciones.
- Cambios en la presencia de bancos a lo largo del tiempo.
- Filas de categorías mezcladas con datos reales.

---

## Problema que resuelve

Actualmente, el análisis comparativo del sector bancario ecuatoriano requiere revisar múltiples archivos Excel con formatos no preparados para análisis directo. Esto dificulta:

- Comparar bancos entre diferentes períodos.
- Analizar tendencias históricas.
- Rankear instituciones según indicadores financieros.
- Identificar cambios en desempeño, tamaño, rentabilidad, solvencia o riesgo.
- Construir dashboards o herramientas de consulta rápida.

Este proyecto automatiza el proceso de extracción, limpieza, transformación y consolidación de los datos financieros.

---

## Propósito del sistema

El propósito del sistema es construir una base analítica confiable que permita convertir archivos Excel oficiales en información accionable para análisis financiero.

El sistema permitirá:

- Procesar múltiples archivos Excel históricos.
- Extraer el período desde la cabecera del archivo.
- Estandarizar nombres de bancos.
- Eliminar filas no analíticas, como categorías o agrupaciones.
- Transformar la estructura original a formato largo.
- Consolidar indicadores financieros en un único dataset.
- Preparar los datos para un dashboard interactivo en Streamlit.
- Facilitar rankings y comparaciones entre bancos.

---

## Audiencia objetivo

Este proyecto está dirigido a:

- Analistas financieros.
- Investigadores académicos.
- Estudiantes de ciencia de datos.
- Instituciones financieras.
- Entidades públicas de control.
- Usuarios interesados en el desempeño del sistema bancario ecuatoriano.

---

## Alcance del proyecto

El proyecto considera el procesamiento de aproximadamente 206 archivos Excel oficiales en formatos `.xls`, `.xlsx` y `.xlsm`.

Como estrategia de desarrollo, primero se trabaja con archivos de prueba para validar el pipeline de limpieza y transformación. Posteriormente, el proceso se escala al conjunto completo de archivos.

---

## Indicadores financieros considerados

El sistema está diseñado para trabajar con indicadores financieros como:

- Activos.
- ROE.
- Solvencia.
- Morosidad.

La estructura final permite incorporar nuevos indicadores sin modificar completamente el modelo de datos.

---

## Estructura del dataset final

El dataset limpio se organiza en formato largo, ideal para análisis con Pandas, visualización en Streamlit y consumo desde APIs.

Estructura propuesta:

| Columna | Descripción |
|---|---|
| `periodo` | Período del boletín en formato `YYYY-MM` |
| `banco` | Nombre estandarizado de la institución bancaria |
| `indicador` | Nombre del indicador financiero |
| `valor` | Valor numérico del indicador |

Ejemplo:

| periodo | banco | indicador | valor |
|---|---|---|---|
| 2024-01 | PICHINCHA | ACTIVOS | 18500000.25 |
| 2024-01 | GUAYAQUIL | ACTIVOS | 11200000.90 |
| 2024-01 | PRODUBANCO | ROE | 12.45 |

---

## Arquitectura general del proyecto

El proyecto se organiza en tres capas principales:

```text
Archivos Excel oficiales
        |
        v
Pipeline de limpieza y transformación con Pandas
        |
        v
Dataset limpio consolidado CSV / Parquet
        |
        v
API local con FastAPI
        |
        v
Dashboard interactivo con Streamlit
