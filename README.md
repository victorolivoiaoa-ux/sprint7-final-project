# sprint7-final-project
sprint7-final-project telecom-analysis
# ConnectaTel: Análisis Exploratorio y Segmentación de Clientes

## 1. Objetivo del Proyecto
Analizar el comportamiento de uso y los perfiles demográficos de los clientes de **ConnectaTel** mediante técnicas de análisis exploratorio de datos (EDA) y segmentación con Python. El fin principal es identificar patrones de consumo en llamadas y mensajería SMS, evaluar la presencia de valores atípicos (*outliers*) y formular recomendaciones estratégicas para la optimización de los planes tarifarios.

---

## 2. Datasets Utilizados
El análisis integra los registros de clientes y sus métricas transaccionales de telecomunicaciones:
* **Variables Demográficas:**
  * `user_id`: Identificador único de cada usuario.
  * `first_name` / `last_name`: Nombre y apellido del cliente.
  * `age`: Edad del usuario.
  * `city`: Ciudad de residencia.
  * `reg_date`: Fecha de contratación/registro del servicio.
  * `churn_date`: Fecha de cancelación de servicio (`NaN` representa usuarios activos).
* **Métricas de Consumo y Servicio:**
  * `cant_llamadas`: Cantidad total de llamadas realizadas.
  * `cant_minutos_llamada`: Duración total acumulada en minutos de voz.
  * `cant_mensajes`: Cantidad de mensajes de texto (SMS) enviados.
  * `plan`: Plan contratado (`Basico` o `Premium`).

---

## 3. Etapas del Análisis Realizadas
1. **Limpieza y Preparación de Datos:**
   * Tratamiento de valores ausentes en variables categóricas (`city`) y de control de estado (`churn_date`).
   * Validación de duplicados y homologación de formatos temporales (`datetime`).
2. **Análisis Estadístico y Outliers:**
   * Detección de rangos intercuartílicos (IQR) en minutos, llamadas y mensajes.
   * Evaluación y conservación de valores atípicos identificados como *heavy users* legítimos.
3. **Segmentación de Clientes:**
   * **Por Nivel de Uso (`grupo_uso`):** Clasificación en *Bajo uso* (< 5 llamadas y < 5 SMS), *Uso medio* (< 10 llamadas y < 10 SMS) y *Alto uso* ($\ge$ 10 llamadas o SMS).
   * **Por Edad (`grupo_edad`):** Segmentación en *Joven* (< 30 años), *Adulto* (30 a 59 años) y *Adulto Mayor* ($\ge$ 60 años).
4. **Visualización de Datos:**
   * Gráficos de barras (`sns.countplot`) para analizar las distribuciones poblacionales por segmento.
5. **Conclusiones Ejecutivas:**
   * Formulación de insights y propuestas de empaquetamiento comercial para stakeholders.

---

## 4. Cómo Ejecutar el Notebook

### Opción 1: Google Colab (Recomendada)
1. Haz clic en la opción de abrir el archivo `.ipynb` desde tu repositorio en GitHub.
2. Reemplaza `github.com` en la URL del navegador por `colab.research.google.com/github/` para abrir el cuaderno directamente en Colab.
3. En el menú superior de Colab, selecciona **Entorno de ejecución** $\rightarrow$ **Ejecutar todas**.

### Opción 2: Entorno Local (Jupyter Notebook / JupyterLab)
1. Clona este repositorio o descarga el archivo `.ipynb`.
2. Asegúrate de tener instalado Python 3 y las librerías necesarias ejecutando en tu terminal:
   ```bash
   pip install pandas numpy matplotlib seaborn
