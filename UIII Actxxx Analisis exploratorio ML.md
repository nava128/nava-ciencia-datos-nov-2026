# Análisis exploratorio de datos de empleados de la industria con Pandas y Matplotlib

Asignatura: Soluciona problemas de Machine Learning\
Nivel: Tercer semestre de preparatoria\
Especialidad: Inteligencia Artificial\
Dificultad: Cero a principiante\
Lenguaje: Python\
Herramientas: Visual Studio Code, Pandas, Matplotlib y CSV.

## 1. Propósito de la práctica

El estudiante aprenderá a realizar un análisis exploratorio de datos (EDA, Exploratory Data Analysis) utilizando las bibliotecas Pandas y Matplotlib.

Se trabajará con información ficticia de seis empleados de una industria, considerando diez características por empleado.

El procedimiento será:

1. Crear un diccionario con diez listas y seis elementos por lista.
2. Convertir el diccionario en un DataFrame.
3. Explorar la estructura de los datos.
4. Guardar la información en un archivo CSV.
5. Leer nuevamente los datos desde el CSV.
6. Identificar tipos de datos, valores faltantes y estadísticas.
7. Ordenar, filtrar y agrupar información.
8. Crear gráficas para interpretar los datos.
9. Obtener conclusiones que puedan utilizarse posteriormente en Machine Learning.

## 2. Comandos de Pandas y Matplotlib más utilizados

### A. Comandos para explorar datos con Pandas

| Núm. | Comando                                      | Función                                    |
| ---- | -------------------------------------------- | ------------------------------------------ |
| 1    | `pd.DataFrame()`                             | Crear un DataFrame.                        |
| 2    | `pd.read_csv()`                              | Leer un archivo CSV.                       |
| 3    | `df.to_csv()`                                | Guardar un DataFrame en CSV.               |
| 4    | `df.head()`                                  | Mostrar los primeros registros.            |
| 5    | `df.tail()`                                  | Mostrar los últimos registros.             |
| 6    | `df.shape`                                   | Consultar filas y columnas.                |
| 7    | `df.columns`                                 | Mostrar nombres de columnas.               |
| 8    | `df.index`                                   | Consultar índices.                         |
| 9    | `df.info()`                                  | Mostrar estructura y tipos de datos.       |
| 10   | `df.dtypes`                                  | Consultar tipos de datos.                  |
| 11   | `df.describe()`                              | Obtener estadísticas descriptivas.         |
| 12   | `df.describe(include='all')`                 | Resumir variables numéricas y categóricas. |
| 13   | `df.isnull().sum()`                          | Contar valores faltantes.                  |
| 14   | `df.notnull().sum()`                         | Contar valores disponibles.                |
| 15   | `df.nunique()`                               | Contar valores únicos por columna.         |
| 16   | `df['columna'].unique()`                     | Mostrar valores diferentes.                |
| 17   | `df['columna'].value_counts()`               | Contar frecuencias.                        |
| 18   | `df['columna'].mean()`                       | Calcular promedio.                         |
| 19   | `df['columna'].max()`                        | Obtener valor máximo.                      |
| 20   | `df['columna'].min()`                        | Obtener valor mínimo.                      |
| 21   | `df['columna'].sum()`                        | Calcular suma.                             |
| 22   | `df.sort_values()`                           | Ordenar registros.                         |
| 23   | `df.groupby()`                               | Agrupar registros.                         |
| 24   | `df.loc[]`                                   | Seleccionar filas y columnas por etiqueta. |
| 25   | `df.iloc[]`                                  | Seleccionar por posición.                  |
| 26   | `df.drop_duplicates()`                       | Eliminar registros duplicados.             |
| 27   | `df.corr(numeric_only=True)`                 | Calcular correlaciones numéricas.          |
| 28   | `df['columna'].value_counts(normalize=True)` | Calcular frecuencias relativas.            |

### B. Comandos para visualizar datos con Matplotlib

Primero se importa la biblioteca:

```
import matplotlib.pyplot as plt
```

