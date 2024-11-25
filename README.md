# Prevalencia de siniestros viales en CABA (Buenos Aires)

<div align="center">
    <img src="https://github.com/jdbaquero84/Prevalencia-de-siniestros-viales-en-CABA-Buenos-Aires-/blob/main/imagen1.jpg" alt="Descripción de la Imagen 1" width="200"/>
    <img src="https://github.com/jdbaquero84/Prevalencia-de-siniestros-viales-en-CABA-Buenos-Aires-/blob/main/imagen2.jpg" alt="Descripción de la Imagen 2" width="200"/>
    <img src="https://github.com/jdbaquero84/Prevalencia-de-siniestros-viales-en-CABA-Buenos-Aires-/blob/main/imagen3.png" alt="Descripción de la Imagen 3" width="200"/>
</div>

## Resumen

La Ciudad de Buenos Aires, como núcleo urbano dinámico, experimenta un flujo vehicular constante que, en ocasiones, se traduce en un elevado número de accidentes de tránsito. Este estudio tiene como objetivo analizar un conjunto de datos detallados sobre siniestros viales ocurridos en la ciudad en el periodo 2016-2021, con el fin de identificar los factores de riesgo. Se buscará determinar las zonas con mayor incidencia de accidentes, los horarios pico y los tipos de vehículos más involucrados. Los resultados de esta investigación servirán como base para diseñar estrategias de seguridad vial más focalizadas y basadas en evidencia.

