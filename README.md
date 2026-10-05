# Taller 7: Construcción de un índice para entender cambios en la economía global antes y después del COVID

Repositorio del equipo consultor para el encargo del fondo de inversión interesado en analizar la evolución y desempeño de tres sectores de la economía global entre 2015 y 2025. El objetivo es construir índices sectoriales transparentes a partir de datos de mercado, evaluar el impacto de distintas reglas de ponderación (precio vs. volumen), comparar retornos y volatilidad entre el periodo previo y posterior al COVID-19, y estructurar una recomendación de inversión clara y fundamentada.

## Equipo consultor

| Integrante | Rol |
| :--- | :--- |
| *Samuel Dussán Fonseca* | *Líder del proyecto y enlace con el fondo* |
| *Chari Valeria Reyes Arias* | *Especialista en datos y reproducibilidad* |
| *Mariana Forigua Tamayo* | *Analista cuantitativo* |
| *Santiago Gómez Ibague* | *Especialista en visualización y comunicación* |
| *María Paula Monroy Molina* | *Analista cuantitativo / Apoyo en investigación* |

> Los roles definen una responsabilidad principal, no dividen el taller en partes aisladas. Todos los productos son responsabilidad conjunta y cualquier integrante puede ser seleccionado como portavoz en la Sesión 3.

## Descripción del encargo

El fondo de inversión requiere entender la evolución sectorial comparada entre 2015 y 2025, analizando el comportamiento antes y después del impacto del COVID-19 para orientar la asignación de sus recursos. Puntualmente, se busca responder a las siguientes preguntas clave:

1. **Construcción y ponderación de índices:** ¿Cómo se comportan los índices sectoriales según las distintas reglas de ponderación (volumen inicial vs. precio inicial) y qué implicaciones tiene la regla de ponderación para la lectura del fondo?
2. **Resumen y comportamiento:** ¿Qué revelan los retornos diarios ponderados, su dispersión, *outliers* y la evolución acumulada normalizada (base 100 en 2015) sobre la dinámica de cada sector?
3. **Comparación pre y post COVID (2015 vs. 2025):** ¿Existen diferencias estadísticamente significativas en términos de retorno promedio, desviación estándar e intervalos de confianza (95%) entre 2015 y 2025?
4. **Recomendación estratégica:** ¿Qué sector(es) debería el fondo priorizar, mantener bajo observación o evitar, considerando el desempeño acumulado, la dispersión, los eventos extremos y las limitaciones metodológicas del análisis?

El análisis se basa en datos de precios de cierre diario y volúmenes de transacción (2015–2025) obtenidos mediante Bloomberg, estructurados y procesados rigurosamente en Excel, siguiendo la metodología de *Doing Economics* (CORE Econ, Cap. 10.2).

# Estructura del repositorio
```text
TALLER_7_INDICES_COVID/
├── Datos_y_Analisis/
│   └── Raw_Data_taller 7.xslx      # Libro de Excel dinámico, verificado y reproducible
│   └── Taller_7_Documento              # Documento pdf con respuesta a las preguntas del taller
├── Presentacion/
│   └── Presentación Taller 7           # Presentación ejecutiva para el cliente (Sesión 3)
│   └── .gitignore                      # Archivo de texto encargado de evitar la creación de archivos temporales                        
└── README.md                           # Documentación principal del proyecto
```

## Reproducibilidad

* Todo el análisis se ejecuta y procesa dinámicamente en Excel a través de `Datos_y_Analisis/taller7_indices_fondo.xlsx`.
* Ningún resultado depende de ingreso manual de valores (*hardcoding*) ni edición directa sin fórmulas.
* Para reproducir y auditar el análisis completo: abrir el libro de Excel y seguir la secuencia de pestañas etiquetadas de la Parte 1 a la Parte 3.
* La descarga de datos de precios y volúmenes se conecta mediante la integración Excel-Bloomberg.
* Todas las tablas, gráficos de distribución e intervalos de confianza generados se guardan y referencian en el libro de Excel para ser verificados desde `Presentacion/taller7_briefing.pptx`.

## Contenido del análisis

Parte 1 — Construcción de los índices: Selección de 3 sectores económicos (10 acciones por sector), descarga de precios de cierre diario y volúmenes de transacción (2015–2025) desde Bloomberg. Construcción de pesos según el volumen de transacciones inicial (enero 2015) y comparación con pesos según el precio inicial. Explicación de las implicaciones metodológicas de la regla de ponderación para la toma de decisiones del fondo de inversión.