| Núm. | Comando              | Función                          |
| ---- | -------------------- | -------------------------------- |
| 1    | `plt.figure()`       | Crear una figura.                |
| 2    | `plt.bar()`          | Crear gráfica de barras.         |
| 3    | `plt.plot()`         | Crear gráfica de líneas.         |
| 4    | `plt.scatter()`      | Crear gráfica de dispersión.     |
| 5    | `plt.hist()`         | Crear histograma.                |
| 6    | `plt.boxplot()`      | Crear diagrama de caja.          |
| 7    | `plt.pie()`          | Crear gráfica circular.          |
| 8    | `plt.title()`        | Colocar título.                  |
| 9    | `plt.xlabel()`       | Nombrar eje X.                   |
| 10   | `plt.ylabel()`       | Nombrar eje Y.                   |
| 11   | `plt.xticks()`       | Modificar etiquetas del eje X.   |
| 12   | `plt.yticks()`       | Modificar etiquetas del eje Y.   |
| 13   | `plt.grid()`         | Mostrar cuadrícula.              |
| 14   | `plt.legend()`       | Mostrar leyenda.                 |
| 15   | `plt.tight_layout()` | Ajustar espacios de la figura.   |
| 16   | `plt.show()`         | Mostrar gráfica.                 |
| 17   | `plt.savefig()`      | Guardar gráfica como imagen.     |
| 18   | `plt.subplots()`     | Crear figura y área de gráficas. |

## 3. Situación práctica: información de empleados de una industria

Una empresa industrial necesita analizar las características de sus empleados para conocer sus edades, salarios, antigüedad, departamentos y desempeño laboral.

Se utilizarán diez variables:

| Variable         | Descripción                   | Tipo de dato |
| ---------------- | ----------------------------- | ------------ |
| id_empleado      | Identificador                 | Numérico     |
| nombre           | Nombre del empleado           | Categórico   |
| edad             | Edad en años                  | Numérico     |
| departamento     | Área de trabajo               | Categórico   |
| puesto           | Cargo laboral                 | Categórico   |
| salario          | Salario mensual en pesos      | Numérico     |
| antiguedad       | Años trabajando en la empresa | Numérico     |
| horas_trabajadas | Horas semanales               | Numérico     |
| capacitaciones   | Capacitaciones realizadas     | Numérico     |
| desempeno        | Evaluación de desempeño       | Numérico     |

Los datos son ficticios y se utilizan exclusivamente con fines educativos.

## 4. Preparación del entorno de trabajo en Visual Studio Code

### Paso 1. Crear la carpeta del proyecto

Crear una carpeta con el nombre:

```
analisis-empleados-industria
```

Abrirla desde Visual Studio Code.

### Paso 2. Crear el entorno virtual

Abrir la terminal de VS Code y ejecutar:

```
python -m venv .venv
```

### Paso 3. Activar el entorno virtual

En Windows PowerShell:

```
.\.venv\Scripts\Activate.ps1
```

Si utilizas CMD:

```
.venv\Scripts\activate.bat
```

### Paso 4. Instalar las bibliotecas

```
python -m pip install pandas matplotlib
```

### Paso 5. Verificar las instalaciones

```
python -c "import pandas; import matplotlib; print('Bibliotecas instaladas correctamente')"
```

### Paso 6. Crear los archivos del proyecto

La estructura será:

```
analisis-empleados-industria/
│
├── .venv/
│
├── empleados_industria.csv
│
├── explorar_datos_empleados.py
│
└── requirements.txt
```

Crear `requirements.txt`:

```
pandas
matplotlib
```

Para generar el CSV ejecutaremos primero el programa Python, que construirá el diccionario y guardará el archivo.

## 5. Crear el diccionario con 10 listas y 6 elementos

Paso 7. Crear los datos de los empleados

En el archivo `explorar_datos_empleados.py`, escribir el siguiente código.

Primero importamos las bibliotecas:

```
import pandas as pdimport matplotlib.pyplot as plt
```

Después creamos un diccionario llamado `empleados`, que contiene diez listas con seis elementos cada una.

```
# 1. Crear diccionario con datos de empleadosempleados = {    'id_empleado': [101, 102, 103, 104, 105, 106],    'nombre': [        'Carlos',        'Maria',        'Jose',        'Ana',        'Luis',        'Sofia'    ],    'edad': [25, 32, 28, 40, 35, 29],    'departamento': [        'Produccion',        'Calidad',        'Mantenimiento',        'Produccion',        'Calidad',        'Mantenimiento'    ],    'puesto': [        'Operador',        'Inspector',        'Tecnico',        'Supervisor',        'Inspector',        'Tecnico'    ],    'salario': [12000, 15000, 13500, 22000, 16000, 14500],    'antiguedad': [2, 6, 4, 12, 8, 3],    'horas_trabajadas': [48, 40, 45, 40, 42, 48],    'capacitaciones': [2, 5, 3, 8, 6, 4],    'desempeno': [80, 95, 85, 98, 90, 88]}
```

