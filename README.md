# sprint7-final-project-telecom-analysis
Análisis de datos y segmentación de clientes de telecomunicaciones con Python. Limpieza de datos, detección de outliers y perfiles de uso.

Análisis de Comportamiento y Segmentación: ConnectaTel 📊
Este proyecto realiza un análisis profundo de los datos de consumo y perfiles de usuario de una empresa de telecomunicaciones para identificar patrones de uso, limpiar inconsistencias y proponer estrategias de negocio basadas en datos.

🎯 Objetivo del Proyecto
El objetivo principal es procesar y limpiar datos crudos de telecomunicaciones para construir perfiles de usuario que permitan:

Sanear errores de captura (valores sentinel y fechas imposibles).

Analizar la distribución del consumo (llamadas y mensajes).

Segmentar a los clientes según su demografía y nivel de actividad.

Identificar oportunidades comerciales (Upselling) basadas en el uso excedente.

📂 Datasets Utilizados
El análisis se basa en tres tablas principales:

users: Datos demográficos (edad, ciudad, fecha de registro, plan).

usage: Registros detallados de consumo (tipo de servicio, duración, longitud de mensajes).

plans: Información sobre los límites y costos de los planes "Básico" y "Premium".

🛠️ Etapas del Análisis
Carga y Exploración Inicial: Identificación de tipos de datos y valores faltantes.

Limpieza de Datos (Data Wrangling):

Tratamiento de valores sentinel (-999 en edad, ? en ciudad).

Corrección de fechas futuras mediante pd.NaT.

Análisis de nulos bajo la lógica MAR (Missing At Random).

Ingeniería de Características: Agregación de consumos por usuario para obtener totales de mensajes y minutos.

Análisis Estadístico: Detección de outliers mediante el Método del Rango Intercuartílico (IQR).

Segmentación: Clasificación de usuarios en grupos por Edad (Joven, Adulto, Adulto Mayor) y Nivel de Uso (Bajo, Medio, Alto).

Visualización: Histogramas y gráficos de barras para validar la distribución de los segmentos.

🚀 Cómo ejecutar el proyecto
Puedes ejecutar este análisis de dos formas:

Opción A: Google Colab (Recomendado)
Sube el archivo .ipynb a tu Google Drive.

Ábrelo con Google Colaboratory.

Asegúrate de cargar los archivos .csv en la sección de "Archivos" en el panel izquierdo.

Opción B: Entorno Local (Jupyter / VS Code)
Clona este repositorio:

Bash
git clone https://github.com/tu-usuario/nombre-del-repo.git
Instala las librerías necesarias:

Bash
pip install pandas numpy matplotlib seaborn
Ejecuta el comando jupyter notebook en tu terminal.

🔄 Guía de Reproducción
Preparación: Asegúrate de que los nombres de los archivos CSV coincidan con los nombres llamados en el código (users.csv, usage.csv).

Limpieza: Ejecuta las celdas de tratamiento de sentinels; verifica que los nulos en city aumenten tras el reemplazo del signo ?.

Agregación: Al combinar las tablas, verifica que se utilice un left join para no perder usuarios que no tengan registros de consumo.

Visualización: Observa los histogramas; las colas largas hacia la derecha confirmarán la presencia de los "Power Users" (outliers) analizados.
