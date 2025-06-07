# presentacion-sinadef
Propuesta de Proyecto Final Le Wagon (Batch 1959 Online)
Título del Proyecto: plataforma Interactiva para el Análisis Predictivo de Riesgos de Mortalidad en Perú.**
Equipo: 4 personas (Jhon Wilber Ajata Ascarrunz y 3 compañeros)
Fecha: 7 de Junio de 2025
1. Resumen Ejecutivo / Visión del Proyecto (Para el Pitch)
•	Problema: Las decisiones críticas en salud pública en Perú a menudo carecen de un análisis profundo y accesible de los patrones de mortalidad. Esto dificulta la focalización efectiva de recursos y estrategias preventivas para reducir muertes evitables y proteger a las poblaciones vulnerables.
•	Dataset: Utilizaremos la base de datos oficial anonimizada del SINADEF (fallecidos_sinadef.csv), que contiene 1,110,168 registros y 31 columnas con información demográfica, geográfica y causas de muerte (CIE-10) de los fallecidos en Perú.
•	Solución Propuesta (Nuestra Visión): Desarrollaremos "SINADEF Insight", una plataforma web interactiva (construida con Streamlit) que: 
1.	Visualizará patrones y tendencias de mortalidad de forma clara e intuitiva.
2.	Incorporará un modelo predictivo para identificar perfiles demográficos y geográficos con mayor riesgo asociado a categorías amplias de causas de muerte.
3.	Generará insights accionables para que gestores de salud pública, investigadores y ciudadanos puedan tomar decisiones informadas, focalizar intervenciones y, en última instancia, contribuir a mejorar la salud pública en el país.
o	Este proyecto se alinea fuertemente con mi (Jhon Wilber) formación en Ingeniería Estadística, mi tesis en optimización de salud pública regional mediante modelos predictivos, y mi vocación por generar impacto social a través de los datos.
2. Problema Detallado a Resolver
La mortalidad es un indicador clave de la salud de una nación. Si bien Perú cuenta con el Sistema Informático Nacional de Defunciones (SINADEF), la explotación de esta rica fuente de datos para generar inteligencia accionable para la salud pública a menudo es limitada o no es fácilmente accesible para todos los tomadores de decisiones y la ciudadanía. Existe una brecha entre la recolección de datos y su uso efectivo para:
•	Identificar con precisión las principales causas de muerte y cómo varían por región, demografía y tiempo.
•	Detectar grupos poblacionales desproporcionadamente afectados por ciertas enfermedades o causas externas.
•	Informar el diseño de políticas y programas de prevención y control de enfermedades de manera oportuna y basada en evidencia local.
•	Monitorear el impacto de las intervenciones de salud pública.
3. Objetivos del Proyecto
•	Objetivo Principal: 
o	Desarrollar y desplegar una aplicación web interactiva ("SINADEF Insight") que permita la exploración, visualización y análisis predictivo de los datos de mortalidad del SINADEF.
•	Objetivos Secundarios: 
1.	Realizar un Análisis Exploratorio de Datos (EDA) exhaustivo para descubrir patrones, tendencias y correlaciones.
2.	Procesar y categorizar los códigos de causa de muerte (CAUSA A (CIE-X), etc.) para facilitar el análisis agregado.
3.	Construir y evaluar un modelo de machine learning para identificar perfiles de riesgo asociados a categorías amplias de causas de muerte.
4.	Presentar los hallazgos de manera clara y visualmente atractiva a través del dashboard interactivo.
5.	Documentar el proceso, el código y los hallazgos del proyecto.
4. Dataset
•	Fuente Primaria: Base de datos anonimizada de defunciones del SINADEF, contenida en el archivo fallecidos_sinadef.csv.
•	Estructura: El dataset consta de 1,110,168 registros y 31 columnas, de las cuales las más relevantes para el proyecto son: 
o	Variables Demográficas: TIPO SEGURO, SEXO, EDAD, TIEMPO EDAD, ESTADO CIVIL, NIVEL DE INSTRUCCIÓN.
o	Variables Geográficas: COD# UBIGEO DOMICILIO, DEPARTAMENTO DOMICILIO, PROVINCIA DOMICILIO, DISTRITO DOMICILIO.
o	Variables Temporales: FECHA, AÑO, MES.
o	Variables de Contexto de la Defunción: TIPO LUGAR, INSTITUCION, MUERTE VIOLENTA, NECROPSIA.
o	Variables de Causa de Muerte: DEBIDO A (CAUSA A) hasta (CAUSA F) y, fundamentalmente, sus códigos estandarizados CAUSA A (CIE-X) hasta CAUSA F (CIE-X).
•	Consideraciones: Se requerirá un preprocesamiento significativo para unificar EDAD y TIEMPO EDAD en una sola variable numérica, así como para agrupar los códigos CIE-X en categorías manejables.
5. Metodología y Plan de Trabajo (para equipo de 4)
•	Fase 1: Comprensión, Adquisición y Limpieza de Datos (1 Líder, apoyo de 1) 
o	Investigación a fondo de la estructura de los códigos CIE-10 y definición de categorías relevantes para el análisis.
o	Ingeniería de Características: Creación de una variable de edad numérica unificada a partir de EDAD y TIEMPO EDAD. Agrupación de CAUSA A (CIE-X) en categorías. Estandarización de variables categóricas como NIVEL DE INSTRUCCIÓN o ESTADO CIVIL.
o	Limpieza de datos: manejo de valores faltantes y corrección de tipos de datos (FECHA, AÑO, MES).
•	Fase 2: Análisis Exploratorio de Datos (EDA) (1 Líder, apoyo de 1) 
o	Análisis univariado y bivariado. Visualización de patrones de mortalidad por edad, sexo, ubicación (DEPARTAMENTO DOMICILIO), tiempo y causa.
o	Análisis específico de la variable MUERTE VIOLENTA en relación con otras características demográficas.
•	Fase 3: Modelado Predictivo (Enfoque: Perfiles de Riesgo) (1 Líder, apoyo de 1) 
o	Definición de Variable Objetivo: Categoría amplia de causa de muerte (ej. Cardiovascular, Cáncer, Infecciosa/Respiratoria, Externa, Otras).
o	Selección de Features: Se utilizarán las variables demográficas, geográficas y temporales procesadas, así como variables de contexto como TIPO SEGURO, TIPO LUGAR, etc.
o	Entrenamiento de Modelos: Probar algoritmos como Regresión Logística, Random Forest, Gradient Boosting.
o	Evaluación y Selección: Métricas apropiadas (F1-Score, AUC-ROC), validación cruzada. Manejo de desbalance de clases si existe.
o	Interpretabilidad: Uso de técnicas como SHAP para entender qué factores definen los perfiles de riesgo.
•	Fase 4: Desarrollo de la Aplicación Web (Streamlit) (1 Líder, apoyo de todos) 
o	Diseño de la interfaz de usuario (UI) y experiencia de usuario (UX) del dashboard.
o	Implementación de filtros interactivos.
o	Integración de las visualizaciones del EDA y de los resultados del modelo predictivo.
o	Pruebas y despliegue (ej. en Streamlit Cloud).
•	Fase 5: Documentación y Preparación de Presentación Final (Todos) 
o	Elaboración del informe técnico, la presentación visual (enfocada en el pitch) y práctica de la misma.
6. Entregables
1.	Aplicación Web Interactiva "SINADEF Insight": Dashboard desplegado en Streamlit.
2.	Código Fuente: Notebooks de Jupyter/Python con todo el proceso.
3.	Modelo Entrenado: Archivo del modelo predictivo final (ej. .pkl).
4.	Informe Final del Proyecto: Documento detallado.
5.	Presentación Final: Diapositivas para la exposición del proyecto.
6.	Video de Demostración (si es requerido).
7. Tecnologías y Herramientas
•	Lenguaje de Programación: Python
•	Bibliotecas Principales: 
o	Manipulación de Datos: Pandas, NumPy
o	Visualización: Matplotlib, Seaborn, Plotly Express
o	Machine Learning: Scikit-learn, XGBoost, LightGBM, SHAP
o	Aplicación Web: Streamlit
•	Entorno de Desarrollo: Jupyter Notebooks/Lab, VS Code
•	Control de Versiones: Git, GitHub
8. Factores de Riesgo y Plan de Mitigación
•	Complejidad de los Códigos CIE-10: 
o	Mitigación: Dedicar tiempo inicial a la investigación y validación de las categorías. Empezar con agrupaciones de alto nivel.
•	Calidad de los Datos: 
o	Mitigación: Técnicas de imputación robustas, documentación clara de limitaciones.
•	Definición del Objetivo Predictivo: 
o	Mitigación: Enfocar la predicción en perfiles de riesgo para categorías amplias y accionables, priorizar la interpretabilidad del modelo.
•	Alcance del Proyecto vs. Tiempo del Bootcamp: 
o	Mitigación: Definir un MVP claro para la aplicación. Buena gestión del tiempo y división de tareas.
9. Impacto Esperado y Alineación Estratégica
Este proyecto tiene el potencial de:
•	Proporcionar una herramienta valiosa para la toma de decisiones en salud pública en Perú.
•	Demostrar un ciclo completo de ciencia de datos, desde la limpieza hasta una aplicación interactiva.
•	Contar una historia impactante sobre cómo los datos pueden usarse para el bien social.