Explicación:

- `empleados`: nombre del diccionario.
- Las claves, por ejemplo `'edad'`, representan las columnas.
- Los valores entre corchetes representan las listas.
- Cada lista contiene seis elementos, uno por empleado.
- Cada posición de las listas corresponde al mismo empleado.

## 6. Convertir el diccionario en un DataFrame

Paso 8. Crear la tabla de empleados

Utilizamos `pd.DataFrame()` para convertir el diccionario en una tabla.

```
# 2. Convertir diccionario en DataFramedf = pd.DataFrame(empleados)print("\nTABLA ORIGINAL DE EMPLEADOS")print(df)
```

Resultado esperado:

| id_empleado | nombre | edad | departamento  | salario | antiguedad |
| ----------- | ------ | ---- | ------------- | ------- | ---------- |
| 101         | Carlos | 25   | Produccion    | 12,000  | 2          |
| 102         | Maria  | 32   | Calidad       | 15,000  | 6          |
| 103         | Jose   | 28   | Mantenimiento | 13,500  | 4          |
| 104         | Ana    | 40   | Produccion    | 22,000  | 12         |
| 105         | Luis   | 35   | Calidad       | 16,000  | 8          |
| 106         | Sofia  | 29   | Mantenimiento | 14,500  | 3          |

La tabla completa contiene diez columnas. Aquí se muestran seis para facilitar su lectura.

## 7. Convertir el DataFrame en archivo CSV

Paso 9. Guardar los datos

Utilizamos `to_csv()` para convertir el DataFrame en un archivo CSV.

```
# 3. Exportar los datos a CSVdf.to_csv(    'empleados_industria.csv',    index=False,    encoding='utf-8-sig')print("\nArchivo CSV creado correctamente")
```

Explicación de los parámetros:

| Parámetro                   | Función                                                               |
| --------------------------- | --------------------------------------------------------------------- |
| `'empleados_industria.csv'` | Nombre del archivo.                                                   |
| `index=False`               | Evita guardar el índice como columna adicional.                       |
| `encoding='utf-8-sig'`      | Facilita la lectura de caracteres especiales en programas como Excel. |

Al ejecutar el programa aparecerá el archivo:

`empleados_industria.csv`

## 8. Leer los datos desde el archivo CSV

Paso 10. Importar nuevamente los datos

Ahora trabajaremos con el archivo CSV y no directamente con el diccionario.

```
# 4. Leer el archivo CSVdf = pd.read_csv('empleados_industria.csv')print("\nDATOS LEIDOS DESDE CSV")print(df)
```

¿Por qué hacemos esto?

Porque en un proyecto de Machine Learning es frecuente recibir los datos desde archivos CSV, bases de datos o fuentes externas, en lugar de construirlos manualmente.

# 9. Análisis exploratorio de datos (EDA)

A partir de este punto comenzamos a explorar la información del archivo CSV.

### Paso 11. Mostrar los primeros registros

```
print("\n1. PRIMEROS REGISTROS")print(df.head())
```

Explicación: `head()` muestra los primeros cinco registros por defecto.

También podemos indicar cuántos registros queremos:

```
print(df.head(3))
```

### Paso 12. Mostrar los últimos registros

```
print("\n2. ULTIMOS REGISTROS")print(df.tail())
```

Explicación: `tail()` permite observar los últimos cinco empleados.

### Paso 13. Conocer las dimensiones del DataFrame

```
print("\n3. DIMENSIONES")print(df.shape)
```

Resultado:

```
(6, 10)
```

Interpretación:

- 6 representa el número de filas.
- 10 representa el número de columnas.

### Paso 14. Consultar los nombres de las columnas

```
print("\n4. NOMBRES DE LAS COLUMNAS")print(df.columns)
```

Explicación: Permite identificar las variables disponibles para el análisis.

### Paso 15. Identificar los tipos de datos

```
print("\n5. TIPOS DE DATOS")print(df.dtypes)
```

Ejemplo de interpretación:

| Variable         | Tipo   |
| ---------------- | ------ |
| id_empleado      | int64  |
| nombre           | object |
| edad             | int64  |
| departamento     | object |
| salario          | int64  |
| antiguedad       | int64  |
| horas_trabajadas | int64  |
| capacitaciones   | int64  |
| desempeno        | int64  |

`object` representa normalmente texto en este DataFrame, mientras que `int64` representa números enteros.

### Paso 16. Consultar la información general

