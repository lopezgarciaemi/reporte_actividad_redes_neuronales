# 🧪 Lab: Explorando las Entrañas de Stable Diffusion
### Workshop: Redes Neuronales para la IA Generativa

Este repositorio contiene la guía práctica para comprender la arquitectura interna de los modelos de difusión. El objetivo es manipular los mecanismos que dictan cómo una IA transforma el ruido en arte.

---

## 👥 Dinámica del Laboratorio
* **Formato:** Trabajo en parejas.
* **Tiempo estimado:** 30 minutos.
* **Herramientas:** Jupyter Notebook / Google Colab.

---

## 🚀 Paso 1: Configuración
1. Abran el notebook del laboratorio en Google Colab o su entorno local de Jupyter.
2. Si usan Colab, asegúrense de activar la GPU: `Entorno de ejecución` > `Cambiar tipo de entorno` > `T4 GPU`.
3. Ejecuten la **Celda 1** para instalar las librerías necesarias (`diffusers`, `transformers`).
4. Ejecuten la **Celda 2** para cargar el modelo en memoria (CLIP, U-Net y VAE).

---

## 🛠️ Paso 2: Experimentos con Hiperparámetros

En la **Celda 3**, encontrarán el código para generar imágenes. Su misión es modificar las variables y documentar los resultados.

### Experimento A: El Escultor de Ruido (`num_inference_steps`)
La **U-Net** elimina ruido en pasos sucesivos. Vamos a ver qué pasa cuando la interrumpimos.
* **Misión:** Generen una imagen con el prompt de su elección usando 1, 10, 25 y 50 pasos.
* **Observación:** ¿En qué punto la imagen deja de ser "manchas" y empieza a tener una estructura coherente?

### Experimento B: El Nivel de Obediencia (`guidance_scale`)
Aquí ajustaremos la influencia del **Transformer (CLIP)** sobre la **U-Net**.
* **Misión:** Usando el mismo prompt y la misma semilla (Seed), cambien la escala a 1, 7.5 y 30.
* **Observación:** ¿Qué efectos visuales aparecen cuando forzamos a la IA a ser "demasiado obediente" (valor 30)?

### Experimento C: El Espacio Latente (`seed`)
Cada imagen es una coordenada en un mapa infinito de números.
* **Misión:** Mantengan el prompt y los pasos fijos, pero cambien el valor de la semilla (Seed) tres veces.
* **Observación:** Si el prompt es el mismo, ¿por qué la composición cambia tanto?

---

## 📝 Paso 3: Desafío de Comunicación (Técnica Feynman)

Al final de su notebook, creen una celda de texto y expliquen con sus propias palabras (como si se lo explicaran a un niño):

1. **¿Qué trabajo hizo la red U-Net en el Experimento A?**
2. **¿Cuál fue su hallazgo más sorprendente al manipular el código?**

---

## 🆘 Solución de Problemas
* **Error de Memoria (OOM):** Reinicien el entorno de ejecución. No intenten generar imágenes mayores a 512x512.
* **Imagen Negra:** Es el filtro de seguridad (NSFW). Cambien ligeramente el prompt.

---
*Este workshop es parte de la formación en IA Generativa - 15 de Abril.*
