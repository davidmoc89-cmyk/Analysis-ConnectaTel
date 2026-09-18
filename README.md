ConnectaTel – Análisis de Clientes – Sprint 7

Este repositorio contiene el análisis realizado durante el Sprint 7 del caso ConnectaTel, una empresa de telecomunicaciones en Latinoamérica.

Los datos cubren 4,000 clientes y 40,000 eventos de uso registrados durante 2024, con valores faltantes, sentinels, fechas imposibles y outliers que simulan problemas reales de calidad en datos de telecomunicaciones.

📂 Contenido del repositorio
notebooks/connectatel_analysis.ipynb → Notebook principal con limpieza, perfil estadístico por usuario, distribuciones, outliers, segmentación y conclusiones ejecutivas.
datasets/ → Los tres archivos fuente del análisis:
plans.csv – planes vigentes (2 filas): precio, minutos, mensajes y GB incluidos
users_latam.csv – clientes (4,000 filas): edad, ciudad, fecha de registro, plan, churn
usage.csv – eventos de uso (40,000 filas): llamadas y mensajes de 2024
▶ Cómo abrir el notebook en Google Colab

Haz clic en el siguiente botón:

Open In Colab

O:

Abre el archivo .ipynb en GitHub
Haz clic en Open in Colab

matplotlib

🧠 Objetivo del análisis
Identificar problemas de calidad de datos y corregirlos sin perder información
Construir un perfil estadístico de uso por cliente a partir de 40,000 eventos
Analizar distribuciones, detectar outliers con el método IQR y decidir su tratamiento
Segmentar la base por nivel de uso y por grupo de edad
Generar insights accionables sobre la oferta de planes y la retención de clientes

📊 Hallazgos principales
El sentinel -999 en 55 edades hacía parecer que la edad media era 33.7 años. La real es 48.1: la base es madura, no joven.
La edad no predice el consumo. Los tres grupos de edad consumen prácticamente lo mismo y contratan Premium en la misma proporción.
El nivel de uso sí discrimina: Uso medio 73.58%, Bajo uso 19.48%, Alto uso 6.95%.
Los planes están sobredimensionados. Solo 17 de 2,595 clientes Básico superan sus 100 minutos incluidos, y ningún cliente Premium se acerca a agotar su plan pese a pagar más del doble.
El churn es mayor en el segmento de alto uso (14.03% contra 11.65% general), un patrón contraintuitivo que merece investigación.