```
print("\n6. INFORMACION GENERAL")df.info()
```

Explicación: Muestra:

- Cantidad de registros.
- Nombres de las columnas.
- Tipos de datos.
- Cantidad de valores no nulos.
- Memoria utilizada.

### Paso 17. Obtener estadísticas descriptivas

```
print("\n7. ESTADISTICAS DESCRIPTIVAS")print(df.describe())
```

Explicación: Calcula automáticamente:

| Estadística | Significado          |
| ----------- | -------------------- |
| count       | Cantidad de datos.   |
| mean        | Promedio.            |
| std         | Desviación estándar. |
| min         | Valor mínimo.        |
| 25%         | Primer cuartil.      |
| 50%         | Mediana.             |
| 75%         | Tercer cuartil.      |
| max         | Valor máximo.        |

Para incluir también variables categóricas:

```
print(df.describe(include='all'))
```

### Paso 18. Identificar valores faltantes

```
print("\n8. VALORES FALTANTES")print(df.isnull().sum())
```

Explicación: Identifica cuántos valores vacíos existen en cada columna.

En nuestros datos iniciales, el resultado será cero para todas las columnas.

### Paso 19. Identificar registros duplicados

```
print("\n9. REGISTROS DUPLICADOS")print(df.duplicated().sum())
```

Explicación: Permite detectar filas repetidas.

### Paso 20. Identificar valores únicos

```
print("\n10. VALORES UNICOS")print(df.nunique())
```

Explicación: Cuenta cuántos valores diferentes existen en cada columna.

Para consultar los departamentos:

```
print(df['departamento'].unique())
```

Resultado:

```
['Produccion' 'Calidad' 'Mantenimiento']
```

### Paso 21. Contar empleados por departamento

```
print("\n11. EMPLEADOS POR DEPARTAMENTO")print(df['departamento'].value_counts())
```

Resultado:

```
Produccion       2
Calidad          2
Mantenimiento    2
```

### Paso 22. Calcular el promedio del salario

```
print("\n12. PROMEDIO DE SALARIO")print(df['salario'].mean())
```

Resultado:

```
15583.33
```

Interpretación: El salario promedio de los seis empleados es aproximadamente $15,583.33 mensuales.

### Paso 23. Consultar salario máximo y mínimo

```
print("\n13. SALARIO MAXIMO")print(df['salario'].max())print("\n14. SALARIO MINIMO")print(df['salario'].min())
```

Resultado:

- Salario máximo: $22,000.
- Salario mínimo: $12,000.

### Paso 24. Ordenar empleados por salario

```
print("\n15. EMPLEADOS ORDENADOS POR SALARIO")print(df.sort_values(    by='salario',    ascending=False))
```

Explicación:

- `by='salario'`: indica la columna que se ordenará.
- `ascending=False`: ordena de mayor a menor.
- `ascending=True`: ordena de menor a mayor.

### Paso 25. Filtrar empleados con salario superior a $15,000

```
print("\n16. EMPLEADOS CON SALARIO MAYOR A 15000")filtro = df[df['salario'] > 15000]print(filtro)
```

Explicación: Se utiliza una condición lógica para seleccionar únicamente los empleados que cumplen el criterio.

### Paso 26. Agrupar empleados por departamento

```
print("\n17. PROMEDIO DE SALARIO POR DEPARTAMENTO")resumen = df.groupby('departamento').agg(    empleados=('id_empleado', 'count'),    salario_promedio=('salario', 'mean'),    salario_maximo=('salario', 'max'))print(resumen)
```

Explicación: `groupby()` agrupa empleados por departamento y `agg()` permite calcular diferentes indicadores.

# 10. Visualización de datos con Matplotlib

Ahora utilizaremos Matplotlib para representar gráficamente los resultados del análisis.

### Paso 27. Importar Matplotlib

Ya se realizó al inicio:

```
import matplotlib.pyplot as plt
```

### Paso 28. Gráfica de barras: empleados por departamento

```
conteo = df['departamento'].value_counts()plt.figure(figsize=(8, 5))plt.bar(conteo.index, conteo.values)plt.title('Empleados por departamento')plt.xlabel('Departamento')plt.ylabel('Cantidad de empleados')plt.grid(axis='y')plt.tight_layout()plt.show()
```

Interpretación: permite conocer cómo se distribuyen los empleados en las diferentes áreas industriales.

### Paso 29. Gráfica de barras: salarios por empleado

