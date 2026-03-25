# Análisis de Producción de Hidrocarburos — Argentina 2024/2025

Análisis exploratorio de la producción de petróleo y gas en Argentina durante 2024 y 2025, utilizando datos oficiales del Ministerio de Energía de la Nación. El proyecto incluye limpieza y transformación de datos con Python, análisis estadístico y visualización mediante un dashboard interactivo en Power BI con comparativo entre ambos años.

## Objetivo

Identificar patrones de producción a nivel nacional, provincial y por pozo, con el fin de detectar oportunidades de inversión y señales de alerta operativa en el sector hidrocarburífero argentino.

Las preguntas que guían el análisis son:

- ¿Cómo evolucionó la producción de petróleo y gas mes a mes durante 2024 y 2025?
- ¿Qué provincias y empresas concentran la mayor producción?
- ¿Cuál es el peso del recurso no convencional (Vaca Muerta) sobre el total?
- ¿Qué pozos son más eficientes y qué características comparten?
- ¿Qué pozos representan un costo operativo elevado en relación a su producción?
- ¿Cómo evolucionaron estos indicadores entre 2024 y 2025?

## Tecnologías utilizadas

- Python 3.13
- Pandas
- Jupyter Notebook
- Power BI Desktop

## Estructura del proyecto
hidrocarburos-analisis/
│
├── analyses/
│   ├── 2024/
│   │   ├── notebooks/
│   │   │   ├── 01_exploracion.ipynb
│   │   │   ├── 02_limpieza.ipynb
│   │   │   ├── 03_analisis_general.ipynb
│   │   │   ├── 04_analisis_pozos.ipynb
│   │   │   └── 05_patrones_recomendaciones.ipynb
│   │   └── preparar_powerbi.ipynb
│   │
│   ├── 2025/
│   │   ├── notebooks/
│   │   │   ├── 01_exploracion.ipynb
│   │   │   ├── 02_limpieza.ipynb
│   │   │   ├── 03_analisis_general.ipynb
│   │   │   ├── 04_analisis_pozos.ipynb
│   │   │   └── 05_patrones_recomendaciones.ipynb
│   │   └── preparar_powerbi.ipynb
│   │
│   └── comparativo/
│       └── analisis_comparativo.ipynb
│
├── data/
│   ├── raw/
│   │   ├── 2024/
│   │   │   └── produccin-de-pozos-de-gas-y-petroleo-2024.csv
│   │   └── 2025/
│   │       └── produccin-de-pozos-de-gas-y-petroleo-2025.csv
│   └── processed/
│       ├── 2024/
│       │   ├── datos_limpios.csv
│       │   ├── analisis_pozos.csv
│       │   ├── declive_pozos.csv
│       │   ├── patrones_pozos.csv
│       │   ├── powerbi_convencional_vs_no.csv
│       │   ├── powerbi_patrones_pozos.csv
│       │   ├── powerbi_produccion_empresa.csv
│       │   ├── powerbi_produccion_mensual.csv
│       │   └── powerbi_produccion_provincia.csv
│       ├── 2025/
│       │   ├── datos_limpios.csv
│       │   ├── analisis_pozos.csv
│       │   ├── declive_pozos.csv
│       │   ├── patrones_pozos.csv
│       │   ├── powerbi_convencional_vs_no.csv
│       │   ├── powerbi_patrones_pozos.csv
│       │   ├── powerbi_produccion_empresa.csv
│       │   ├── powerbi_produccion_mensual.csv
│       │   └── powerbi_produccion_provincia.csv
│       └── integrated/
│           ├── variacion_pozos_2024_2025.csv
│           ├── variacion_provincia_2024_2025.csv
│           └── variacion_recurso_2024_2025.csv
│
├── powerbi/
│   └── analisis_hidrocarburos.pbix
│
├── .gitignore
└── README.md

## Dataset

Los datos utilizados provienen del portal de datos abiertos del Ministerio de Energía de la Nación Argentina:

**Producción de petróleo y gas por pozo (Capítulo IV)**
https://datos.gob.ar/dataset/energia-produccion-petroleo-gas-por-pozo-capitulo-iv

Se utilizaron los archivos CSV correspondientes a 2024 y 2025, que contienen el detalle mensual de producción por pozo, yacimiento, concesión y provincia. Los datasets originales no están incluidos en este repositorio por su tamaño. Para reproducir el análisis, descargarlos desde el link anterior y ubicarlos en `data/raw/2024/` y `data/raw/2025/` respectivamente.

