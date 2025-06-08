## Temas
1. **Weather data pipeline.** 
	**==Objetivos:==** 
	Fase 1:
	- almacenar datos historicos del clima en Cuba en lo últimos 20 años. 
	- proveer análisis por períodos de tiempo (que se puedan escoger dinámicamente) en diversos parámetros: precipitaciones, temperatura, cantidad de ciclones, etc.
	- proveer las predicciones del clima para el día. 
	Fase 2: 
	- realizar análisis sobre la intensidad de los huracanes.
	- incluir análisis similares a los de Cuba para otros países del caribe como: ....
	- mejoras de herramientas y técnicas de procesamiento y visualización. 
	- introduccion de manejo de usuarios.
	Fase 3:
	- incluir un sistema streaming que dada una ubicación, pueda proveer en tiempo real el clima actual y las predicciones para hasta dentro de 3 días. Este sistema será a través de un chatbot manejado por un LLM. Este chatbot solo debe responder preguntas relacionadas con predicciones del clima. Su tarea es si el mensaje del ususario pide por información del clima de hoy o los próximos 3 días determinar la ubicación e iniciar (el llm no tiene q iniciarlo) una busqueda de predicciones en diversas fuentes. Ese resultado es procesado por el modelo para responder al usuario, contrastando las varias fuentes. Los resultados de las varias fuentes podrían ser previamente procesados, para determinar la media o la mediana; o todo el analisis lo puede efectuar un LLM.
	- que los usuarios puedan guardar queries historicas que hayan hecho y se les pueda hacer CRUD (esto podría pasar a fase 2).
	- Servir la mayoría o todas las funcionalidades (o una modificación de ellas) a través de un API con API-key

2. **Aviation analysis pipeline.** 
	**==Objetivos:==** 
	Fase 1:
	- almacenar datos historicos de vuelos, aeropuertos y situacion meteorologica en loa aeropuertos de los últimos 10 años.
	- proveer dado un aeropuerto los vuelos planeados de las proximas 24 horas
	- proveer analisis por períodos de tiempo de diversos parametros.
	Fase 2:
	- Modelo de ML para predecir retrasos de un tipo de vuelo en especifico o de un aeropuerto dado el clima.
	- incluir datos de nuevas regiones
	- mejoras de herramientas y técnicas de procesamiento y visualización
	Fase 3:
	- Monitoreo de desempeño del modelo de ML en producción: Panel de visualización que permita a los usuarios visualizar predicciones del modelo de ML en tiempo real. Implementar un módulo que registre métricas del modelo (precisión, recall) y compare predicciones con datos reales post-vuelo. Integrar esta información en el dashboard para análisis continuo (usando Prometheus/Grafana o herramientas similares). 
    - Implementación de Microservicios y API: Ofrecer endpoints del API que devuelvan resultados en formatos JSON y CSV, integrando filtros dinámicos (fechas, aeropuertos, rangos de retraso). Además de un endpoint para exponer la predicción de retrasos. Separar claramente frontend, backend (db) y el servicio de predicción en microservicios independientes.
    - Integración de un sistema de alertas basado en ML: Implementar un servicio que, utilizando el modelo de predicción de retrasos, genere alertas automáticas (vía email o notificación en el dashboard) cuando se detecten retrasos probables en vuelos específicos o aeropuertos seleccionados por el usuario. Estos parametros seleccionados por el usuario deben tener un crud completo. 
	
## Fase 1
Orientación: semana 3 o 4.
- Ciclo completo dada una o más fuentes de datos, pasando por proceso de ingestión, almacenamiento, análisis y transformación de datos, servicio de datos y analíticas sobre ellos para responder a la problemática planteada.
- Se debe utilizar un sistema de almacenamiento de medio o alto nivel que se adecue al tipo de datos y su flujo particular para la problemática que está siendo tratada.
- se evalúa la modularidad de la implementación y su escalabilidad.
- se requiere utilizar un sistema de control de versiones como git, idealmente con issues y uno o más commits por issue. Se puede tener más de una rama.
- el sistema tiene que estar desplegado en la nube, como mínimo en un sistema como render.
Entrega: Martes de la semana 7.
Revisión: semana 8. o 7
## Fase 2
Orientación: semana 7.
- Se incluyen nuevos requerimientos de herramientas sobre todo respecto al almacenamiento, procesamiento y visualización. 
- El sistema ahora debe tener manejo de usuarios.
- El acceso al sistema de almacenamiento debe ser mediante un ORM o herramienta similar.
Revisión: semana 10.
## Fase 3
Orientación: semana 10.
- Se debe incluir CI/CD, IaC, y otras técnicas de DevOps (DataOps). Además de tener alguna arquitectura de pruebas automatizados.
- Se incluyen requerimientos de nuevas fuentes, nuevos procesamiento, Inverse ETL, etc; así como de visualización y mejora de la experiencia de usuario tanto con su frontend como con el serving de su sistema (que debe ser un API).

Revisión: final del curso.