Parte 2 — Resumen y comportamiento de los datos: Caracterización teórica del universo de activos representados y sus limitaciones. Cálculo de retornos aritméticos diarios por activo y retornos diarios ponderados de los tres índices (2015–2025). Análisis gráfico de dispersión y valores atípicos mediante gráficos de caja y bigotes (boxplots), análisis de forma de distribución mediante histogramas, y evolución acumulada mediante gráfico de líneas normalizado a base 100 (enero de 2015).

Parte 3 — Una comparación antes y después del COVID: 2015 vs. 2025: Cálculo de desviación estándar y número de observaciones (n) para 2015 y 2025. Estimación de intervalos de confianza al 95% para los retornos ponderados utilizando la función CONFIDENCE.T. Construcción de gráficos de barras comparativos con barras de error. Interpretación cuantitativa de cambios pre y post COVID (distinguiendo evidencia empírica de afirmaciones causales) y formulación de la recomendación final de inversión (priorizar, observar o evitar sectores) con al menos una cautela metodológica.

## Contribuciones individuales

Samuel Dussán Fonseca — Líder del proyecto y enlace con el fondo
* Dirección general del proyecto, creación y gestión del repositorio de GitHub (`.gitignore` y `README.md`), velando por el cumplimiento de estándares de reproducibilidad y versionamiento.
* Co-diseño, estructura y maquetación de la presentación ejecutiva en PowerPoint (`Presentación Taller 7`), adaptando la narrativa para el cliente.
* Desarrollo técnico y redacción del análisis cuantitativo de la pregunta 1.3 (implicaciones metodológicas de las reglas de ponderación) y la pregunta 2.5 (comportamiento, dispersión y dinámicas sectoriales).
* Supervisión de la coherencia entre el libro de Excel, cálculo para los pesos fijos por volumen, precio y los entregables ejecutivos del proyecto.

Chari Valeria Reyes Arias - Especialista en datos y reproducibilidad
* Extracción, depuración y estructuración de las series históricas de datos diarios de precios de cierre y volúmenes (2015–2025) obtenidas desde Bloomberg Terminal.
* Construcción conjunta de las visualizaciones de distribución en Excel (`taller7_indices_fondo.xlsx`), elaborando los gráficos de caja y bigotes para la detección de *outliers* e histogramas de frecuencias.
* Protocolo de auditoría de reproducibilidad para asegurar la ausencia de valores quemados (*hardcoding*) en el libro de trabajo.
* Validación y verificación continua de la consistencia de los datos entre los distintos sectores para prevenir inconsistencias y fechas faltantes en las series temporales.

Mariana Forigua Tamayo — Analista cuantitativo
* Liderazgo técnico en la estructuración de los modelos cuantitativos del taller según la metodología del proyecto empírico de CORE Econ (Cap. 10.2).
* Desarrollo de la arquitectura de cálculo en Excel para los pesos fijos por volumen y precio, las series de retornos diarios ponderados e índices normalizados base 100 (`1.2_Pesos_y_Ponderaciones` y `1.3_Indices_y_Retornos`).
* Co-construcción de los gráficos de evolución temporal y trayectorias sectoriales acumuladas.
* Apoyo general y acompañamiento continuo a todos los integrantes del grupo en el desarrollo integral del proyecto.

Santiago Gómez Ibague — Especialista en visualización y comunicación
* Liderazgo en el diseño visual, maquetación y jerarquización de la información para el *deck* ejecutivo de la presentación en PowerPoint (`Presentacion Taller 7`).
* Transformación de tablas estadísticas, estimaciones cuantitativas e intervalos de confianza en recursos gráficos de alto impacto para la Sesión 3.
* Estandarización de la identidad visual y formato de los materiales de apoyo del equipo.
* Redacción de la "Presentación Taller 7" final.

María Paula Monroy Molina — Analista cuantitativo / Apoyo en investigación
* Ejecución de las pruebas estadísticas de la Parte 3, calculando desviaciones estándar e intervalos de confianza al 95% mediante la función `CONFIDENCE.T` para los periodos 2015 y 2025.
* Consolidación del análisis comparativo estructural pre y post COVID-19 para evaluar diferencias estadísticamente significativas entre ambos periodos.
* Redacción de las consideraciones finales, delimitación de cautelas metodológicas y formulación de la recomendación estratégica de inversión.

## Referencias

- CORE Econ. (2021). *Doing Economics: Empirical Projects in Economics*. Capítulo 10: *Measuring changes in the economy: Index numbers*. Disponible en: https://books.core-econ.org/doing-economics/book/text/10-02.html
- Datos de mercado y precios de cierre de renta variable recuperados mediante **Bloomberg Terminal** (2015–2025).