## Instalación

Clonar el repositorio:
```bash
git clone https://github.com/SantiAbdal/hidrocarburos-analisis.git
cd hidrocarburos-analisis
```

Instalar dependencias:
```bash
pip install pandas jupyter
```

## Flujo del análisis

El mismo flujo se aplica de forma independiente para 2024 y 2025:

1. **Exploración inicial** — Inspección del dataset: dimensiones, tipos de datos, valores nulos y valores únicos en columnas clave.

2. **Limpieza** — Eliminación de columnas irrelevantes, tratamiento de nulos, corrección de valores negativos, tratamiento de outliers y filtrado de pozos activos.

3. **Análisis general** — Producción total anual, evolución mensual, comparación por provincia y empresa, análisis de concentración de mercado y comparación convencional vs no convencional.

4. **Análisis por pozo** — Ranking de pozos más productivos, eficiencia en relación a inyección y tiempo efectivo de flujo, detección de pozos en declive.

5. **Patrones y recomendaciones** — Clasificación de pozos por rendimiento, identificación de patrones geográficos y operativos en pozos de alto y bajo rendimiento.

6. **Comparativo 2024 vs 2025** — Análisis integrado de ambos años para identificar tendencias, variaciones en la concentración de mercado y evolución del recurso no convencional.

## Principales hallazgos

### 2024
- Neuquén concentra el 58% de la producción de petróleo y el 68% del gas, impulsado por Vaca Muerta.
- El recurso no convencional representa el 55% de la producción de petróleo y el 63% del gas.
- Solo 4 empresas (YPF, Pan American Energy, Vista Energy y Pluspetrol) concentran el 77% de la producción nacional.
- Los pozos de alto rendimiento no requieren inyección de agua, mientras que los de bajo rendimiento inyectan en promedio 52 m³ para producir cantidades mínimas.
- Se identificaron 6.232 pozos con caída de producción mayor al 30% entre el primer y segundo semestre.

### 2025
- El recurso no convencional creció al 62.6% de la producción de petróleo y al 63.7% del gas.
- La producción total de petróleo creció un 2.74% respecto a 2024.
- La producción total de gas cayó un 6.34% respecto a 2024.
- El no convencional de petróleo creció un 15.80%, confirmando la aceleración de Vaca Muerta.
- Shell Argentina ingresó al top 5 de empresas productoras.
- Se detectaron valores anómalos de inyección de gas en pozos de QUINTANA E&P, documentados y tratados en la limpieza.

### Comparativo 2024 vs 2025
- El 95% de los pozos activos en 2024 continuaron operando en 2025, con 1.832 cierres y 982 nuevos pozos.
- El crecimiento total de petróleo (+2.74%) se explica por pozos no convencionales de alto rendimiento que compensan el declive generalizado en pozos convencionales existentes.
- La mediana de variación en pozos continuos es -19% en petróleo y -22.76% en gas — la mayoría de los pozos perdieron productividad.
- El declive es generalizado en todas las provincias, con Neuquén mostrando una mediana de -25% compensada por su alto componente no convencional.
- El no convencional gana peso año a año — pasó del 55% al 62.6% en petróleo en un solo año.
- La concentración de mercado se mantiene alta pero con leve diversificación — pasó de 4 a 5 empresas para concentrar el 77% de la producción.

## Dashboard

El dashboard interactivo desarrollado en Power BI incluye tres páginas:

**2024**
- Producción mensual de petróleo y gas
- Producción de petróleo y gas por provincia
- Producción de petróleo y gas por empresa
- Convencional vs No Convencional — petróleo y gas
- Productividad promedio por rendimiento de pozo

**2025**
- Mismos indicadores que 2024 con datos actualizados

**Comparativo**
- Producción total de petróleo 2024 vs 2025
- Producción total de gas 2024 vs 2025
- Producción no convencional de petróleo 2024 vs 2025
- Producción no convencional de gas 2024 vs 2025
- Variaciones porcentuales entre años

El archivo `.pbix` está disponible en la carpeta `powerbi/`.

## Trabajo futuro

- Incorporar datos de precios para calcular rentabilidad real por pozo
- Profundizar el análisis de declive por formación productiva identificando qué formaciones muestran mayor caída sostenida

## Autor

Santiago Abdala — [LinkedIn](https://www.linkedin.com/in/santiago-abdala-170982340) · [GitHub](https://github.com/SantiAbdal)