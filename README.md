# Análisis de Producción de Hidrocarburos - Argentina 2024

Análisis exploratorio de la producción de petróleo y gas en Argentina durante 2024, utilizando datos oficiales del Ministerio de Energía de la Nación. El proyecto incluye limpieza y transformación de datos con Python, análisis estadístico y visualización mediante un dashboard interactivo en Power BI.

---

## Objetivo

Identificar patrones de producción a nivel nacional, provincial y por pozo, con el fin de detectar oportunidades de inversión y señales de alerta operativa en el sector hidrocarburífero argentino.

Las preguntas que guían el análisis son:

- ¿Cómo evolucionó la producción de petróleo y gas mes a mes durante 2024?
- ¿Qué provincias y empresas concentran la mayor producción?
- ¿Cuál es el peso del recurso no convencional (Vaca Muerta) sobre el total?
- ¿Qué pozos son más eficientes y qué características comparten?
- ¿Qué pozos representan un costo operativo elevado en relación a su producción?

---

## Tecnologías utilizadas

- Python 3.13
- Pandas
- Jupyter Notebook
- Power BI Desktop

---

## Estructura del proyecto

    hidrocarburos-analisis-2024/
    │
    ├── notebooks/
    │   ├── 01_exploracion.ipynb
    │   ├── 02_limpieza.ipynb
    │   ├── 03_analisis_general.ipynb
    │   ├── 04_analisis_pozos.ipynb
    │   └── 05_patrones_recomendaciones.ipynb
    │
    ├── data/
    │   └── processed/
    │       ├── datos_limpios.csv
    │       ├── analisis_pozos.csv
    │       ├── declive_pozos.csv
    │       ├── patrones_pozos.csv
    │       ├── powerbi_produccion_mensual.csv
    │       ├── powerbi_produccion_provincia.csv
    │       ├── powerbi_produccion_empresa.csv
    │       └── powerbi_convencional_vs_no.csv
    │
    ├── powerbi/
    │   └── analisis_hidrocarburos.pbix
    │
    ├── preparar_powerbi.ipynb
    ├── .gitignore
    └── README.md

---

## Dataset

Los datos utilizados provienen del portal de datos abiertos del Ministerio de Energía de la Nación Argentina:

**Producción de petróleo y gas por pozo (Capítulo IV)**
https://datos.gob.ar/dataset/energia-produccion-petroleo-gas-por-pozo-capitulo-iv

Se utilizó el archivo CSV correspondiente al año 2024, que contiene el detalle mensual de producción por pozo, yacimiento, concesión y provincia. El dataset original no está incluido en este repositorio por su tamaño (301 MB). Para reproducir el análisis, descargarlo desde el link anterior y ubicarlo en la carpeta `data/raw/`.

---

## Instalación

Clonar el repositorio:

    git clone https://github.com/SantiAbdal/hidrocarburos-analisis-2024.git
    cd hidrocarburos-analisis-2024

Instalar dependencias:

    pip install pandas jupyter

---

## Flujo del análisis

**1. Exploración inicial** (`01_exploracion.ipynb`)
Inspección del dataset: dimensiones, tipos de datos, valores nulos y valores únicos en columnas clave.

**2. Limpieza** (`02_limpieza.ipynb`)
Eliminación de columnas irrelevantes, tratamiento de nulos, corrección de valores negativos y filtrado de pozos activos.

**3. Análisis general** (`03_analisis_general.ipynb`)
Producción total anual, evolución mensual, comparación por provincia y empresa, análisis de concentración de mercado y comparación convencional vs no convencional.

**4. Análisis por pozo** (`04_analisis_pozos.ipynb`)
Ranking de pozos más productivos, eficiencia en relación a inyección y tiempo efectivo de flujo, detección de pozos en declive.

**5. Patrones y recomendaciones** (`05_patrones_recomendaciones.ipynb`)
Clasificación de pozos por rendimiento, identificación de patrones geográficos y operativos en pozos de alto y bajo rendimiento, y recomendaciones de negocio.

---

## Principales hallazgos

- Neuquén concentra el 58% de la producción de petróleo y el 68% del gas, impulsado por Vaca Muerta.
- El recurso no convencional ya representa el 55% de la producción de petróleo y el 63% del gas.
- Solo 4 empresas (YPF, Pan American Energy, Vista Energy y Pluspetrol) concentran el 77% de la producción nacional.
- Los pozos de alto rendimiento no requieren inyección de agua, mientras que los de bajo rendimiento inyectan en promedio 52 m³ para producir cantidades mínimas.
- Se identificaron 6.232 pozos con caída de producción mayor al 30% entre el primer y segundo semestre.

---

## Dashboard

El dashboard interactivo desarrollado en Power BI incluye:

- Producción mensual de petróleo y gas
- Producción por provincia
- Top empresas por producción
- Convencional vs No Convencional
- Productividad promedio por rendimiento de pozo

El archivo `.pbix` está disponible en la carpeta `powerbi/`.

---

## Trabajo futuro

- Incorporar datos de 2023 y 2025 para análisis comparativo entre años
- Profundizar el análisis de declive por formación productiva
- Incorporar datos de precios para calcular rentabilidad real por pozo

---

## Autor

Santiago Abdala — [LinkedIn](https://www.linkedin.com/in/santiago-abdala-170982340/) · [GitHub](https://github.com/SantiAbdal)