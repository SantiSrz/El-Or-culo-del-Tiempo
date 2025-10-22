# El-Or-culo-del-Tiempo

https://github.com/SantiSrz/El-Or-culo-del-Tiempo.git

🧩 Fase 1: Preparando los Datos Temporales
Issue 1: Cargar y Explorar el Dataset

Descripción:
Importar el dataset de consumo eléctrico (por ejemplo, Household Power Consumption Dataset). Explorar las columnas, tipos de datos y valores faltantes.

Tareas:

Cargar el dataset con pandas.

Analizar la estructura de los datos.

Identificar valores nulos y rangos de fechas.

Objetivo:
Tener una comprensión general del dataset y asegurar su correcta lectura.

Issue 2: Limpieza y Re-muestreo de Datos

Descripción:
Procesar los datos eliminando o imputando valores faltantes y convertir la frecuencia horaria a diaria.

Tareas:

Rellenar valores faltantes (por ejemplo, con el método forward fill).

Re-samplear los datos para obtener consumo diario (sumatoria o promedio).

Comprobar consistencia temporal de los datos.

Objetivo:
Obtener una serie temporal diaria continua sin valores faltantes.

Issue 3: Visualización y Normalización

Descripción:
Explorar visualmente los patrones de consumo diario y escalar los datos para el entrenamiento de la red.

Tareas:

Graficar el consumo diario a lo largo del tiempo.

Detectar tendencias, estacionalidad y anomalías.

Aplicar MinMaxScaler para escalar los valores entre 0 y 1.

Objetivo:
Preparar los datos limpios y normalizados para construir las ventanas temporales.

🧠 Fase 2: Creando las Ventanas de Tiempo
Issue 4: Crear Función de Ventanas Móviles (Rolling Windows)

Descripción:
Transformar la serie temporal en un conjunto de datos supervisados: entradas (X) y salidas (y).

Tareas:

Definir el parámetro look_back (por ejemplo, 60 días).

Escribir una función que cree secuencias de entrada y etiquetas correspondientes.

Verificar la forma de salida de X e y.

Objetivo:
Tener los datos en formato supervisado para el entrenamiento de la red.

Issue 5: División Cronológica en Entrenamiento y Prueba

Descripción:
Dividir los datos de manera temporal (no aleatoria) para respetar la naturaleza secuencial.

Tareas:

Dividir el dataset en 80% entrenamiento y 20% prueba.

Adaptar las dimensiones para LSTM: (muestras, pasos_de_tiempo, características).

Objetivo:
Obtener los conjuntos X_train, y_train, X_test, y_test listos para el modelo.

Issue 6: Pregunta de Análisis 1

Título:
➡️ ¿Por qué no podemos usar un solo día para predecir el siguiente?

Descripción:
Explicar en un bloque de Markdown la importancia del contexto temporal y cómo las ventanas móviles capturan dependencias temporales.

⚙️ Fase 3: Construyendo y Entrenando la Red LSTM
Issue 7: Definir la Arquitectura del Modelo

Descripción:
Crear el modelo LSTM secuencial en Keras con dos capas LSTM y una capa densa final.

Tareas:

Crear un modelo Sequential() en TensorFlow/Keras.

Añadir dos capas LSTM (50 unidades cada una, la primera con return_sequences=True).

Añadir una capa Dense con una salida.

Objetivo:
Definir correctamente la estructura del modelo recurrente.

Issue 8: Compilar y Entrenar el Modelo

Descripción:
Configurar el modelo con optimizador adam y pérdida mean_squared_error, y entrenarlo.

Tareas:

Compilar el modelo con adam y mse.

Entrenar durante 50–100 épocas.

Guardar el historial de entrenamiento para graficar la pérdida.

Objetivo:
Entrenar el modelo y observar la convergencia del error.

Issue 9: Pregunta de Análisis 2

Título:
➡️ ¿Cómo ayudan las “puertas” internas de una LSTM a recordar u olvidar información?

Descripción:
Responder en un bloque de Markdown explicando cómo las puertas de entrada, olvido y salida controlan el flujo de información.

📊 Fase 4: El Veredicto del Oráculo (Evaluación)
Issue 10: Generar y Visualizar Predicciones

Descripción:
Evaluar el rendimiento del modelo mediante predicciones en el conjunto de prueba.

Tareas:

Generar predicciones usando el modelo entrenado.

Aplicar inverse_transform para devolver a la escala original.

Graficar los valores reales vs. predichos.

Objetivo:
Evaluar visualmente la precisión del modelo y su capacidad para seguir las tendencias.

Issue 11: Análisis de Resultados

Título:
➡️ ¿Qué tan bien sigue la predicción a los datos reales?

Descripción:
Analizar la gráfica de resultados y discutir fortalezas y debilidades del modelo.
Identificar en qué momentos falla más y por qué.

📝 Fase 5: Documentación y Entrega
Issue 12: Redacción del Informe Final (PDF, 2 páginas)

Descripción:
Elaborar un informe sintético con los hallazgos del proyecto.

Estructura del informe:

Introducción: Predicción de la demanda energética y su relevancia.

Metodología: Preparación de datos, ventanas móviles, modelo LSTM.

Resultados: Gráfica de predicciones vs. valores reales.

Conclusión: Reflexión sobre LSTM y sus aplicaciones (ej. lenguaje, clima, finanzas).

Objetivo:
Entregar un documento que comunique de manera clara el proceso y resultados del proyecto.
