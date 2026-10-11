# Clasificador de Perros y Gatos con TensorFlow.js

Un proyecto web interactivo que clasifica en tiempo real si la imagen capturada por la cámara web corresponde a un **perro** o un **gato**. Utiliza un modelo de Deep Learning (Red Neuronal Convolucional) ejecutado directamente en el navegador a través de TensorFlow.js.

## 🚀 Pila Tecnológica (Tech Stack)

Este proyecto está construido con tecnologías web estándar y herramientas de Machine Learning para el navegador:

- **Frontend:** HTML5, CSS3, JavaScript (Vanilla).
- **Diseño / UI:** [Bootstrap 5.0.2](https://getbootstrap.com/) (vía CDN) para estilos responsivos.
- **Machine Learning:** [TensorFlow.js 2.0.0](https://www.tensorflow.org/js) (vía CDN) para cargar el modelo preentrenado y realizar inferencias en el lado del cliente.
- **Hardware API:** `navigator.mediaDevices.getUserMedia` para acceder al video de la cámara web (webcam o cámara móvil).

## 🛠 Instalación y Configuración del Entorno Local

Dado que el proyecto consiste en archivos estáticos (`.html`, `.json`, `.bin`), no requiere instalar dependencias mediante `npm` o `pip`. Sin embargo, para que TensorFlow.js pueda cargar correctamente el archivo `model.json` y los binarios asociados, **es obligatorio servir los archivos a través de un servidor HTTP local**. Abrir directamente el archivo `index.html` en el navegador usando el protocolo `file://` producirá un error de CORS.

### Pasos a seguir:

1. **Clonar el repositorio:**
   ```bash
   git clone <URL_DEL_REPOSITORIO>
   cd <NOMBRE_DE_LA_CARPETA>
   ```

2. **Iniciar un servidor HTTP local:**
   Puedes utilizar el servidor de tu preferencia. Aquí tienes algunos comandos comunes:

   - **Con Python 3 (Recomendado):**
     ```bash
     python3 -m http.server 8000
     ```

   - **Con Node.js (usando `http-server`):**
     ```bash
     npx http-server -p 8000
     ```

   - **Con PHP:**
     ```bash
     php -S localhost:8000
     ```

3. **Abrir la aplicación en el navegador:**
   Navega a `http://localhost:8000` en tu navegador web. El navegador te solicitará permisos para utilizar la cámara; asegúrate de concederlos.

## 📁 Estructura del Repositorio

- `index.html`: Punto de entrada principal. Contiene la interfaz de usuario, la lógica de acceso a la cámara y el script para procesar las imágenes y realizar predicciones.
- `model.json`: Archivo de configuración (generado por el convertidor de TensorFlow.js) que describe la topología del modelo preentrenado.
- `group1-shard1of2.bin` y `group1-shard2of2.bin`: Archivos binarios que almacenan los pesos entrenados del modelo. Son requeridos y cargados automáticamente por el `model.json`.
- `README.md`: Este archivo de documentación técnica.

## 📖 Guía Básica de Uso

1. Levanta tu servidor local (ej. `python3 -m http.server 8000`).
2. Ingresa a `http://localhost:8000` desde el navegador de tu computadora o dispositivo móvil conectado a la misma red (en este último caso, usando la IP local de la computadora).
3. Concede los permisos de uso de cámara en tu navegador.
4. Apunta con la cámara web de tu dispositivo a una foto real de un perro o un gato (también funciona apuntando a una imagen en otro monitor o celular).
5. Observa el área inferior de la pantalla: el modelo actualizará automáticamente el texto ("Perro" o "Gato") en tiempo real según lo que capte la cámara.
6. Si estás en un dispositivo móvil con múltiples cámaras, puedes usar el botón azul **"Cambiar camara"** para alternar entre la cámara frontal y la trasera.