```
plt.figure(figsize=(8, 5))plt.bar(df['nombre'], df['salario'])plt.title('Salario mensual por empleado')plt.xlabel('Empleado')plt.ylabel('Salario en pesos')plt.grid(axis='y')plt.tight_layout()plt.show()
```

Interpretación: permite comparar los salarios de los trabajadores.

### Paso 30. Histograma: distribución de edades

```
plt.figure(figsize=(8, 5))plt.hist(df['edad'], bins=5)plt.title('Distribucion de edades de empleados')plt.xlabel('Edad')plt.ylabel('Frecuencia')plt.grid(axis='y')plt.tight_layout()plt.show()
```

Interpretación: permite observar cómo se distribuyen las edades de los trabajadores.

### Paso 31. Gráfica de dispersión: edad y salario

```
plt.figure(figsize=(8, 5))plt.scatter(df['edad'], df['salario'])plt.title('Relacion entre edad y salario')plt.xlabel('Edad')plt.ylabel('Salario mensual')plt.grid()plt.tight_layout()plt.show()
```

Interpretación: permite observar si existe algún patrón entre la edad y el salario. Una asociación visual no demuestra causalidad.

### Paso 32. Diagrama de caja: distribución de salarios

```
plt.figure(figsize=(7, 5))plt.boxplot(df['salario'])plt.title('Distribucion de salarios')plt.ylabel('Salario mensual')plt.grid(axis='y')plt.tight_layout()plt.show()
```

Interpretación: permite observar la mediana, dispersión y posibles valores atípicos.

### Paso 33. Matriz de correlación

```
correlacion = df.corr(numeric_only=True)print(correlacion)plt.figure(figsize=(9, 6))plt.imshow(correlacion, cmap='coolwarm', vmin=-1, vmax=1)plt.colorbar()plt.xticks(    range(len(correlacion.columns)),    correlacion.columns,    rotation=45)plt.yticks(    range(len(correlacion.columns)),    correlacion.columns)plt.title('Matriz de correlacion de empleados')plt.tight_layout()plt.show()
```

Explicación:

- `corr()`: calcula correlaciones entre variables numéricas.
- `imshow()`: representa los valores como una matriz de colores.
- `cmap='coolwarm'`: selecciona una escala de colores.
- `vmin=-1` y `vmax=1`: establecen los límites de correlación.
- `colorbar()`: muestra la escala de valores.

La correlación puede tomar valores entre -1 y 1:

| Valor        | Interpretación                         |
| ------------ | -------------------------------------- |
| Cercano a 1  | Asociación positiva.                   |
| Cercano a -1 | Asociación negativa.                   |
| Cercano a 0  | Asociación lineal débil o inexistente. |

Importante: Seis empleados son insuficientes para obtener conclusiones confiables sobre relaciones estadísticas o entrenar un modelo de Machine Learning. Este conjunto sirve para aprender los comandos y el procedimiento.

# 11. Código completo del archivo explorar_datos_empleados.py

El siguiente programa integra los pasos anteriores. Copia todo el código en el archivo `explorar_datos_empleados.py`.

El programa crea primero el CSV y posteriormente lee ese mismo archivo para realizar el análisis exploratorio.

```
# =====================================================# PROYECTO: ANALISIS EXPLORATORIO DE EMPLEADOS# ASIGNATURA: SOLUCIONA PROBLEMAS DE MACHINE LEARNING# ESPECIALIDAD: INTELIGENCIA ARTIFICIAL# NIVEL: TERCER SEMESTRE# =====================================================# PASO 1. Importar bibliotecasimport pandas as pdimport matplotlib.pyplot as pltprint("\nPASO 1. BIBLIOTECAS IMPORTADAS")# PASO 2. Crear diccionario con 10 listasempleados = {    'id_empleado': [101, 102, 103, 104, 105, 106],    'nombre': ['Carlos', 'Maria', 'Jose', 'Ana', 'Luis', 'Sofia'],    'edad': [25, 32, 28, 40, 35, 29],    'departamento': [        'Produccion', 'Calidad', 'Mantenimiento',        'Produccion', 'Calidad', 'Mantenimiento'    ],    'puesto': [        'Operador', 'Inspector', 'Tecnico',        'Supervisor', 'Inspector', 'Tecnico'    ],    'salario': [12000, 15000, 13500, 22000, 16000, 14500],    'antiguedad': [2, 6, 4, 12, 8, 3],    'horas_trabajadas': [48, 40, 45, 40, 42, 48],    'capacitaciones': [2, 5, 3, 8, 6, 4],    'desempeno': [80, 95, 85, 98, 90, 88]}print("\nPASO 2. DICCIONARIO CREADO")
```

