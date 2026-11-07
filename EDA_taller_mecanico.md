¡Hola! Qué gusto saludarlos, equipo. Como su docente en esta hermosa disciplina de la Inteligencia Artificial, hoy daré inicio a una sesión práctica clave: el **Análisis Exploratorio de Datos (EDA)** con Python, utilizando `pandas` y `matplotlib`.

Para cualquier modelo de Machine Learning, el EDA es la etapa primordial donde entendemos qué datos tenemos, qué patrones guardan y qué problemas requieren limpieza antes de entrenar un modelo.

---

## Comandos más frecuentes en pandas y matplotlib para EDA

1. **Lectura y exportación:** `pd.DataFrame()`, `df.to_csv()`, `pd.read_csv()`.
2. **Inspección general:** `df.head()`, `df.tail()`, `df.info()`, `df.shape`.
3. **Resumen estadístico:** `df.describe()`, `df.describe(include='object')`.
4. **Valores nulos y duplicados:** `df.isnull().sum()`, `df.duplicated().sum()`.
5. **Conteo de categorías:** `df['columna'].value_counts()`.
6. **Visualización rápida:** `plt.figure()`, `plt.hist()`, `plt.scatter()`, `plt.title()`, `plt.show()`.

---

## Guía Paso a Paso del Desarrollo (`eda_empleados_mecanico.py`)

A continuación verás la secuencia lógica detallada paso a paso para crear el dataset del taller mecánico, guardarlo en un archivo CSV y realizar el análisis exploratorio.

1. **Construir el Diccionario de Datos:** 10 características con 6 registros cada una.
Creamos un diccionario nativo de Python donde cada llave representa una variable del taller mecánico (edad, sueldo, especialidad, etc.) y su valor es una lista con 6 elementos (un registro por cada uno de los 6 empleados).


2. **Convertir a DataFrame y Exportar a CSV:** Creación del archivo empleados_mecanicos.csv.
Transformamos la estructura del diccionario a un `pd.DataFrame` y guardamos los datos físicamente en un archivo `empleados_mecanicos.csv` sin el índice por defecto.


3. **Cargar el Archivo CSV para el EDA:** Simulación del flujo real de trabajo de Machine Learning.
Leemos el archivo `.csv` recién creado con `pd.read_csv()` para simular la importación real de datos antes de un modelo.


4. **Inspección Inicial y Dimensiones:** Conociendo el tipo y forma de nuestros datos.
Visualizamos las primeras filas con `.head()` e inspeccionamos los tipos de variables (`int64`, `float64`, `object`) y nulos con `.info()`.


5. **Estadística Descriptiva:** Medidas de tendencia central y dispersión.
Generamos el resumen numérico con `.describe()` para analizar promedios, desviaciones estándar, cuartiles y rangos del personal.


6. **Filtrado y Análisis Categórico:** Extracción de patrones específicos.
Contamos cuántos empleados hay por especialidad mediante `.value_counts()` y filtramos aquellos con salarios o niveles de experiencia destacados.


7. **Visualización Gráfica con Matplotlib:** Comunicación visual de hallazgos.
Generamos gráficos para representar la distribución del salario (histograma) y la relación entre la experiencia y las reparaciones realizadas (gráfico de dispersión).


---

## Código Python Completo: `eda_empleados_mecanico.py`

```python
# ==============================================================================
# ASIGNATURA: Inteligencia Artificial - 3er Semestre
# TEMA: Análisis Exploratorio de Datos (EDA) en un Taller Mecánico
# ARCHIVO: eda_empleados_mecanico.py
# ==============================================================================

import pandas as pd
import matplotlib.pyplot as plt

# ------------------------------------------------------------------------------
# PASO 1: Crear un diccionario con 10 listas de 6 elementos cada una
# ------------------------------------------------------------------------------
datos_taller = {
    "id_empleado": [101, 102, 103, 104, 105, 106],
    "nombre": ["Carlos", "Ana", "Luis", "Elena", "Jorge", "Sofía"],
    "edad": [28, 35, 42, 29, 50, 31],
    "especialidad": ["Frenos", "Motor", "Diagnóstico", "Eléctrico", "Motor", "Frenos"],
    "anios_experiencia": [3, 8, 15, 4, 22, 6],
    "salario_mensual": [18000, 25000, 32000, 20000, 38000, 22000],
    "reparaciones_mes": [45, 60, 75, 50, 80, 55],
    "turno": ["Mañana", "Tarde", "Mañana", "Tarde", "Mañana", "Tarde"],
    "certificacion_ia": [True, True, True, False, True, False],
    "evaluacion_desempenio": [8.5, 9.2, 9.8, 8.0, 9.5, 8.9]
}

# ------------------------------------------------------------------------------
# PASO 2: Convertir a DataFrame y guardar en empleados_mecanicos.csv
# ------------------------------------------------------------------------------
df_inicial = pd.DataFrame(datos_taller)
archivo_csv = "empleados_mecanicos.csv"
df_inicial.to_csv(archivo_csv, index=False)
print(f"-> Archivo '{archivo_csv}' generado exitosamente con 6 registros.\n")

# ------------------------------------------------------------------------------
# PASO 3: Cargar el archivo CSV para realizar el Análisis Exploratorio (EDA)
# ------------------------------------------------------------------------------
df = pd.read_csv(archivo_csv)

# ------------------------------------------------------------------------------
# PASO 4: Inspección general de la estructura y contenido
# ------------------------------------------------------------------------------
print("=== 1. PRIMEROS REGISTROS (df.head) ===")
print(df.head(3))

print("\n=== 2. INFORMACIÓN GENERAL DEL DATAFRAME (df.info) ===")
df.info()

print(f"\nForma del dataset (filas, columnas): {df.shape}")

# ------------------------------------------------------------------------------
# PASO 5: Análisis Estadístico Descriptivo
# ------------------------------------------------------------------------------
print("\n=== 3. RESUMEN ESTADÍSTICO NUMÉRICO (df.describe) ===")
print(df.describe())

# ------------------------------------------------------------------------------
# PASO 6: Análisis Categórico y Filtrado
# ------------------------------------------------------------------------------
print("\n=== 4. CONTEO POR ESPECIALIDAD (df['especialidad'].value_counts) ===")
print(df['especialidad'].value_counts())

print("\n=== 5. EMPLEADOS CON MÁS DE 5 AÑOS DE EXPERIENCIA ===")
empleados_senior = df[df['anios_experiencia'] > 5]
print(empleados_senior[['nombre', 'especialidad', 'anios_experiencia', 'salario_mensual']])

# ------------------------------------------------------------------------------
# PASO 7: Visualización de Datos con Matplotlib
# ------------------------------------------------------------------------------
# Gráfica 1: Histograma de Salarios
plt.figure(figsize=(8, 4))
plt.hist(df['salario_mensual'], bins=4, color='skyblue', edgecolor='black')
plt.title("Distribución de Salarios Mensuales en el Taller Mecánico")
plt.xlabel("Salario ($)")
plt.ylabel("Frecuencia (N° Empleados)")
plt.grid(axis='y', alpha=0.75)
plt.tight_layout()
plt.show()

# Gráfica 2: Dispersión - Años de Experiencia vs Reparaciones al mes
plt.figure(figsize=(8, 4))
plt.scatter(df['anios_experiencia'], df['reparaciones_mes'], color='darkorange', s=100)
plt.title("Experiencia vs Reparaciones Completadas al Mes")
plt.xlabel("Años de Experiencia")
plt.ylabel("Reparaciones por Mes")
plt.grid(True)
plt.tight_layout()
plt.show()

```