## Tecnologías Utilizadas

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Power BI](https://img.shields.io/badge/PowerBI-F2C811?style=for-the-badge&logo=power-bi&logoColor=black)

## Enfoque del análisis

Las variables consideradas determinantes para el análisis se seleccionaron en función de tratar de responder a los siguientes interrogantes:
- **¿Cuándo hay mayor incidencia?** ¿Cuándo prevenir?
- **¿Cuál es el perfil de las víctimas y victimarios?** ¿Población más afectada?
- **¿En qué comunas hay más ocurrencia?** Lugares

## Modelo de econometría espacial

El código para el modelo de econometría espacial está incluido en el análisis exploratorio de datos (EDA). Se ha implementado para analizar los accidentes de tránsito en Buenos Aires, proporcionando una base robusta para comprender los patrones espaciales y temporales en los datos de víctimas.

### ¿Qué es un modelo de econometría espacial?

Un modelo de econometría espacial es una herramienta estadística utilizada para analizar y comprender los datos que tienen una dimensión geográfica. Estos modelos no solo consideran la relación entre las variables tradicionales sino también cómo estas relaciones varían en el espacio. La econometría espacial es crucial en estudios donde los datos espaciales presentan autocorrelaciones, es decir, donde las observaciones cercanas entre sí en el espacio tienden a estar relacionadas. Esta técnica ayuda a identificar patrones espaciales, como la concentración de fenómenos en ciertas áreas geográficas, y es esencial en la planificación urbana, economía regional, y estudios ambientales.

Los modelos de econometría espacial utilizan varias formas de modelar las dependencias espaciales, incluyendo modelos de regresión espacial

## Resumen del Modelo

El modelo de regresión espacial ajustado mediante el método de máxima verosimilitud se centró en la variable dependiente `N_VICTIMAS`, con un total de 704 observaciones. El **Log likelihood** del modelo es -20.1886, un indicador de qué tan bien el modelo ajusta los datos. Una pseudo R-cuadrada espacial de 0.0257 sugiere que el modelo espacial captura cierta variabilidad en los datos, aunque no de manera sobresaliente. La varianza del sigma (sigma cuadrada) es de 0.0619, lo que indica que los errores del modelo son relativamente pequeños, lo que sugiere una buena precisión en las predicciones del modelo.

## Coeficientes del Modelo

El término constante tiene un coeficiente de 1.03075, altamente significativo (p < 0.0001), lo que indica un impacto considerable en el número de víctimas. En contraste, la variable `SEXO` presenta un coeficiente de 0.00856, que no es estadísticamente significativo (p = 0.70594), sugiriendo que el género no tiene un impacto considerable en el número de víctimas. Por otro lado, la variable `EDAD` tiene un coeficiente negativo (-0.00068), lo que indica que a mayor edad, menor el número de víctimas, aunque esta relación no es significativa (p = 0.18070).

## Impacto de la Franja Horaria

La variable `HH` (franja horaria) tiene un coeficiente de -0.00424, que es significativo (p = 0.00316). Esto sugiere que a medida que aumenta la franja horaria, el número de víctimas disminuye. Este hallazgo es importante para entender cómo las diferentes franjas horarias impactan la frecuencia de los accidentes de tránsito. El coeficiente espacial de la variable `N_VICTIMAS` (`W_N_VICTIMAS`) es 0.01340, también significativo (p < 0.0001), lo que indica que hay una fuerte correlación espacial en el número de víctimas; es decir, los accidentes de tránsito tienden a agruparse en ciertas áreas.

## Interpretación de los Impactos Espaciales

Los impactos espaciales directos e indirectos muestran cómo las variables afectan tanto las ubicaciones específicas como sus vecinas. Por ejemplo, el impacto total de la variable `SEXO` es 0.0087, mientras que el de `EDAD` es -0.0007, y el de `HH` es -0.0043. Estos valores indican que, aunque `SEXO` y `EDAD` no tienen un impacto significativo individualmente, la franja horaria (`HH`) tiene un impacto negativo moderado en el número de víctimas. En resumen, el modelo resalta la importancia de considerar factores espaciales y temporales para entender y mitigar los accidentes de tránsito.

## KP1’s

Se definen tres KPI clave para el análisis de accidentes de tránsito: el total de víctimas, el promedio de víctimas y el número máximo de víctimas. El KPI del total de víctimas proporciona una visión global del impacto total en un periodo determinado, mientras que el KPI del promedio de víctimas ofrece una perspectiva sobre la incidencia promedio, permitiendo identificar tendencias generales. Finalmente, el KPI del máximo número de víctimas destaca los picos de incidentes, ayudando a identificar periodos de alta criticidad y concentrar esfuerzos en la prevención. Estos KPI son esenciales para una comprensión integral y estratégica de los patrones de accidentes y la planificación de medidas preventivas efectivas.

## Conclusiones

Entre 2016 y 2021, se ha observado una tendencia notable en los accidentes de tránsito en Buenos Aires. Durante este periodo, se registró una disminución significativa en los incidentes durante la pandemia y la pospandemia, lo que puede atribuirse a las restricciones de movilidad y cambios en las dinámicas diarias. Sin embargo, en términos agregados, los días de mayor incidencia de accidentes son de viernes a lunes. Este patrón puede estar relacionado con la mayor actividad económica y social durante estos días.

La distribución de los accidentes varía considerablemente entre comunas, estando estrechamente ligada a la actividad económica local. Las franjas horarias más críticas también muestran variaciones según la comuna. En términos agregados, diciembre es el mes con mayor prevalencia de accidentes, posiblemente debido al incremento de actividades sociales y laborales propias del fin de año. La mañana, específicamente entre las 5 y las 10, es el periodo con más accidentes, correlacionándose con los horarios laborales y la puntualidad en los desplazamientos.

El perfil de las víctimas ofrece otro aspecto crucial a considerar. Más del 75% de los afectados son hombres, abarcando las categorías de joven adulto, adulto y anciano. Estas víctimas suelen transportarse en motos, carros o como peatones, reflejando una mayor exposición al riesgo en estos modos de transporte. La predominancia masculina en los accidentes puede implicar la necesidad de estrategias de seguridad vial específicas para estos grupos demográficos.

Las zonas más afectadas por los accidentes son las comunas 1, 4, 9, 8 y 7, con una alta concentración de incidentes en las avenidas principales. Esto sugiere que los puntos de alta actividad vehicular y peatonal son especialmente vulnerables, y enfatiza la necesidad de medidas de seguridad vial más estrictas y eficientes en estas áreas. La identificación de estos patrones proporciona una base sólida para desarrollar políticas y acciones preventivas más efectivas en la ciudad.

## Recomendaciones

1. **Implementación de Estrategias de Control de Tráfico en Horarios Críticos**:
   - Dado que los accidentes de tránsito tienen una mayor incidencia de viernes a lunes y entre las 5 y las 10 de la mañana, se recomienda la implementación de estrategias de control de tráfico durante estos periodos. Esto puede incluir el aumento de la presencia policial para supervisar y controlar el flujo vehicular, así como la instalación de más semáforos y señales de tránsito para guiar adecuadamente a los conductores.

2. **Campañas de Concienciación Específicas**:
   - Las campañas de concienciación deben enfocarse en los grupos demográficos más afectados: hombres, especialmente aquellos en categorías de joven adulto, adulto y anciano. Además, las campañas deben destacar la importancia de la seguridad para aquellos que utilizan motos, carros y como peatones. Iniciativas educativas pueden ser llevadas a cabo en centros comunitarios, lugares de trabajo y a través de plataformas digitales para alcanzar un público más amplio.

3. **Mejoras en la Infraestructura Vial de Comunas Críticas**:
   - Las comunas 1, 4, 9, 8 y 7, que presentan una alta concentración de accidentes, requieren mejoras específicas en la infraestructura vial. Esto podría incluir la creación de más pasos peatonales, la instalación de barandillas de seguridad, y la mejora de la iluminación en las avenidas principales. Además, la implementación de zonas de reducción de velocidad y cámaras de control de velocidad pueden ayudar a reducir los accidentes en
