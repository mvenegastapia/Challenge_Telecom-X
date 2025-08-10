# Challenge_Telecom-X
Alura: Challenge Telecom X: Análisis de evasión de clientes 
# Análisis de Fuga de Clientes (Churn) para una Empresa de Telecomunicaciones

Este repositorio contiene un análisis de datos exploratorio completo para identificar las causas fundamentales de la fuga de clientes (churn) en una empresa de telecomunicaciones. El objetivo es transformar datos brutos en insights accionables que puedan ser presentados a la gerencia para la toma de decisiones estratégicas.

---

## 📝 Descripción del Proyecto

El proyecto consiste en un análisis detallado de un conjunto de datos de clientes de una empresa de telecomunicaciones. Se realiza un proceso completo que abarca desde la limpieza y transformación de los datos (ETL) hasta la visualización interactiva y la identificación de los factores clave que influyen en la decisión de un cliente de abandonar la compañía. El resultado final es un diagnóstico claro y un conjunto de recomendaciones estratégicas.

---

## 🎯 Objetivo

El objetivo principal de este análisis es responder tres preguntas fundamentales para el negocio:
1.  **¿Quiénes son los clientes que abandonan la empresa?** (Perfil del cliente)
2.  **¿Por qué están abandonando la empresa?** (Factores y causas raíz)
3.  **¿Qué acciones podemos tomar para retenerlos?** (Recomendaciones estratégicas)

El propósito es proporcionar a la gerencia una hoja de ruta clara, basada en evidencia, para reducir la tasa de churn y aumentar la lealtad de los clientes.

---

## 💻 Tecnologías Utilizadas

Este análisis se ha realizado enteramente en un entorno de Python, aprovechando las siguientes librerías de ciencia de datos:

* **Pandas:** Para la manipulación, limpieza y transformación de datos.
* **NumPy:** Para operaciones numéricas y el manejo de valores nulos.
* **Plotly (Express y Graph Objects):** Para la creación de visualizaciones de datos interactivas y de alta calidad.
* **Requests:** Para la carga de datos directamente desde una URL.
* **Google Colab:** Como entorno de desarrollo basado en la nube para la ejecución del código y la presentación del análisis.

---

## 🔬 Método de Análisis

El análisis sigue una metodología estructurada de ciencia de datos:

1.  **Carga y Comprensión de Datos:** Carga del dataset JSON desde una URL y revisión inicial de su estructura.
2.  **Limpieza y Preprocesamiento (ETL):**
    * Normalización de la estructura JSON anidada a un DataFrame plano.
    * Corrección de tipos de datos (ej. `account_Charges_Total` a numérico).
    * Manejo de valores nulos y inconsistentes (ej. reemplazar `" "` por `NaN` y eliminar).
    * Estandarización de valores categóricos (ej. unificar `"No internet service"` y `"No phone service"` a `"No"`).
3.  **Análisis Exploratorio de Datos (EDA):**
    * **Análisis Univariado:** Estudio de la distribución de variables clave (`Churn`, `account_Contract`, `internet_InternetService`).
    * **Análisis Bivariado:** Cruce de la variable `Churn` con otras características para calcular tasas de cancelación e identificar correlaciones.
    * **Análisis Multivariado:** Creación de visualizaciones complejas (scatter plots, sunburst charts) para entender la interacción entre múltiples factores.
4.  **Visualización Interactiva:** Uso de Plotly para crear gráficos dinámicos que permitan una exploración profunda y una presentación clara de los hallazgos.
5.  **Síntesis y Conclusiones:** Interpretación de los resultados para construir un perfil del cliente propenso a cancelar y formular recomendaciones estratégicas.

---

## 💡 Hallazgos Clave

