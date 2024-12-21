# Reconocimiento de Emociones Faciales con VGG16

Este proyecto implementa un modelo de aprendizaje profundo para clasificar emociones faciales en cuatro categorías principales: Neutral, Triste, Feliz y Enojo. Utilicé la arquitectura VGG16 preentrenada como base para la extracción de características, añadiendo capas personalizadas para la clasificación. Este trabajo busca explorar la capacidad del modelo para identificar emociones humanas en imágenes faciales reales y demostrar su aplicabilidad en diversos contextos, como interfaces humano-computadora y análisis emocional.

## Características

- **Entrenamiento:** Utilizando TensorFlow/Keras 
- **Visualización:** Incluye gráficos de precisión, pérdida y matriz de confusión.
- **Automatización:** Compatible con Docker para una configuración y ejecución sencilla.

## Requisitos previos

Asegúrate de cumplir con los siguientes requisitos antes de comenzar:

- [Docker](https://www.docker.com/): Confirma que Docker está instalado y operativo.
- [NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html#prerequisites): Necesario para aprovechar TensorFlow con GPU.

Verifica que Docker funciona correctamente ejecutando:

```bash
docker --version
```

Para confirmar que `nvidia-smi` funciona:

```bash
nvidia-smi
```

---

## Pasos para construir y ejecutar el contenedor

### 1. Clonar el repositorio

Clona este repositorio en tu máquina local usando:

```bash
git clone https://github.com/Roussd/Emociones-VGG16.git
cd Reconocimiento-Emociones
```

### 2. Construir la imagen Docker

Ejecuta el siguiente comando para construir la imagen desde el `Dockerfile`:

```bash
docker build -t nombre_imagen .
```

Por ejemplo, para nombrarla "emociones-dl":

```bash
docker build -t emociones-dl .
```

Esto generará una imagen con ese nombre.

---

### 3. Ejecutar el contenedor

Lanza el contenedor con soporte para GPU usando el comando:

```bash
docker run --gpus all -p 8888:8888 nombre_imagen
```

Esto asignará las GPUs disponibles al contenedor.

---

### 4. Acceder a Jupyter Notebook

Cuando el contenedor esté en ejecución, verás un enlace en la terminal similar a:

```
http://127.0.0.1:8888/tree?token=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

Copia y pega este enlace en tu navegador para acceder a Jupyter Notebook.

---

## Comandos útiles

### Listar imágenes Docker disponibles

```bash
docker images
```

### Listar contenedores (incluidos los detenidos)

```bash
docker ps -a
```

### Eliminar una imagen Docker

```bash
docker rmi <image_id>
```

**Sugerencia:** Puedes usar los primeros 4 caracteres del ID de la imagen para referenciarla.

### Eliminar todos los contenedores detenidos

```bash
docker container prune
```

---

## Notas adicionales

- **NVIDIA Drivers**: Es necesario tener instalados los controladores de NVIDIA.
- **Dataset**: Asegúrate de descargar y preparar el dataset AffectNet en la ubicación correspondiente antes de iniciar.
