

---

# Actividad de Clase: Analizando Agentes de IA con Hugging Face Spaces

## 1. Nombre del Space

**Nombre:** Wanman

**Enlace:** https://huggingface.co/spaces/loveseries/wanmanlove

---

## 2. ¿Qué hace el agente?

El agente genera un video a partir de una o varias imágenes y un prompt escrito por el usuario. Analiza las entradas y produce un video que intenta seguir las instrucciones y el estilo solicitado.

---

## 3. Análisis PEAS

| Elemento        | Respuesta                                                                                                                                       |
| --------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| **Performance** | Que el agente genere correctamente el video solicitado, siguiendo las instrucciones del prompt y utilizando las imágenes proporcionadas.        |
| **Environment** | Entorno de generación de video por IA, donde interactúa con el modelo de generación, las imágenes proporcionadas y el sistema de procesamiento. |
| **Actuators**   | Generar el video solicitado.                                                                                                                    |
| **Sensors**     | Texto del prompt e imágenes proporcionadas por el usuario.                                                                                      |

---

## 4. Clasificación del entorno

| Propiedad        | Clasificación | Justificación                                                                                                                                         |
| ---------------- | ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Observable**   | **Parcial**   | El agente solo recibe la información proporcionada por el usuario (prompt e imágenes) y no conoce otros aspectos que el usuario pueda tener en mente. |
| **Determinista** | **No**        | El mismo prompt puede generar videos diferentes debido a la naturaleza probabilística del modelo.                                                     |
| **Episódico**    | **Sí**        | Cada solicitud es independiente y no depende de las anteriores.                                                                                       |
| **Estático**     | **Sí**        | Mientras el agente genera el video, las entradas no cambian.                                                                                          |
| **Discreto**     | **No**        | Tanto las imágenes como el video y el texto contienen información continua.                                                                           |
| **Conocido**     | **Sí**        | El agente conoce las acciones que puede realizar y cómo procesar las entradas para generar el video.                                                  |

---

## 5. ¿Qué tipo de programa de agente creen que es?

### **Agente basado en objetivos**

**Justificación:**

Se considera un agente basado en objetivos porque recibe como meta generar un video de acuerdo con las instrucciones del prompt y las imágenes proporcionadas. El agente analiza la información de entrada y genera un resultado que busca cumplir el objetivo especificado por el usuario.

---

# Discusión en clase

### ¿Dos Spaces diferentes pueden compartir el mismo tipo de entorno?

Sí. Aunque realicen tareas distintas, dos Spaces pueden operar en entornos con las mismas características, por ejemplo, ambos pueden ser parcialmente observables y no deterministas.

### ¿Es posible saber con certeza qué tipo de agente implementa un Space únicamente observándolo?

No. Solo es posible inferir el tipo de agente a partir de su comportamiento. La implementación interna puede ser diferente y no suele ser visible para el usuario.

### ¿Qué diferencia existe entre el comportamiento observable de un agente y su implementación interna?

El comportamiento observable es lo que el usuario puede ver: las entradas que recibe el agente, las acciones que realiza y los resultados que produce. La implementación interna corresponde a los algoritmos, modelos y procesos que utiliza para obtener esos resultados, información que normalmente no es visible.

---

# Reto adicional

### 1. Totalmente observable, determinista y episódico

**Ejemplo:** Un Space que convierta unidades (por ejemplo, kilómetros a millas).

**Justificación:**

* **Totalmente observable:** recibe toda la información necesaria.
* **Determinista:** la misma entrada siempre produce la misma salida.
* **Episódico:** cada conversión es independiente de las anteriores.

### 2. Parcialmente observable, estocástico y secuencial

**Ejemplo:** Un Space de generación de video mediante IA.

**Justificación:**

* **Parcialmente observable:** solo conoce el prompt y las imágenes proporcionadas.
* **Estocástico:** el mismo prompt puede generar resultados diferentes.
* **Secuencial:** el video se construye mediante múltiples pasos donde cada uno influye en el resultado final.