* **Factor Contrato:** El contrato `Month-to-month` es el principal predictor de abandono, con una tasa de cancelación drásticamente superior a los contratos anuales.
* **Factor Servicio de Internet:** Los clientes con **Fibra Óptica** cancelan en una proporción mucho mayor que los clientes con DSL.
* **Factor Soporte:** La combinación de **Fibra Óptica** con la **ausencia de Soporte Técnico (`TechSupport`) y Seguridad Online (`OnlineSecurity`)** es un catalizador clave para el abandono.
* **Factor Antigüedad y Costo:** Los **clientes nuevos** (baja antigüedad) son extremadamente **sensibles a los cargos mensuales altos**, formando el grupo de mayor riesgo.
* **Factor Compromiso:** La tasa de cancelación disminuye a medida que un cliente contrata más servicios adicionales, lo que indica que un mayor "compromiso" con el ecosistema de la empresa aumenta la lealtad.

---
## 🚀 Cómo Usar este Notebook en Google Colab

Puedes ejecutar este análisis por tu cuenta siguiendo estos sencillos pasos:

1.  **Abre Google Colab:** Ve a [https://colab.research.google.com/](https://colab.research.google.com/).
2.  **Sube el Notebook:** Si tienes el archivo `.ipynb`, puedes subirlo directamente usando `Archivo > Subir notebook`.
3.  **Crea un Notebook Nuevo:** Si solo tienes el código, puedes crear un notebook nuevo y pegar las celdas de código en orden.
4.  **Ejecuta el Código:** Ejecuta cada celda de código secuencialmente, desde la carga de datos hasta las visualizaciones. No necesitas descargar el archivo JSON, ya que el código lo carga directamente desde la URL.
5.  **Interactúa con los Gráficos:** Los gráficos generados con Plotly son interactivos. Pasa el mouse sobre ellos, haz clic en las leyendas y explora los datos por tu cuenta.

---

## 📊 Informe Ejecutivo: Diagnóstico y Plan de Acción

### ¿Quiénes son los Clientes que Abandonan?

El perfil del cliente con mayor probabilidad de cancelar se caracteriza por:
* **Contractualmente:** Es un cliente con un contrato de **mes a mes**.
* **Antigüedad:** Es un **cliente nuevo**, con menos de un año en la compañía.
* **Forma de Pago:** Utiliza predominantemente el **Cheque Electrónico (`Electronic check`)**.

### ¿Qué Factores Originan el Abandono?

El abandono se origina por una "tormenta perfecta" de tres factores:

1.  **Producto Premium, Soporte Básico:** Se vende **Fibra Óptica** a un precio elevado, pero sin el ecosistema de soporte (`TechSupport`, `OnlineSecurity`) necesario para garantizar una buena experiencia.
2.  **Alta Sensibilidad al Precio del Cliente Nuevo:** Los nuevos clientes no perdonan una mala experiencia si sienten que están pagando un precio alto.
3.  **Barrera de Salida Inexistente:** El contrato **mes a mes** permite que la frustración inicial se convierta inmediatamente en una cancelación.

### Plan de Acción Gerencial

Se recomienda un plan de acción enfocado en tres estrategias:

1.  **Rediseñar la Oferta de Valor de Fibra Óptica:**
    * **Acción:** Crear **paquetes de Fibra Óptica** donde el **Soporte Técnico se incluya por defecto** durante el primer año.
    * **Objetivo:** Aumentar el valor percibido y reducir la frustración técnica.

2.  **Fomentar la Lealtad a Largo Plazo:**
    * **Acción:** Lanzar una **campaña de migración** para incentivar a los clientes de "mes a mes" a cambiarse a contratos anuales a cambio de un beneficio claro.
    * **Objetivo:** Aumentar la retención y la estabilidad de la base de clientes.

3.  **Implementar un Programa de "Blindaje" para Clientes Nuevos:**
    * **Acción:** Crear un **programa de *onboarding* proactivo de 90 días** para clientes de Fibra Óptica.
    * **Objetivo:** Construir confianza y lealtad desde el primer día.