## 12. Ejecutar el programa desde la terminal de VS Code

Paso 34. Verificar que el entorno virtual esté activado.

Debe aparecer `(.venv)` al inicio de la terminal.

Paso 35. Ejecutar el programa.

```
python explorar_datos_empleados.py
```

Paso 36. Verificar los archivos generados.

```
analisis-empleados-industria/
│
├── .venv/
│
├── empleados_industria.csv
│
├── explorar_datos_empleados.py
│
└── requirements.txt
```

El programa mostrará los resultados en la terminal y abrirá las gráficas de Matplotlib.

# 13. Interpretación de resultados para Machine Learning

Una vez terminado el análisis exploratorio, los estudiantes deben interpretar la información antes de intentar construir un modelo de Machine Learning.

| Pregunta de análisis                   | Variable utilizada | Comando          |
| -------------------------------------- | ------------------ | ---------------- |
| ¿Cuál es la edad promedio?             | `edad`             | `mean()`         |
| ¿Qué departamento tiene más empleados? | `departamento`     | `value_counts()` |
| ¿Quién tiene el salario más alto?      | `salario`          | `max()`          |
| ¿Cuál es la antigüedad promedio?       | `antiguedad`       | `mean()`         |
| ¿Qué empleado tiene mejor desempeño?   | `desempeno`        | `max()`          |
| ¿Existe relación entre edad y salario? | `edad`, `salario`  | `corr()`         |

Conexión con Machine Learning:

Los datos explorados pueden utilizarse posteriormente para desarrollar un modelo de aprendizaje supervisado.

Por ejemplo:

Proyecto posterior: Predicción del desempeño laboral

VARIABLES DE ENTRADA (X)

Edad, salario, antigüedad, horas trabajadas y capacitaciones.

MODELO DE MACHINE LEARNING

Algoritmo de regresión o clasificación, según cómo se defina el objetivo.

VARIABLE OBJETIVO (Y)

Desempeño laboral.

Consideración importante: El desempeño laboral debe estar definido mediante criterios objetivos y pertinentes. Además, las variables laborales y personales deben utilizarse con criterios de privacidad, equidad y ausencia de discriminación. Este conjunto de seis empleados no permite entrenar ni validar un modelo confiable; se necesitarían muchos más registros y una evaluación adecuada.

# 14. Actividad de aprendizaje para los estudiantes

Instrucciones: Realiza las siguientes actividades utilizando el archivo `empleados_industria.csv`.

1. Agrega cuatro empleados nuevos al diccionario.
2. Calcula la edad promedio de los empleados.
3. Identifica el departamento con mayor número de trabajadores.
4. Ordena los empleados por antigüedad de mayor a menor.
5. Filtra los empleados que tengan más de cinco años trabajando en la industria.
6. Calcula el salario promedio por departamento.
7. Genera una gráfica de barras con los salarios.
8. Genera un histograma con las edades.
9. Calcula la correlación entre antigüedad y salario.
10. Escribe cinco conclusiones sobre los resultados obtenidos.

## 15. Evidencias de aprendizaje y evaluación

| Evidencia       | Características                               | Instrumento     |
| --------------- | --------------------------------------------- | --------------- |
| Archivo CSV     | Contiene los datos de los empleados.          | Lista de cotejo |
| Programa Python | Utiliza Pandas para explorar información.     | Lista de cotejo |
| Gráficas        | Presenta cinco visualizaciones correctamente. | Rúbrica         |
| Análisis        | Interpreta estadísticas y resultados.         | Cuestionario    |
| Conclusiones    | Explica los hallazgos del análisis.           | Rúbrica         |

Distribución de tiempo sugerida: 5 horas.

- 1 hora: creación del diccionario y CSV.
- 2 horas: exploración con Pandas.
- 1 hora: visualización con Matplotlib.
- 1 hora: interpretación y conclusiones.

Recomendación docente: Es importante que los estudiantes comprendan que el análisis exploratorio de datos es una etapa fundamental antes de entrenar un modelo de Machine Learning. Primero deben conocer qué información tienen, cómo está organizada, qué problemas presenta y qué patrones pueden identificar.

También puedo preparar la siguiente práctica: limpieza de datos, tratamiento de valores faltantes, detección de valores atípicos y preparación del CSV para entrenar un modelo de Machine Learning.

📊Preparar práctica semanal de Pandas y MLToca para configurar
